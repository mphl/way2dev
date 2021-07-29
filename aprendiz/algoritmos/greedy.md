
# Algoritmos gananciosos (greedy)

Esse tipo de algoritmo é utilizado quando é necessária uma otimização, podendo ser uma Maximização ou uma Minimização. 

A estratégia aqui é não pensar qual o mínimo ou máximo da solução completa, mas sim, pensar em otimizar um sub problema, e acreditar que a cada sub problema otimizado irá resultar na otimização global.

*Nem sempre a solução final vai ser a melhor solução, mas ela tem uma chance boa de acertar e resolver o problema de forma eficiente.*
  

### Algoritmo Abstrato

Inicialmente o conjunto de itens está vazio (i.e. conjunto solução)

A cada passo:
- Um item será adicionado ao conjunto solução, pela função de selecção
- SE o conjunto solução tornar SE o conjunto solução tornar-se inviável, ENTÃO reje se inviável, ENTÃO rejeita-se os ita se os itens em consideração (não voltando a seleccioná itens em consideração (não voltando a seleccioná-los)
- SENÃO o conjunto solução ainda é viável, ENTÃO adiciona-se os itens a serem considerados

### Exemplo de utilização

**Problema do troco**
Dado que você tem as seguintes cédulas de 1, 2 e 5= {1, 1, 1, 2, 2, 2, 2, 5, 5}  , como dar o troco de 8 reais com o menor número possível de notas?

**Resolução**
Esse é o subproblema = Escolhe-se a cédula de valor mais alto que não excede o montante em falta (pois com cédulas de valor mais alto o nº de cédulas necessário será mais baixo).
Os passos então são os seguintes:
calculaTroco(8, {1, 1, 1, 2, 2, 2, 2, 5, 5} ) -> retirando 5, totalizando 5 
calculaTroco(3, {1, 1, 1, 2, 2, 2, 2, 5} ) -> retirando 2, totalizando 7
calculaTroco(1, {1, 1, 1, 2, 2, 2, 5} ) ->  retirando 1 , totalizando 8
calculaTroco(0, {1, 1, 2, 2, 2, 5} ) -> retirando 0, Fim
  
**Implementação**

    // int caixa[] = {1, 1, 1, 2, 2, 2, 2, 5, 5}; 
    // int total = 8
    
    public int[] calculaTroco(int total, int[] caixa) {
    	List troco = new ArrayList<Integer>(); 
    	for (int i=caixa.length-1; total>0 && i>=0; i--){
    		if (caixa[i] <= total) { 
    			troco.add(caixa[i]); 
    			total -= caixa[i]; 
    		} 
	    }
	    if (total > 0){
	    	return null; 
    	}else{
	    	return troco; 
	    }
    }

### E quando o algoritmo ganancioso não funciona?
Imagina o cenário onde o caixa tem somente as seguintes notas:
calculaTroco(8, {2,2,2,2,5})
Seria possível dar o troco, mas o algoritmo acima não funciona!
Nesse caso, será necessário utilizar um [algoritmo de retrocesso.](backtracking)
