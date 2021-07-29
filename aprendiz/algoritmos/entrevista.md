# Entrevistas de emprego

Entrevistas de emprego para um desenvolvedor normalmente tem as seguintes etapas:

### Conversa com o recrutador técnico.
Nesta etapa ele pode verificar seu ingles, se você conhece alguma(s) ferramenta(s) especificas que a empresa precisa e provavelmente perguntar sobre sua carreira para entender sua senioridade.
### Algoritmos
Esta etapa visa validar seus conhecimentos dos fundamentos da programação, se você consegue resolver problemas de forma eficiente.
### Coding / Pair Programing
Esta etapa visa analisar sua capacidade de desenvolver um código limpo e claro, seguindo boas práticas. Além de analisar sua capacidade de comunicação ao dar manutenção em um código existente ou cocriação com os entrevistadores.
### Arquitetura / System Design
Desenho de uma solução de um projeto.  Pode cobrir desde a experiencia do usuário ate a estruturação em domínios e armazenamento dos dados. 
### Desenvolvimento de um projeto
Aqui a ideia é analisar o quanto você conhece uma linguagem de programação, frameworks e ferramentas.

> **Importante**: Independentemente de etapa você estiver, o entrevistador vai estar analisando sua capacidade de comunicação com ele. Portanto, sempre deixa claro suas intenções e soluções.


## Algoritmos
Ser capaz de pensar, codificar e comunicar simultaneamente pode parecer uma façanha impossível, mas é possível com pratica.

Pratique e resolva questões de algoritmo no idioma escolhido. Enquanto [Cracking the Coding Interview](http://www.crackingthecodinginterview.com/) é um bom recurso, eu prefiro resolver problemas digitando código, deixando-o funcionar e recebendo feedback instantâneo. Existem vários juízes on-line, como [LeetCode](https://leetcode.com/) , [HackerRank](https://www.hackerrank.com/) e [CodeForces](http://codeforces.com/) para que você possa fazer perguntas on-line e se acostumar com a linguagem.
  
Escute o entrevistador, ele sempre vai te dar boas dicas, ele esta ali para te passar e não reprovar.
- comunica com o seu entrevistador o tempo todo.
- certifique-se de que tenha entendido o problema.

Considere fazer as seguintes perguntas.
-   Quão grande é o tamanho da entrada?
-   Quão grande é a gama de valores?
-   Que tipos de valores existem? Existem números negativos? Pontos flutuantes? Haverá entradas vazias?
-   Existem duplicatas dentro da entrada?
-   Quais são alguns dos casos extremos da entrada?
-   Como é armazenada a entrada? Se você receber um dicionário de palavras, é uma lista de strings ou trie?

Antes de codificar, faça uma explicação em alto nível, isso garante que o entrevistador sabe sua linha de raciocínio pra te ajudar e também te ajuda a guiar na solução.

- Faça primeiro uma Solução trivial

Dica: adie as implementações “helpers”… faça o seu método de validação depois, isso mostra um clean code, facilidade em abstração e ajuda a ganhar tempo. Alem de mostrar que não faz códigos monolíticos.

De um exemplo simples para resolver o problema, nao comece pensando em muitos corner cases. Mas tb não se limite ao caminho feliz, assim que terminar o trivial pense no que pode ser diferente.

Pense em problemas relacionados que você viu antes e como eles foram resolvidos.

Modifique o problema ao quebrá-lo em problemas menores
Agora otimizar algoritmo, pense na complexidade que vc tem e como seria possível abaixar.
Lembre dos tipos de exercício
- Estruturas de dados
	- array
	- filas
	- pilhas
	- grafos
Quais são as características de inserção/exclusão/pesquisa?
- Busca
- Ordenação
- Recursão
- Algoritmos em Grafo (Menor Caminho)
- Dividir e Conquistar
- Greedy
- Programação dinamica
 
Faça testes (em voz alta ou escritos) para seu código
Código limpo e correto é mais importante que um código perfeito.

  

#### Ordenação

Existem diversos algoritmos famosos de ordenação como BubbleSort, MergeSorte e QuickSort. Aprender como esses algoritmos funcionam pode ser interessante se você quiser ser mestre nesse assunto (recomendo que você ao menos de uma olhadinha nesse [site](https://www.toptal.com/developers/sorting-algorithms) para conhecer um pouco mais deles, e o melhor de tudo, você pode ver um comparativo deles de forma visual).  Mas na vida real, as linguagens de programação que utilizamos já tem uma biblioteca que faz a ordenação pra gente apenas usando um comando `sort`. Portanto, saber utilizar esse comendo para resolver problemas é de suma importância, pois nem sempre a solução esperada é uma ordenação crescente ou decrescente.

Exemplo de exercício:

1) Retornar um array com números em forma de onda, onde deve ser apresentado um numero, depois um maior, depois um menor , depois um maior e assim por diante.

Fácil! Ordenar o array e retornar a primeiro, depois o ultimo, e ir internado no começo e do fim ate os ponteiros se cruzarem.
Lição de casa:
1) Qual a complexidade do algoritmo acima ?
2) Fazer um algoritmo que tenha uma performance melhor.

#### Busca

Muitos algoritmos pedem para você buscar algum elemento (ex. numero em um array) ou algum padrão (sequencia de letras em uma string). A forma mais simples é ir iterando por todos elementos até achar o que você precisa, mas normalmente essa não é a solução com melhor performance.  Lembre-se sempre que buscar um elemento utilizando busca binária é mais performático do que iterar por todos os números (porém o conjunto precisa estar ordenado, o que já requer consumo computacional). Uma outra abordagem que costuma ajudar é utilizar mais de um ponteiro ao percorrer um conjunto. Exemplo:

Informar o Nth elemento antes do fim de uma lista ligada.

A solução mais simples seria percorrer a lista ligada ate o fim, descobrir quantos elementos ela tem, subtrair o numero passado no enunciado e percorrer novamente para achar o elemento. Todavia, você precisou percorrer a lista duas vezes. Para fazer isso somente uma vez, comece a percorrer a lista, quando der o numero do anunciado voce começa um novo ponteiro, quando o ponteiro da frente chegar o fim, o ponteiro de traz vai estar apontando para o elemento requisitado.

#### Algoritmos de Strings
