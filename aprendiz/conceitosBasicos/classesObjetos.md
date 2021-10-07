
# Trabalhando com Objetos

Classes e Objetos são recursos um pouco confusos de entender quando estamos começando com desenvolvimento. Não que sejam recursos complicados, na verdade a diferenciação é bem claro. O que costumamos ter dificuldade é de enxergar essa diferenciação.



 ## Classes

Classes são definições de [Tipo](./tipos.md), ou seja, definições de um elemento que terá participação no seu aplicativo. 
Imagine que para nosso sistema funcionar, devemos trazer para dentro do sistema a definição de um aluno. Para podermos definir o que é um aluno dentro do sistema, temos algumas perguntas para responder:

- Qual a *estrutura* esperada de um aluno dentro do meu sistema?
- Quais *atributos* devem estar associados a um aluno para que o sistema funcione?
- Quais *ações* um aluno deve fazer no meu sistema?



Levando essas perguntas em consideração, podemos começar a estruturar como seria a representação do aluno em nosso sistema:

```
classe Aluno {
  nome;
  idade;
  anoLetivo;

  fazerMatricula(canalDeAtendimento) {
    ...
  }
}
```

No exemplo acima defimos alguns *atributos* para nosso aluno, como **nome, idade e anoLetivo**. Você deve notar que não definimos os **valores** desses atributos, apenas **especificamos** quais atributos um aluno deve ter. Além disso, adicionamos uma [**função**](./funcoes) chamada **fazerMatricula(canalDeAtendimento)**, que seria uma **ação** que poderia ser executada a partir de um Aluno. Isso é uma classe: a **especificação** de o que seria um elemento dentro de seu sistema. Agora precisamos transformar essa especificação em algo utilizável, e é aí que entram os **objetos**.



 ## Objetos

 Objetos são *instâncias* de uma classe, nome um pouco complicado mas que significa que estamos criando algo baseado em uma *definição* ou *especificação* com uma finalidade em específico. Fazendo uma relação com o dia a dia, pense em um formulário de usuário por exemplo. Um formulário de usuário teria campos como nome, sobrenome, email e senha. Antes de preenchermos o formulário, não temos a instância do seu usuário, não temos o **registro representando você**. Temos apenas as informações que um usuário em geral deveria ter. Quando preenchemos os dados do usuário e enviamos, criamos um registro de usuário que representa você, ou seja, uma instância de usuário, algo que representa um usuário em específico.

Levando em consideração o exemplo de classe representado anteriormente, criaremos a instância de um *Aluno*. Cada linguagem de programação tem uma forma de representar a criação de um Objeto a partir de uma classe. No nosso exemplo, usaremos o operador **new**, muito comum em várias linguagens.

```
alunoOrlando = new Aluno
alunoOrlando.nome = "Orlando"
alunoOrlando.idade = 16
alunoOrlando.anoLetivo = "segundo colegial"
```

Com o exemplo, o que significa instanciar um Objeto deve ter ficado mais claro: temos uma variável para representar um aluno chamado Orlando. Essa variável deve respeitar a estrutura de um aluno, então alimentamos essa variável com um Objeto criado a partir da especificação de um aluno. Fazemos a criação desse objeto dizendo que queremos um **new** (novo em inglês) Aluno. A palavra Aluno aqui referencia a Classe que criamos anteriormente. Com uma nova *referência* do que será nosso aluno, começamos a alimentar os **atributos** do aluno que estamos representando.

Consegue notar como podemos usar a *especificação* feita na **classe** *Aluno* para criar vários **objetos** de *Aluno* representando alunos diferentes? Essa é a mecânica básica em *linguagens de programação orientadas a objeto*: **especificar** como um determinado elemento deve ser dentro de nosso código, e **criar diversas instâncias** dessa **especificação** para representarmos **elementos diferentes de um mesmo tipo**, separando as características do indivíduo em si.



## Construtores

Em classes temos um tipo de [função](./funcoes.md) especial, ela é chamada de *construtor*. 

Um construtor é como se fosse um atalho, uma forma de construir uma nova instância de nossa classe já com todos ou alguns atributos preenchidos. Pode ser usado para garantir que um objeto não seja criado sem a presença de alguns valores de atributos obrigatórios, ou para facilicar a criação de um objeto.

Usando o caso do aluno Orlando visto anteriormente, poderíamos criar o mesmo tirando proveito de um construtor:

```
alunoOrlando = new Aluno("Orlando", 16, "segundo colegial")
```

Os **parenteses** que acompanham a chamada `new Aluno` é a forma que chamamos um construtor na grande maioria das linguagens de programação, mas existem algumas exceções que não trataremos aqui. 
No exemplo acima já criamos o Aluno com todos os valores de atributos que haviamos definido em nossa classe Aluno. Mas o construtor não é gerado de forma automática. No nosso caso para que o exemplo acima funcione, precisaríamos descrever o construtor em nossa classe, caso contrário a chamada acima apresentaria um erro.

Para expecificarmos um construtor em nossa classe, definiríamos algo semelhante a:

```
classe Aluno {

  constructor Aluno(nome, idade, anoLetivo) {
     this.nome = nome
     this.idade = idade
     this.anoLetivo = anoLetivo
  }

  nome;
  idade;
  anoLetivo;

  fazerMatricula(canalDeAtendimento) {
    ...
  }
}
```

No exemplo acima, criamos um construtor que recebe as variáveis e grava as mesmas dentro dos atributos do objeto a ser criado. Por isso usamos a palavra-chave **this** . **this** é um recurso comum de algumas linguagens de programação, mas pode ser encontrado como **self** e algumas outras variações dependendo da linguagem. Usamos o *this* aqui para diferenciar os atributos do objeto e os parâmetros da função, já que as mesmas possuem o mesmo nome. 