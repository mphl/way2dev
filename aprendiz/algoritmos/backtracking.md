
# Algoritmos de retrocesso (backtracking)

Basicamente é um algoritmo que funciona com tentativa e erro.

Um dado problema tem um conjunto de restrições e possivelmente uma função objectivo
Uma solução optimiza a função objectivo e/ou a satisfaz

Pode-se representar o espaço de solução para o problema utilizando problema utilizando-se uma árvore de espaço de espaço de estados
- A raiz da árvore representa 0 escolhas
- Nós ao nível 1 representam a primeira escolha
- Nós ao nível 2 representam a segunda escolha, etc…

O caminho da raiz a uma folha representa uma solução candidata.

Definição: chama-se a um nó “não promissor”  caso este não conduza a uma solução viável (ou ótima). Caso contrário, este será tido como um nó “promissor”.

Ideia básica:  retrocesso consiste em realizar uma pesquisa em profundidade na árvore de espaço de estados, verificando se um nó é promissor, e caso o nó não seja promissor, retroceder até o nó pai.

**Estratégia**
- Ao chegar a um ponto de escolha (c/ vários estados seguintes), escolher uma das opções e prosseguir a exploração.
- Chegando a um “beco sem saída”, retroceder até ao ponto de escolha mais próximo com alternativas para explorar, e tentar outra alternativa.


**Exemplos**: Problema do troco quando há falta de estoque de algumas cédula, Sudoku, 8 rainhas, puzzles em geral.


### Problema do troco
No tópico de [algoritmos gananciosos](greedy) descobrimos como resolver o problema do troco e que nem sempre ele funciona. Para resolver, a solução é um algoritmo de retrocesso conforme vamos ver a seguir.

Dado que você tem as seguintes cédulas disponíveis no caixa {2,2,2,2,5}, como dar o troco de 8 reais com o menor número possível de notas?

**Resolução**
Executar os mesmos passos do algoritmo ganancioso, mas quando ele falhar, retroceder até ao ponto de escolha mais próximo e escolher a cédula de valor mais baixo a seguir em frente.

calculaTroco(8, {2, 2, 2, 2, 5 } ) -> retirando 5, totalizando 5
calculaTroco(3, {2, 2, 2, 2} ) -> retirando 2, totalizando 7
calculaTroco(1, {2, 2, 2} ) -> nenhuma cédula satisfaz a condição
(Falha - Retrocesso)
calculaTroco(6, {2, 2, 2} ) - > retirando 2, totalizando 2
calculaTroco(4, {2, 2} ) -> retirando 2, totalizando 4
calculaTroco(2, {2} ) -> retirando 2, totalizando 6
calculaTroco(0, {} ) -> retirando 2, totalizando 8
(Sucesso - Fim)

**Implementação**
Para executar o exemplo de cima, chamar o código abaixo da seguinte forma `calculaTroco(8,[0,3,1,0,0,0,0,0])
```
static final int cedulasPossiveis[] = {1,2,5,10,20,50,100,200};

// stock[i] = nº de cedulas de valor cedulasPossiveis[i] 
public int[] calculaTroco(int total, int[] stock) { 
	int[] troco = new int[cedulas.length]; 
	return  calcula(total,caixa,troco,cedulasPossiveis.length-1)? troco:null; 
}

boolean calcula(int total, int[] caixa, int[] troco, int maxIdx) {
	if (mont == 0){
		return true;
	} 
	for (int i = maxIdx; i >= 0; i--){
		if (caixa[i] > troco[i] && cedulas[i] <= total) { 
			troco[i]++; 
			total -= cedulasPossiveis[i]; 
		}
		if (calcula(total, caixa, troco, maxIdx)){
			return true; 
		}
		troco[i]--; 
		total += cedulasPossiveis[i]; 
	}
	return false; 
}
```

Aprendemos até aqui que algoritmos de retrocesso encontram a solução, mas muitas vezes na força bruta. Para melhorar a performance desses algoritmos, chegaram os [algoritmos de programação dinâmica](dynamicprogramming).
