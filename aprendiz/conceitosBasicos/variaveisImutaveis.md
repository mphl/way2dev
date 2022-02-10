 # Variáveis imutáveis e Constantes

Variáveis imutáveis não podem ter seu valor alterado após a primeira atribuição, ou seja, variáveis imutáveis recebem valor uma única vez e preservam esse valor por toda a sua existência. 

Esse tipo de variável é usado para <u>garantir que um valor atribuído não seja substituído</u> por engano ou de forma inadvertida, forçando ao desenvolvedor criar uma nova variável que receberá o valor atualizado, caso essa operação seja necessária. 

Alguns exemplos de variáveis imutáveis:

 *Javscript:*

 ```javascript
const valor = 10 //const define que o valor não poder ser alterado
valor = 11 //aconteceria um erro de execução
 ```

 *Java:*

 ```java
private final int valor = 10; //final define que o valor não poder ser alterado
valor = 11; //aconteceria um erro de compilação
 ```



Já as constantes são uma especialização das variáveis imutáveis. Constantes também são variáveis imutáveis, mas com o objetivo de oferecer um **valor constante dentro da aplicação**. Constantes são usadas para definir configurações, ou evitar que um mesmo valor tenha sua atribuição feita diversas vezes pelo código, o que poderia abrir brechas para erros.

Normalmente as constantes são aplicadas em letras maiúsculas, mas pode haver variação em relação às **boas práticas aplicadas pela linguagem de programação** em uso. Ex:

```javascript
 const SEPARADOR = ';'

 resultado1 = `valor1${SEPARADOR}valor2` //resultado1 receberia um texto de valor igual a valor1;valor2
 resultado2 = `valor3${SEPARADOR}valor4` //resultado2 receberia um texto de valor igual a valor3;valor4
```

Caso a regra de negócio do exemplo acima mudasse e o `separador` passasse a ser uma barra (/), bastaria mudar o valor da constante para que todo o código seguisse a nova regra. Ex:

```javascript
 const SEPARADOR = '/' // única mudança no código
 
 resultado1 = `valor1${SEPARADOR}valor2` //resultado1 receberia um texto de valor igual a valor1/valor2
 resultado2 = `valor3${SEPARADOR}valor4` //resultado2 receberia um texto de valor igual a valor3/valor4
```

Constantes e variáveis imutáveis podem possuir algumas diferenças na forma de declaração conforme a especificação de cada linguagem utilizada, mas as principais diferenças são os locais em que as mesmas são declaradas (constantes possuem um escopo mais abrangente do que variáveis imutáveis) e possuem objetivos levemente diferentes, com as variáveis imutáveis preocupadas em manter sempre o mesmo valor durante seu ciclo de vida, mas podendo receber valores diferentes a cada vez que são criadas, enquanto às constantes tem o objetivo de fornecer um **valor constante durante todo o tempo de execução da aplicação**.



## Na prática:

Para testarmos as variáveis imutáveis na prática, vamos usar um console de javascript presente na web: o [jsconsole](https://jsconsole.com/). Um console serve para pequenos testes, e é exatamente o que faremos aqui. **Atenção:** apesar de estarmos usando javascript para o exemplo, os conceitos aqui servem para **qualquer linguagem de programação** sofrendo apenas variações de sintaxe. 

Com o [jsconsole](https://jsconsole.com/) aberto em outra aba digite:

```javascript
const testConst = "valor"
```

e pressione a tecla "Enter".
O console exibira algo como 

```javascript
< undefined 
```

Notou o sinal de `>` e `<` no começo de cada linha do console? O sinal de `>` indica que o console está esperando que digitemos alguma coisa, já o sinal de `<` indica o **resultado** do comando que acamos de inserir. Quando fizemos a criação da variável usando o comando `const testConst = "valor"` apenas definimos o texto `valor` dentro da variável teste. A operação de definir valores, ou fazer **atribuições** de variáveis, é uma operação que normalmente não gera um retorno utilizável.

Bom, com isso acabamos de criar uma variável de valor constante. Se você digitar apenas `testConst` no jsconsole, você receberá o valor atual dela. Mas e ae, será que não é possível mesmo alterar o valor desta variável? Tente digitar no console:

```javascript
testConst = "novo valor"
```

Recebeu um erro, né? Algo como:

```javascript
TypeError { "Assignment to constant variable." }
```

Isso é o que a gente espera de uma variável imutável: que ninguém consiga trocar seu valor a partir do momento de sua **inicialização**, ou seja, a partir do momento que ela recebe seu primeiro valor. Variáveis imutáveis são muito úteis quando queremos preservar um valor específico e evitar que um trecho de código troque seu valor por acidente.

