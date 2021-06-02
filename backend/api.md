# Integrando Softwares (API)

Dando um pouco de contexto para quem caiu aqui de paraquedas:

> API é um conjunto de padrões estabelecidos por um software para a utilização das suas funcionalidades por outros interessados que não pretendem envolver-se em detalhes da implementação, mas apenas usar seus serviços.

Certo, dado que um software precisa de uma funcionalidade de outro software, tem duas formas dele requisitar isso:

## Comunicação síncrona
Isso quer dizer que ao fazer uma chamada para outro software, você fica esperando ele responder para continuar com seu processamento. 

Essas são as técnicas mais comuns:
- RPC/gRPC : Essa é a forma mais antiga, e o Google deu uma repaginada criando o gRPC.
- XML: Tentativa de organizar um pouco o RPC.
- REST: Essa provavelmente é o tipo mais comum.
- GraphQL: Esta é a forma que  o Facebook achou para contornar os problemas do REST.
- Websockets: Comunicação onde a troca de mensagens é constante, e não apenas uma chamada e uma resposta.
- MQTT: Esse é o padrão para IoT (intert das coisas). 


## Comunicação assíncrona
Nesta comunicação você realiza um comando em outro software mas segue seu processamento, pois você não precisa da resposta imediata para tomar realizar alguma ação.

