

 # Tipos de dados

Tipos são usados para definir qual o tipo de conteúdo que uma variável pode receber ou os tipos de entrada e retorno usados por uma função. São usados para garantir que o código escrito trabalhe com o tipo de informação que ele conhece. Sem os tipos, uma calculadora pode receber o texto "oi" e gerar um erro, já que a calculadora não sabe o que fazer com o valor "oi".

Existem vários tipos de dados: numéricos, alpha-numéricos, datas, conjuntos, objetos, entre outros.

Em algumas linguagens, tipos são sempre representados por objetos, em outras existem os *tipos primitivos*, que são tipos fundamentais na linguagem, e *tipos complexos* que nada mais são do que objetos. Os tipos primitivos normalmente representam apenas o valor do dado, sem ações pré estabelecidas além da compatibilidade com operações matemáticas, já os tipos complexos possibilitam o uso de todas as operações presentes na definição do objeto.

Alguns tipos mais comuns em linguagens de programação:

### Numéricos:

- long - tipo usado para inteiros, sem casas decimais, até 64 bits
- int - tipo usado para inteiros, sem casas decimais, até 32 bits
- double - tipo usado para valores com casas decimais, até 64 bits
- float - tipo usado para valores com casas decimais, até 32 bits
- short - tipo usado para inteiros pequenos, de até 16 bits
- byte - tipo usado para números inteiros de até 8 bits

### Texto

- string - valor de tipo alpha-numérico, usado para armazenar textos
- char - valor que representa um único caracter. Pode ter seu valor representado pelo próprio caracter, ou por um correspondente numérico

### Outros

- array - representa um conjunto de elementos
- Objeto - o nome da classe define que apenas objetos criados por aquela classe podem ser atribuídos (respeitando ocorrência de herança, quando disponível pela linguagem em uso).

Os tipos disponíveis variam com relação a linguagem de programação utilizada.

 ## Tipagem estática

Tipagem estática é uma **característica de linguagens de programação**, que estipula a necessidade de se informar qual o tipo de uma variável ou de retorno de uma função. Algumas linguagens de tipagem estática possuem o recurso de *inferência* (explicado mais abaixo) para reduzir a verbosidade causada pelo modelo. 

Essa definição de tipo acontece *antes da execução do código*, ou seja, já definimos o tipo **enquanto estamos codificando o programa**. Essa característica é predominante nas linguagens que passam por processo de *compilação* ou conversão para *bytecode*.

A tipagem estática é uma característica muito útil na identificação de possíveis erros no código durante o desenvolvimento.

Exemplo:

```
Objeto valor = new Objeto(); // Tipo objeto foi declarado de forma estática
```

 ## Tipagem dinâmica

A tipagem dinâmica é a característica de uma linguagem de programação de definir o tipo de uma variável ou dos dados usados em uma função *durante sua execução*, sem definição prévia de tipo. Isso implica que **o programa só saberá o tipo da variável quando tiver seu primeiro valor atribuído**.
Tipagem dinâmica ocorre normalmente em linguagens de scripts, mas não existe essa obrigatoriedade. Existem linguagens de script que possuem tipagem estática.

Exemplo:

```
valor = new Objeto(); // O tipo da variável só vai ser definido quando essa linha de código for executada.
```

## Inferência

Inferência é a habilidade de uma linguagem de programação de "descobrir" qual o tipo de uma variável pela atribuição de valor. Inferência é um recurso de linguagens de *tipagem estática*, já que linguagens de tipagem dinâmica não precisam de inferência.

Em linguagens de tipagem estática, você define o tipo da variável durante a declaração. Ex:

```
Tipo variavel = new Tipo(); // declaração e atribuição de uma variável de tipo "Tipo".
```

Quando a linguagem de programação tem suporte a inferência, essa mesma declaração pode ser feita como:

```
variavel = Tipo(); // Não foi necessário declarar o tipo da variável
```

Apesar de parecer que o tipo de variável não foi definido antes da execução do programa, **a definição acontece através da inteligencia existente em compiladores ou pré-compiladores**, e o código em execução já possui o tipo de dado corretamente definido.



## Tipagem forte e fraca

 ## 