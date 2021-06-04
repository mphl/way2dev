# RPC e gRPC

> Chamada de procediemento remoto (RPC, acrônimo de Remote Procedure Call) é uma tecnologia de comunicação entre processos que permite a um programa de computador chamar um procedimento em outro espaço de endereçamento (geralmente em outro computador, conectado por uma rede). O programador não se preocupa com detalhes de implementação dessa interação remota: do ponto de vista do código, a chamada se assemelha a chamadas de procedimentos locais.

Se você quiser conhecer a fundo RPC você pode ler a página da [Wikipedia](https://pt.wikipedia.org/wiki/Chamada_de_procedimento_remoto) que traz informações super interessantes, mas não vou explicar aqui a RFC de 1976 ou tecnologias defasadas como CORBA, SOAP e RMI. Prefiro que a gente foque apenas em características principais do RPC e no que o Google fez para melhorar o RPC.

### Qual a maior vantagem do RPC ?
Poder trabalhar com computação distribuída, executando pedaços de código em computadores e redes diferentes sem se preocupar com a implamentação destes métodos.

### Qual a maior desvantagem do RPC ?
RPC é focado nos métodos que você precisa executar, então conhecer a diferença dos métodos e os objetos trafegados na entrada e saída pode dar um pouco de trabalho. Outro problema é você ter que se procupar com o formato da mensagem e os problemas que podem acontecer na rede durante a comunicação com sua chamada remota.

O [SOAP](https://pt.wikipedia.org/wiki/SOAP) tentou resolver essa questão utilizando [XML](https://pt.wikipedia.org/wiki/XML) para definir a estrutura das chamadas e o protocolo [HTTP](https://pt.wikipedia.org/wiki/Hypertext_Transfer_Protocol) para resolver as questões de rede. Porém, manter os [WSDL](https://pt.wikipedia.org/wiki/Web_Services_Description_Language) era algo tão trabalhoso, que acabou fazendo o [REST](rest) ficar muito mais popular.

## gRPC
> É um framework de alta performance, open source e universal para trabalhar com RPC.

O Google utiliza RPC em suas aplicações a muito tempo, então desenvolveu seu próprio framework para contornar os problemas listados acima. Quer saber como? Vamos lá:

- Você não precisa se preocupar com a rede, todo o trabalho de manter a comunicação entre os serviços é feita por baixo dos panos pelo gRPC. Diga-se de passagem que ele utiliza HTTP/2 para fazer isso, então possíbilita streaming bidirecional (consegue enviar e receber dados ao mesmo tempo). Se amanha o padrão for HTTP/3, você não vai se preocupar em ter que mudar todo seu código, apenas atualizando sua biblioteca de gRPC, tudo isso vai estar lá pronto.
- Toda a descrição das funções e objetos é feita em arquivos [Protobuf](https://developers.google.com/protocol-buffers), desta forma é possível gerar clientes e servidores com apenas um comando. Obs. gRPC também suporta outros formato de mensagem como JSON ou XML, mas o mais comum é utilizar o Protobuf mesmo.
- Já que o gRPC está controlando todas as chamadas, é facilmente adicionado autorização, tracing, load balance e health check.



