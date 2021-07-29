# Divisão e conquista (divide and conquer)

A estratégia deste tipo de exercício é dividir um problema grande em problemas menores para que possam ser resolvidos em tempo menor que tentando resolver o problema grande.

**Divisão**: resolver recursivamente problemas pequenos (até o caso base).
**Conquista**: solução do problema original é formada com as soluções dos subproblemas

Divisão em subproblemas de dimensão semelhante é importante para se obter uma boa eficiência temporal

É uma ótima solução para algoritmos que se beneficiam de processamento paralelo.

**Algoritmo abstrato**

    function DAQ(x){
	    if (x é suficientemente pequeno){
			resolver x diretamente
		}else{
		    dividir x em subproblemas: x1,…, xk
		    for (i := 1 to k){
			    yi := DAQ( xi )
		    }
		    y := Σ yi
		    return y
		}
	}

## Utilização

 - Algoritmos de ordenação como MergeSort e QuickSort.
 - Algoritmos de busca como Busca Binária.

Exemplo de algoritmo otimizando tempo:
Realizar o cálculo de Xˆn com a complexidade de O(log n)

    double potencia(double x, int n) {
	    if (n == 0) return 1;
	    if (n == 1) return x;
	    
	    double p = potencia(x, n / 2);
	    
	    if (n % 2 == 0){
		    return p * p;
	    }else{
		    return x * p * p;
	    }
    }
