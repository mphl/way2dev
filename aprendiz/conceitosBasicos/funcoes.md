# Funções

Funções, em algumas linguagens chamadas de *métodos* , são usadas para descrever uma <u>ação reusável</u>. Lembra das funções de matemática, como f(x) = x + 1? Essa função sempre soma 1 ao valor atribuído a x:

```
f(1) = 2
f(2) = 3
f(3) = 4
...
```

Uma função de programação tem um objetivo muito semelhante: Assim que uma função tem uma ação definida, podemos chamar essa função para <u>executar uma determinada *regra* sempre que necessário</u>. Um exemplo de uma função em programação:

```
function calcularQuadradoDe(valor) {
  return valor * valor; // O símbolo (*) é usado como operador de multiplicação em várias linguagens de programação.
}
```

Assim como a função matemática do exemplo anterior, posso usar a função de `calcularQuadradoDe(valor)` sempre que houver necessidade na regra de negócio. Junto das definições de variáveis, poderíamos usar algo como:

```
quadradoDe2 = calcularQuadradoDe(2); // quadradoDe2 receberá o valor 4
quadradoDe5 = calcularQuadradoDe(5); quadradoDe5 receberá o valor 25
```

Um detalhe importante é a palavrinha mágica `return`. Nesse exemplo ela indica que a função devolve um valor após a sua execução. A palavra `return` é comum em diversas linguagens de programação, mas nem sempre a mesma é necessária, dependendo muito dos recursos da linguagem que você usa.

O ponto importante de ter em mente aqui é que <u>uma função pode ou não retornar um valor após a sua execução</u>. Se ela retornar um valor, você pode atribuí-lo a uma variável como no exemplo de calculoDeQuadrado.
Caso contrário não existe nada a ser atribuído a variável e o código pode apresentar um erro ou gerar um valor nulo em sua variável dependendo da linguagem de programação.

Funções que não retornam dados estão mais relacionadas à <u>alteração de estado em Objetos</u> ou ações de iteração direta, como exibir uma mensagem na tela. Alterações de estado em objetos será comentado [aqui](classesObjetos.md).



 ## Funções anônimas

Funções anônimas são como qualquer outra função, com uma diferença importante: elas não possuem nome. "Tá, e no que isso implica?" você pode se perguntar. O que acontece, é que esse tipo de função tem alguns poderes especiais, mas também pode trazer consequências na aplicação.

Uma função anônima é usada como se fosse um valor de uma variável. **Não é o resultado da função que é armazenado em uma variável, é todo o corpo da função**. Funções anônimas são normalmente usadas para auxiliar no comportamento de outra função, ou usadas em um contexto muito específico, no qual não faria sentido o reuso em outros lugares do código.

Vou usar como exemplo a função `map`. A função `map` é usada em diversas linguagens, e tem como objetivo trabalhar cada elemento de um conjunto gerando um outro conjunto (caso tenha curiosidade, mais informações podem ser lídas na [wikipedia](https://en.wikipedia.org/wiki/Map_(higher-order_function))). Esse trabalho a ser realizado para gerar um novo conjunto é comumente feito através de uma função anônima. Exemplo:

```
conjuntoDeMaçãsVerdes = conjuntoDeMaçãsVermelhas.map(
 (maçãVermelha) => pintarMaçãDeVerde(maçãVermelha)
)
```

Talvez um pouco de informação demais no exemplo acima, mas o importante é notar que `(maçãVermelha) => pintarMaçãDeVerde(maçãVermelha)` é a nossa *função anônima*. Você deve ter notado que a gente não deu um nome para essa função. Nós a enviamos diretamente como um valor para a função `map`, e não conseguimos chamá-la posteriormente, já que nem atribuímos essa função a uma variável. O código acima poderia ser escrito sem usar uma função anônima da seguinte maneira:

```
function transformarMaçã(maçãVermelha){
	return pintarMaçãDeVerde(maçãVermelha);
} 

conjuntoDeMçãsVerdes = conjuntoDeMaçãsVermelhas.map(transformarMaçã);
```

Esse código e o exemplo anterior fazem exatamente a mesma coisa, mas usando a função anônima eu declaro a função diretamente como um valor, já usando uma função comum (nomeada), eu passo diretamente o nome da função, mas *sem usar os parênteses* já que a intenção é passar a função em si e não o valor de uma possível execução dela.
Nem toda linguagem de programação tem suporte a funções anônimas, já que é possível trabalhar sem as mesmas, mas elas ajudam muito no dinamismo de soluções. Outras linguagens não permitem a passagem de uma função nomeada como um valor, sendo obrigatório o uso de uma função anônima em cenários como o exposto acima.

O uso de funções anônimas permite que uma regra não fique disponível para uso fora do contexto apropriado (já que fora de contexto a função poderia ter resultado adverso), além de facilitar a implementação de alguns padrões de projeto que veremos no futuro. No entanto é importante ter em mente que elas podem causar **aumento no consumo de memória** em algumas linguagens, então fique sempre atento às boas práticas de utilização da liguagem de programação que você escolher.