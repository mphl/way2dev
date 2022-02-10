

# Variáveis

 Variáveis são ferramentas de alocação de dados. Uma variável simplesmente recebe atribuições de valores. Ex:

 ```javascript
	x = 10
	y = x + 5 
 ```

 Nesse exemplo, `y` receberá o valor atual de `x` (10) com a soma do valor 5. Portanto `y` terá o valor de 15.

 Uma variável também pode ter seu valor atualizado:

 ```javascript
	x = 10
	x = x + 1
 ```

Depois de executadas as duas instruções, `x` terá o valor *11* e o antigo valor de *10* será perdido. Isso é um ponto muito importante: toda nova atribuição de valor a uma variável removerá seu valor antigo.

## Na prática:

Para testarmos as variáveis na prática, vamos usar um console de javascript presente na web: o [jsconsole](https://jsconsole.com/). Um console serve para pequenos testes, e é exatamente o que faremos aqui. **Atenção:** apesar de estarmos usando javascript para o exemplo, os conceitos aqui servem para **qualquer linguagem de programação** sofrendo apenas variações de sintaxe. 

Com o [jsconsole](https://jsconsole.com/) aberto em outra aba digite:

```javascript
let test = 10
```

e pressione a tecla "Enter".
O console exibira algo como 

```javascript
< undefined 
```

Notou o sinal de `>` e `<` no começo de cada linha do console? O sinal de `>` indica que o console está esperando que digitemos alguma coisa, já o sinal de `<` indica o **resultado** do comando que acamos de inserir. Quando fizemos a criação da variável usando o comando `let test = 10` apenas definimos o valor 10 dentro da variável teste. A operação de definir valores, ou fazer **atribuições** de variáveis, é uma operação que normalmente não gera um retorno utilizável. Veremos mais sobre isso no futuro.

Bom, assim que apertamos a tecla **enter**, criamos uma nova variável chamada `test` contendo o valor 10. Vamos checar se o valor 10 realmente está contido na variável `test`? No jsconsole escreva apenas `test` e aperte **enter**.

O jsconsole exibiu um retorno parecido com:

```javascript
< 10
```

correto?

Isso acontece porque o console está nos mostrando o valor presenta na variável que criamos. `test` representará o valor de 10 até que alteremos seu valor ou até fecharmos o console. Experimente digitar agora:

```javascript
test + 1
```

O resultado foi

```javascript
< 11
```

Correto? Isso acontece pq você fez uma operação matemática de adição, aproveitando a variável que você criou anteriormente e somando a ela o valor 1. Dessa forma uma variável permite que você faça diversas operações com o valor atribuído a ela, sem ter que ficar digitando o mesmo valor diversas vezes e sem ter que manter o valor **fixo**, permitindo que a gente tenha alguma flexibilidade quando a gente escreve nosso código. Se você digitar apenas `test` novamente, verá que o valor de nossa varriável continua sendo 10.

E se quiséssemos que nossa variável passasse a ter o valor 12 ao invés de 10? Digite no console:

```javascript
test = 12
```

ou 

```javascript
test = test + 2
```

Nos dois casos a variável `test` receberá o valor *12*, conforme exibido no console. A diferença é que no primeiro caso fizemos uma atribuição direta do valor 12, já no segundo, 12 é o *resultado de uma operação de soma*, ou seja, fizemos um cálculo e o que resultou deste cálculo foi armazenado dentro da variável `test`.

Isso tem um efeito colateral: `test` agora contém o valor 12 e não será mais possível obter o valor 10 da mesma, a não ser que façamos uma nova atribuição. Isso fará com que o valor 12 seja perdido e `test` passará a apenas representar o número 10 novamente, até que uma nova atribuição ocorra.

Um ponto importante. Tente escrever novamente:

```javascript
let test = 12
```

 o resultado deve ter sido algo como:

```javascript
SyntaxError { "Identifier 'teste' has already been declared" }
```

Isso acontece porque os nomes de variáveis devem ser únicos dentro de cada escopo. Falamos de escopo [aqui](./escopo.md), e é legal dar uma olhadinha para entender quando é possível ou não usar o mesmo nome de variável.

Importante notar também que quando usamos a palavrinha `let` estamos **criando** uma variável, e quando não usamos nada antes do nome da mesma estamos apenas fazendo uma **atribuição**. `let` é uma palavra da linguagem javscript para definir uma variável que pode ter seu valor alterado. Existem outros tipos de variáveis, como [variáveis imutáveis](./variaveisImutaveis.md), onde não é possível fazer alterações de valor. Caso esteja começando, não se preocupe muito com [variáveis imutáveis](./variaveisImutaveis.md) por enquanto, o importante é saber que elas existem.

