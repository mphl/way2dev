# Estruturas de repetição

Estruturas de repetição são usadas para executar uma ação repetidas vezes enquanto uma condição se mantém verdadeira. Essas estruturas tem pequenas variações com relação a checar se a condição continua válida, mas todas tem a função.



 ## For

**For** é uma estrutura de repetição normalmente utilizada quando estamos fazendo uma ação para um conjunto de elementos, como por exemplo um array de números. Caso quiséssemos checar se um valor existe em um array, poderíamos escrever o seguinte código:

```
conjuntoDeNumeros = [1,3,2,5,4,6,10] // representação de um array de números inteiros
numeroPesquisado = 3

for(posicao = 0; posicao < tamanhoDo(conjuntoDeNumeros); posicao ++) {
  if(conjuntoDeNumeros[posicao] == numeroPesquisado) return true
}

return false
```

No exemplo acima, definimos o **for** com **3 instruções**, essa é a forma mais tradicional de se escrever um **for**. Essas instruções estão separadas por `;` e significam o seguinte:

- a primeira instrução é usada para criamos uma **variável de controle dentro do loop**. No caso criamos uma variável chamada **posicao** com o valor de **0**, que será usada para controlar qual **posição do array** estamos acessando;
- a segunda instrução é a condição para que o **for** **continue rodando**. No exemplo, o **for** deve continuar rodando enquanto a posição que estamos checando no array for menor que o tamanho total do array;
- a terceira instrução é a "pós-condição", ou seja, o que será feito após a execução de cada repetição do **for**. No caso estamos fazendo a operação **++** no valor de **posicao**, que equivale a **aumentar o valor da variável atual em 1**. Sendo assim, a cada execução do **for**, a variável **posicao** irá ter seu valor incrementado em 1 (começou com 0, na segunda iteração terá o valor de 1, na terceira iteração terá o valor de 2 e assim sussecivamente até alcançar a condição de parada);

Além da condição de parada, outros 2 comandos podem interromper um **for**: **break** que simplesmente interrompe o **for**, e **return** que interrompe o **for** e todo o código de instrução atual (incluindo o que vem depois do for).



Dependendo da linguagem, existem outras formas de se escrever o **for** acima. Por exemplo:

```
conjuntoDeNumeros = [1,3,2,5,4,6,10] // representação de um array de números inteiros
numeroPesquisado = 3

for(item: conjuntoDeNumeros) {
  if(item == numeroPesquisado) return true
}

return false
```

Nesse caso, escrevemos o **for** com apenas **uma** **instrução**, o que funciona como um atalho. Nesse caso o **for** está criando uma variável **item** com cada elemento presente dentro de **conjuntoDeNumeros** e usando esse valor dentro do corpo da instrução, exatamente como no caso anterior, só que com menos código escrito. Existem algumas outras formas de escrever um for que não cobriremos aqui, já que são formas específicas de cada linguagem de programação.



 ## While

**While** é uma estrutura de repetição que é aplicada enquanto uma **condição for verdadeira**. Muito usada para controle de threads ou aplicações que devem se manter rodando até que algo indique que o processo deve parar de ser executado. Também pode ser usado para percorrer elementos de conjunto, mas o **for** tende a ser um recurso melhor para esse tipo de trabalho. Exemplo de construção do while:

```
quantidade = 0

while(quantidade < 10) {
 quantidade = quantidade + 1
}

```

No exemplo acima, somaremos 1 ao valor de quantidade até que o valor de quantidade seja 10. Quando quantidade tiver o valor de 10 o loop será quebrado. Assim como no for, break e return também pode sem usados para interromper o loop.

O while pode ser escrito de mais uma maneira, usando o auxiliar do:

```
quantidade = 0

do {
 quantidade = quantidade + 1
} while (quantidade < 10)
```

O que muda neste caso, é que a **condição** **é checada após a execução da ação dentro do loop**. Muito importante se ater a isso, porque o while escrito dessa forma **sempre executará a primeira iteração**, **mesmo que a condição do while seja falsa**.



 ## Recursão

A recursão é uma técnica para se gerar um loop utilizando chamadas recorrentes de uma mesma função, ou seja, chamamos uma função dentro dela mesmo até que o resultado seja alcançado.

Vou usar aqui o clássico exemplo de calcular o fatorial de um número, lembrando que fatorial é a operação de se multiplicar o valor atual pelo próximo número consecutivo abaixo dele, de forma recorrente até o número 1

```

function fatorial(valor) {
    if (n == 0) {
        return 1
    } 
    
    return (valor * fatorial(valor - 1)) 
}

```



Para ficar um pouco mais fácil de enxergar, esse seria o ciclo do processamento do fatorial de 3:

```
fatorial(3) =
-  3 * fatorial(2) =
-    2 * fatorial(1) =
-      1 * fatorial (0) = 1 
-        => Quando a função retorna 1, ela não chamará ela mesma novamente, e nesse ponto as funções anteriores          -          começam a retornar os cálculos:
-      1 * 1 = 1
-    2 * 1 = 2
-  3 * 2 = 6

logo fatorial(3) = 6
```



**Importante:** recursão gera uma **pilha de chamadas de função** (muito parecido com o que acontece no bloco de exemplo anterior), que mantém o estado da função que chamou a função atual e consequentemente consome memória. Diferente de um loop como while e for, a recursão tem um **limite de vezes** que ela pode ser executada até chegar ao **limite de empilhamento** possível. Quando isso acontece, ocorre o famoso "**estouro de pilha**" ou "**stack overflow**".
