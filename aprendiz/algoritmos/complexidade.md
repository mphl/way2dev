# Complexidade de algoritmos

Esse tópico pode ser chamado de *Complexidade* ou *Eficiência* de um algoritmo. Basicamente você quer saber, em termos comparativos, se seu algoritmo é lento ou rápido.

Essa complexidade pode ser considerada no tempo que seu algoritmo demora pra executar e no espaço de memória que ele utiliza.

Muitas pessoas se preocupam com esse tópico apenas quando estão fazendo entrevistas, mas é importante considerar a complexidade do seu algoritmo sempre. Afinal, se o seu algoritmo tiver uma complexidade alta ele pode ter problemas rodando em celulares mais simples ou ficar mais caro do que deveria rodando em servidores cobrados por tempo de execução.

Para entender esse tópico profundamente, você precisa conhecer bastante de matemática, mas como a ideia desse site é simplificar, você precisa entender que existe basicamente as seguintes complexidades (ordenadas da mais rápida para a mais lenta) da notação Big O:

### O(1) 
Nesse caso a complexidade de executar o seu algoritmo é constante, indepentemente da quantidade de elementos.

Exemplo: Para você buscar o elemento da posição X de um array é constante, pq independentemente da quantidade de elementos de um array, o computador sabe exatamente onde esta a posição 5 na memória.

### O(log n)
Conforme a quantidade de elementos aumenta, a complexidade fica um pouco maior, mas esse aumento é bem pequeno.

Exemplo: Imagina que você esta buscando um contato numa agenda. Se você sabe que o nome da pessoa começa com a letra R, você vai direto para essa página. Tudo bem que se aumentar a quantidade de pessoas com a letra R na sua agenda vai dificultar um pouco sua pesquisa, mas aumentar pessoas com a letra B não vai mudar em nada.

### O (n)
Aqui, cada elemento a mais em sua coleção gera um impacto direto na complexidade do seu algoritmo.

Exemplo: Se você tivesse que contar quantas vezes a palavra *algoritmo* apreceu nessa página você teria que percorrer todas as palavras e ver se ela é *algoritmo*, certo ? Então cada palavra que eu adicionar nesse texto vai fazer com que seu algoritmo demore um pouco mais parra rodar.

### O (n log n)
Agora, além de cada elemento começar a piorar o tempo de execução, ele ainda gera um pouco a mais lentidão.

Exemplo: Para você ordernar uma lista, você precisa passar por todos elementos (n) e trocar a posição dele para o local correto na lista (log n).

### O (n^2)
Essa situação faz com que cada elemento em sua coleção faça você ter que processar novamente todos os outros elementos.

Exemplo: Encontrar 2 números de uma lista que multiplicados dão um número X. (obs. esse algoritmo pode ser resolvido com uma solução melhor que O(nˆ2), mas sua solução mais trivial é para cada elemeneto verificar se tem outro elemento que a multiplicação de X).

Obs. Essa complexidade pode ir aumentando conforme a quantidade de vezes que você tenha que percorrer a sua lista para cada elemento. Exemplo, se for 3 vezes seria O (nˆ3) e assim por diante. 

### O (2^n)
Essa complexidade dobra a cada elemento novo na coleção.

Exemplo: Qual a complexidade de você jogar uma moeda e ter *cara* 2 vezes seguidas ? A primeira moeda pode dar cara ou coroa e a segunda cara ou coroa. Agora se você perguntar qual a probabiliade de tirar *cara* 3 vezes, teria que considerar cara/cora, cara/cora e cara/coroa. 

### O (n!)
Essa é a pior complexidade, onde você precisa considerar a combinação de todos os elementos.

Exemplo: Dado que você tem uma mochila que aguenta 20 quilos e uma coleção de objetos (cada objeto tem um peso). Qual a maior quantidade de objetos que você consegue colocar em sua bolsa ? 

