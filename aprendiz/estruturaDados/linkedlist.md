# LinkedList (lista encadeada)
Esta estrutura de dados representa uma lista encadeada linear. Diferentemente do Array, onde todos os elementos se encontram de forma consecutivas e pré-definidas em memória, a LinkedList  possui um ponteiro indicando onde está o primeiro elemento (chamado de head/cabeça), o próprio elemento e um ponteiro para onde está o próximo elemento. Algumas linguagens de programação também implementam um ponteiro para o último elemento (chamado de tail/cauda).
Assim como o Array, essa estrutura de dados não é boa para verificar se algum elemento existe nesta coleção que não esteja no início ou no fim.


### Essa estrutura de dados parece complicada de lembrar ? Vou te dar um exemplo.
Imagina que você tivesse que criar uma lista de todas as pessoas que leram um determinado livro. No momento da criação, você ainda não sabe o tamanho dessa lista, e muito menos se ela vai ser pequena ou grande, então usar um array para essa abordagem não seria bom. Você poderia então anotar apenas o nome da primeira pessoa que leu e pedir para ela guardar o nome da pessoa que ela emprestou o livro. Assim, sempre que uma pessoa nova ler o livro, basta colocar o nome dela no fim da lista. Mas vou te contar o lado ruim dessa abordagem: e se você quiser saber se o João já leu o livro? Infelizmente, você teria que utilizar o ponteiro do início (head) e percorrer toda a lista para ver se o nome dele aparece.


## Checkpoint
Faça uma lista comparando as vantagens e desvantagens do Array e da LinkedList.

