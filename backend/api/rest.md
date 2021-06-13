# Rest

Com certeza essa é a forma de integração mais comum atualmente, tanto que quando algumas pessoas falam em API, elas já subentendem que é uma API REST, nem pensam que poderia ter outros tipos de integração. Mas vamos conhecer um pouco mais sobre esse modelo tão conhecido mas tão mal compreendido.

*Representational State Transfer*(REST), em português Transferência Representacional de Estado, é um estilo de arquitetura que define como dois softwares devem se comunicar. Essa arquitetura foi criada pelo cientista da computação Roy Fielding e sua dissertação pode ser lida [aqui](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm). Mas como eu sei que você não vai ler a dissertação ( ͡° ͜ʖ ͡°), vamos ao resumo:
 
 - REST é uma arquitetura Client-Server. Onde um cliente vai requisitar informações para um servidor.
 - REST é *stateless* (sem estado). Então uma requisição ao servidor não pode ter conhecimento de nenhum contexto armazenado no servidor.
 - REST define que os recursos de um software devem ser disponibilizados através de URIs.
 - REST define que os recrusos devem ser manipulados através dos verbos HTTP:
  - **GET**: Busca um recurso.
  - **POST**: Cria um recurso.
  - **PUT**: Atualiza completamente um recurso.
  - **PATCH**: Atualiza parcialmente um recurso.
  - **DELETE**: Remove um recurso
  - **HEAD**: Busca apenas o *header* de um resource
  - **OPTIONS**: Retorna os verbos HTTP disponíveis em um recurso. Além de outras informações como CORS.
 - A resposta sobre a solicitação de manipulação de um recurso deve vir como código HTTP:
  - **1XX**: Respostas de informação
  - **2XX**: Respostas de sucesso
  - **3XX**: Redirecionamentos
  - **4XX**: Erros do cliente
  - **5XX**: Erros do servidor
  - Para lista detalhada de todos os possíveis resultados, consultar [aqui](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status).

Não se esqueça de dois conceitos:
- **Idempotente** significa que o método pode ser chamado várias vezes sem resultados diferentes. Isso se aplica apenas ao resultado, não ao próprio recurso. Os métodos PATCH e POST não são idempotentes por natureza, todavia é possível implementar o método POST com uma chave no HEADER para garantir idempotencia ao criar um registro.
- **Safe** são métodos de apenas leitura. Isso significa que são seguros e não importa quantas vezes chamar, ele não irá alterar o estado do resource. Apenas métodos GET, HEAD e OPTIONS são Safe. 

# Dicas
- Utilizar o nome dos recursos sempre no plural.
- Separa nomes compostos por hífen.
- Nomes sempre em minúsculo.
- Após o nome do recurso sempre deve vir o identificador do recurso e seus filtros. Exemplo: `users/123` ou `users?state=SP`.
- Um GET sem ID sempre retorna uma lista



Agora que você já aprender a desenhar sua API com REST, fica aqui para aprender a documenta-la: OPen API.
- Evite usar subdomínios. 
