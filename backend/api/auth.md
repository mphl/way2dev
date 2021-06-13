# Autenticação e autorização

Navegando na internet, acessando nossos apps e até mesmo para acessar logar no computador, estamos acostumados com telinhas de usuário e senha para controlar o acesso. Mas você já parou pra pensar como isso funciona ? Esse tópico vai tentar te explicar um pouco mais sobre isso.

Primeiro de tudo, temos que entender a diferença entre autenticação e autorização.

- **Autenticação**: é o processo de descobrir quem esta fazendo uma requisição e se aquela pessoa realmente é quem ela diz ser.
- **Autorização**: é o processo para saber se uma pessoa pode fazer o que ela está querendo fazer.

Muitas pessoas acreditam que quando estão fazendo chamadas internas (dentro dos servidores) não precisam se preocupar com autenticação e autorização, porém, essa prática gera vários problemas de matenção a longo prazo, como se alguma pessoa está fazendo muitas requisições no seu serivço, você não sabe para quem comunicar.

Então, sem mais delongas, vamos aprender a ter confiança zero e criar autenticação e autorização nos nossos softwares.

Qual é a forma mais simples de saber quem está chamando um serviço?
Poderia passar uma chave pra cada consumidor dos recursos, assim, sempre que tiver uma requisição da pra saber quem fez ela.

Qual é a forma deu saber que a pessoa que está fazendo a chamada realmente é ela ? Como saber o que ela pode acessar ?
Para isso, precisamos de garantir que sempre que uma requisição é feita, ninguem consiga alterar os dados dela.

E é aí que o JWT chega para nos ajudar!

## JWT
JWT (JSON Web Token) é um método para representar reivindicações de forma segura entre duas partes.

Se você quiser ficar fera e entender tudo sobre isso, aqui esta a [RFC](https://datatracker.ietf.org/doc/html/rfc7519) contendo toda explicação, mas vou fazer um resumo:

Você pode passar usuário e senha somente uma vez e receber um token, depois as requisições seguintes só precisam veriricar se o token é válido e se a tem permissão para aquela rota.

Vamos supor que você queira fazer uma requisição e passar as seguintes informações: Eu sou o Marcos, meu ID é 123 e sou admin. Já imaginou que seria muito fácil para outra pessoa mudar a requisição dela e dizer que é admin também ?!
Vou te mostrar como o JWT resolve isso. 
Ele separa a informação em três partes:
- A primeira é o cabeçalho contendo o algoritmo utilizado e o tipo do token.
- A segunda são os campos que você quer transmitir.
- A terceira é uma assinatura dos seus dados, e aqui que entra a segurança da sua requisição, pois somente um token assinado é valido.

Quer ver isso na prática ?
Esse é um token JWT que gerei
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiTWFyY29zIiwiaWQiOiIxMjMiLCJyb2xlIjoiYWRtaW4ifQ.CvzchzYI18CLUzOJJRriY3HfhRYElNu970IaPRqW-SE
```
Se você entrar no site [jwt.io](https://jwt.io/) e digitar no campo `Encoded` esse código acima, vai conseguir ver exatamente as informações que comentei
```
{
  "name": "Marcos",
  "id": "123",
  "role": "admin"
}
```
Então você deve estar pensando, isso não é seguro nada, qualquer um pode pegar meu token e ver e alterar minhas chaves!
Mas isso é somente metade verdade. 
Realmente o token JWT não é criptografado, ele é apenas encodificado. Isso quer dizer que o seu arquivo texto foi tranformado em outro texto, evitando que você possa ter problemas com acentuação, mas todas as informações são decodificaveis facilmente. Portanto nunca coloque senhas ou informações sensíveis num token JWT. 
A segurança está na assinatura! Você pode ver que o site fala que a assinatura é invalida, isso porque ele não sabe qual assinatura eu utilizei para gerar esse token. Se você for no campo de verificar assinatura do site e começar a digitar, vai ver que a cada letra o site vai falar que a assinatura é valida, pois ele esta validando a chave que você esta digitando com o token do lado esquerdo, mas pode perceber que o token esta sendo alterado constantemente. Se você digitar a senha `way2dev`, vai verificar que o token é igualzinho o que eu gerei ali em cima, e dessa forma o servidor conseguiria identificar que a requisição é válida.

NO payload os campos chamados de claims e existe na RFC alguns reservados q esperam um tipo especifico de dados. Iss (issuer) é quem gerou o token,  o sub (subject) é o assunto, aud (audience). exp (experition time). Existe tb alguns clams publicou do IANA (ta escrito na RFC) q são palavras recomendadas para cada tipo. Exemplo name. Privados são os clams q vc mesmo q cria.

Certo, agora que você já sabe uma maneira simples e segura de comunicar entre dois sistemas, deve ter percebido que faltou alguns pontos, por exemplo, e se você quiser criar novos tokens? Para isso, o OAuth vai te ajudar.

## OAuth
OAuth 2.0 é um framework de autorização que habilita um aplicativo a obter acesso limitado para um serviço de terceiro, introduzindo uma camada de autorização e segmentando as funções do cliente. Ao invés de utilizar credenciais fornecidas pelo proprietário do recurso, o client recebe um *Access Token*, contendo o escopo do acesso, tempo de vida, entre outros atributos. Os *Access Tokens* são emitidos para clients terceiros por um servidor de autorização com a aprovação do proprietário do recurso.

O OAuth 2.0, define 4 papéis:

- **End-User**: Uma entidade capaz de conceder acesso a recursos protegidos. Quando o proprietário do recurso é um usuário, ele provê o nível de acesso, limitando o escopo de autorização (leitura ou escrita).
- **Resource Server**: Servidor que hospeda os recursos protegidos, capaz de aceitar e responder a solicitações de recursos protegidos utilizando tokens de acesso.
- **Client**: Um aplicativo que faz solicitações a recursos protegidos em nome do proprietário do recurso, com a sua autorização.
- **Authorization Server**: É o servidor que emite e revoga e informa dados sobre o escopo do token tokens de acesso ao , após autenticar com sucesso e obter autorização do .

Entre esses papeis são tráfegados tokens como:
- Access Token
- Refresh Token
- Authorization Token
- Identity Token

Para se aprofundar mais no assunto e entender as melhores práticas de segurança do Oauth, recomenda e leitura desta [RFC](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics-16).

Até agora já sabemos como é a estrutura de um token JWT e que o OAuth nos ajuda a gerenciar tokens, mas se você quer saber mais sobre autenticação, então o OpenID Connect que vai te ajudar.

## OpenID Connect 
Enquanto o OAuth 2.0 trata do acesso e compartilhamento de recursos, o OIDC trata da autenticação do usuário. Seu objetivo é fornecer a você um login para vários sites. Cada vez que você precisa fazer login em um site usando OIDC, você é redirecionado para o site OpenID, onde faz o login, e depois é levado de volta ao site. Por exemplo, se você escolheu entrar no Way2dev usando sua conta do Google, então você usou o OIDC. Depois de autenticar com sucesso com o Google e autorizar o Way2Dev acessar suas informações, o Google envia informações de volta para Way2Dev sobre o usuário e a autenticação realizada. Essas informações são retornadas em um JWT. Você receberá um token de acesso e, se solicitado, um token de ID.

Os JWTs contêm *claims*, que são declarações (como nome ou endereço de e-mail) sobre uma entidade (normalmente, o usuário) e metadados adicionais. A especificação OpenID Connect define um conjunto de declarações padrão. O conjunto de declarações padrão inclui nome, e-mail, gênero, data de nascimento e assim por diante. No entanto, se desejar capturar informações sobre um usuário e atualmente não houver uma declaração padrão que reflita melhor essa informação, você pode criar declarações personalizadas e adicioná-las aos seus tokens.

Se o seu sistema precisar de mais segurança, você pode implementar CIBA (Client-Initiated Backchannel Authentication), desta forma o usuário vai precisar de um dispositivo para aprovar uma requisição de acesso, conforme ilustrado na imagem abaixo:
<img src="https://miro.medium.com/max/1400/1*Pep5bbuMn6P84yIe_ExSWA.png" alt="CIBA" />

Agora se você estiver trabalhando com sistemas financeiros ou precisar de muita segurança mesmo, então minha sugestão é que você aprenda como funciona o FAPI (Financial-grade API) que é uma especificação de como usar o OAuth2 e OpenID Connect como base e definir requisitos técnicos para garantir uma segurança maior.


## Gestão de acessos
Você deve estar pensando: "nossa, deve dar um trabalhão fazer toda essa gestão de autorização e autenticação". 

Realmente, é um pouco trabalhoso e cansativo. Pensando nisso foi criado ferramentas para te ajudar nesse processo. Existe o [Keycloak](https://www.keycloak.org/) que é uma ferramenta open source e o [Cognito](https://aws.amazon.com/pt/cognito/) caso você esteja trabalhando no cloud da AWS. Assim, todo o controle da identidade dos usuários e o que eles podem acessar fica centralizado em uma ferramenta.

## Resumo
- Tokens JWT é a maneira de trafegar informações entre sistemas de forma segura. 
- OAuth é o framework que te ajuda o controlar os Tokens.
- OpenID Connect (OIDC) é uma forma de organizar a autenticação do usuário.
- CIBA e FAPI são maneiras de fornecer mais segurança para nossos usuários e sistemas
- Keycloak e Cognito são ferramentas para fazer a gestão de autorização e autenticação

Ficou fera 🦁 em segurança de API heim 😉
