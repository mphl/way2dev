# Funções

Funções, em algumas linguagens chamadas de *métodos* , são usadas para descrever uma <u>ação reusável</u>. Lembra das funções de matemática, como f(x) = x + 1? Essa função sempre soma 1 ao valor atribuído a x:

```javascript
f(1) = 2
f(2) = 3
f(3) = 4
...
```

Uma função de programação tem um objetivo muito semelhante: Assim que uma função tem uma ação definida, podemos chamar essa função para <u>executar uma determinada *regra* sempre que necessário</u>. Um exemplo de uma função em programação:

```javascript
function calcularQuadradoDe(valor) {
  return valor ** 2; 
}

/* O símbolo (**) é usado como operador de exponenciação em javascript. Outras linguagens usam com certa frequência o símbolo (^) */
```

Assim como a função matemática do exemplo anterior, posso usar a função de `calcularQuadradoDe(valor)` sempre que houver necessidade na regra de negócio. Junto das definições de variáveis, poderíamos usar algo como:

```javascript
quadradoDe2 = calcularQuadradoDe(2); // quadradoDe2 receberá o valor 4
quadradoDe5 = calcularQuadradoDe(5); // quadradoDe5 receberá o valor 25
```

Um detalhe importante é a palavrinha mágica `return`. Nesse exemplo ela indica que a função devolve um valor após a sua execução. A palavra `return` é comum em diversas linguagens de programação, mas nem sempre a mesma é necessária, dependendo muito dos recursos da linguagem que você usa.

O ponto importante de ter em mente aqui é que <u>uma função pode ou não retornar um valor após a sua execução</u>. Se ela retornar um valor, você pode atribuí-lo a uma variável como no exemplo de calculoDeQuadrado.
Caso contrário não existe nada a ser atribuído a variável e o código pode apresentar um erro ou gerar um valor nulo em sua variável dependendo da linguagem de programação.

Funções que não retornam dados estão mais relacionadas à <u>alteração de estado em Objetos</u> ou ações de interação direta, como exibir uma mensagem na tela. 



## Na prática:

Para testarmos as funções na prática, vamos usar um console de javascript presente na web: o [jsconsole](https://jsconsole.com/). Um console serve para pequenos testes, e é exatamente o que faremos aqui. **Atenção:** apesar de estarmos usando javascript para o exemplo, os conceitos aqui servem para **qualquer linguagem de programação** sofrendo apenas variações de sintaxe. 

Com o [jsconsole](https://jsconsole.com/) aberto em outra aba digite:

```javascript
function somaDosValores(valor1, valor2){ 
   return valor1 + valor2;
}
```

e pressione a tecla "Enter". **Importante**: Se você quiser usar as mesmas quebras de linha que usei no exemplo, aperte `shift + enter`, já que apertar apenas `enter` sinaliza que o comando está concluído (o que não é verdade) e você receberá um erro como:

```javascript
SyntaxError { "Unexpected token (1:55)" }
```

Agora se você inseriu corretamente o exemplo, receberá o seguinte retorno no console: 

```javascript
< undefined 
```

Notou o sinal de `>` e `<` no começo de cada linha do console? O sinal de `>` indica que o console está esperando que digitemos alguma coisa, já o sinal de `<` indica o **resultado** do comando que acamos de inserir. Quando fizemos a criação da função, essa operação não retornou valores, por isso é exibido o termo `undefined` (não definido). Isso representa que a última operação que fizemos não retornou um valor que pudéssemos colocar em uma variável, e esse é o retorno que esperamos no console.

Agora que temos nossa função definida, podemos reusá-la com qualquer valor que queiramos. Para testar a função, execute o comando:

```javascript
somaDosValores(4, 5)
```

o valor `9` deve ser exibido como retorno. Isso demonstra que nossa função foi corretamente declarada. Teste a função com valores diferentes e tente criar suas próprias funções de cálculo matemático como forma de experimentar :-)





