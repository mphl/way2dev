# Integrando Softwares (API)

Dando um pouco de contexto para quem caiu aqui de paraquedas:

> API é um conjunto de padrões estabelecidos por um software para a utilização das suas funcionalidades por outros interessados que não pretendem envolver-se em detalhes da implementação, mas apenas usar seus serviços.

Certo, dado que um software precisa de uma funcionalidade de outro software, tem duas formas dele requisitar isso:

## Comunicação síncrona
Isso quer dizer que ao fazer uma chamada para outro software, você fica esperando ele responder para continuar com seu processamento. 

Algumas técnicas pra gente conhecer:
- [Lib / Plugin](lib): Usamos bibliotecas de terceiros o tempo todo em nosso código.
- [RPC/gRPC](rpc) : Essa é a forma mais antiga, e o Google deu uma repaginada criando o gRPC.
- [REST](rest): Essa provavelmente é o tipo mais comum.
- [GraphQL](graphql): Esta é a forma que  o Facebook achou para contornar os problemas do REST.
- [Websockets](websockets): Comunicação onde a troca de mensagens é constante, e não apenas uma chamada e uma resposta.
- [MQTT](mqtt): Esse é o padrão para IoT (intert das coisas). 


## Comunicação assíncrona
Nesta comunicação você realiza um comando em outro software mas segue seu processamento, pois você não precisa da resposta imediata para tomar realizar alguma ação.

Técnicas:
- [Fire and forget](fireAndForget): Essa técnica é a mais simples, você utiliza o mesma comunicação síncrona, mas não espera o retorno para continua seu código.
- [Message Broker / Filas](messageBroker): Provavelmente a mais utilizada.
- [Event streaming](eventStreaming): Essa técnica é muito difundida utilizando a ferramenta Kafka.
