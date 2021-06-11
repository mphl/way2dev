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

Para se aprofundar mais no assunto e entender as melhores práticas de segurança do Oauth, recomenda e leitura desta [RFC](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics-16)

## OPenID Connect
Imagina uma pessoa, se um sistema requisitar informações dela, podemos falar que ela eh professora e se outro sistema requisitar informações, podemos falar que ela ja correu 5km, o open id controle isso. Se vc tem apenas um provider de identidade o open id nao eh necessário.

OIDC provides:

WHO is the user that got authenticated

WHERE was he authenticated

WHEN was he authenticated

WHAT attributes he can give you

WHY he is providing them

Interoperable

- standard scopes : openid, profille, email, address, phone
- method to ask for more granular claims : request object and claims
- id token: info about the authenticated user
- UserInfo endpoint: get attributes about the user. Translate the tokens

Simple

- JSON Based
- REST Friendly

Secure

- choice of crypt

Flexible

- Granular request: Data minimization
- Aggregated claims: does not disclose data recipients to data sources
- Distributed Claims: Decentralized Data Storage

OpenID Connect uses standard JSON Web Token (JWT) data structures when signatures are required. This makes OpenID Connect dramatically easier for developers to implement, and in practice has resulted in much better interoperability.

## FAPI (Financial-grade API)
Agora que vc já aprendeu toda a base de autenticação, se voce trabalha com sistemas financeiros, recomendo conhecer o FAPI https://fapi.openid.net/  que é uma especificação de como usar OAuth2 e OpenID Connect como base e definir requisitos técnicos para industrias que precisam de uma segurança maior.
Financial-grade API, o FAPI, é uma especificação técnica desenvolvida pelo Grupo de Trabalho Financial-grade API da OpenID Foundation. Ele utiliza OAuth 2.0 e OpenID Connect (OIDC) como sua base e define requisitos técnicos adicionais para o setor financeiro e outros setores que exigem maior segurança.

## CIBA
https://miro.medium.com/max/1400/1*Pep5bbuMn6P84yIe_ExSWA.png

## Gestão de acessos
Cognito ou Keyclak


##### Resumo
Pelo q to entendendo ate agora eu posso ter um software como o Keyclak ou Cognito q faz td gerenciamento de usuário e serviços, oprotocolo  oauth q controla a autorização podendo trafegar um JWT (access token) e o open id connec(OIDC) com o IDToken para a autenticação.
