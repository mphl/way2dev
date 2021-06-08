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
