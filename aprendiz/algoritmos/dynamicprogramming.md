
# Programação dinâmica

A programação dinâmica equivale a quebrar um problema de otimização em subproblemas mais simples e **armazenar a solução para cada subproblema** de modo que cada subproblema seja resolvido apenas uma vez.

Na programação dinâmica, depois de resolver cada subproblema, você deve memorizar ou armazená-lo, esse processo chamamos de Memoização. Desta forma, tormamos o algoritmo mais eficiente por evitar recalculo.  A escolha do subproblema correto que garante que um programa dinâmico passe por todas as possibilidades para encontrar a melhor.

### Explicando a Memoização com Números de Fibonacci

Quando instruído a implementar um algoritmo que calcula o [valor de Fibonacci](https://www.mathsisfun.com/numbers/fibonacci-sequence.html) para qualquer número, o que você faria? A maioria das pessoas que conheço optaria por um algoritmo recursivo que se parece com isto em Python:

```
def Fibonacci(n):
	if n==0:
		return 0
	elif n==1:
		return 1
	else:
		return Fibonacci(n-1)+Fibonacci(n-2)
```

Este algoritmo cumpre seu propósito, mas a um custo enorme. Por exemplo, vejamos o que este algoritmo deve calcular a fim de resolver para n = 6):

![Fibonacci example](/static/fibo.png)


A árvore acima representa cada cálculo que deve ser feito para encontrar o valor de Fibonacci para n = 6. Observe como o subproblema para n = 2 é resolvido **cinco vezes**. Para um exemplo relativamente pequeno (n = 6) , isso é muita computação repetida e desperdiçada!

E se, em vez de calcular o valor de Fibonacci para n = 2 cinco vezes, criássemos um algoritmo que o calcula uma vez, armazena seu valor e acessa o valor de Fibonacci armazenado para cada ocorrência subsequente de n = 2? Isso é exatamente o que a memoização faz.

Com isso em mente, esta é a solução de programação dinâmica para o problema de valor de Fibonacci:

```
def fibonacci(n):
	fib = [0, 1]
	for i in range(2, n+1):
		fib.append(fib[i-1] + fib[i-2])
	return fib[n]
```

Observe como a solução do valor de retorno vem do array fib[], que é preenchido iterativamente pelo loop. Por "iterativamente", quero dizer que o fib[2] é calculado e armazenado antes do fib[3], fib[4],… e fib[n]. Como fib[] é preenchido nesta ordem, a solução para cada subproblema (n = 3) pode ser resolvida pelas soluções de seus subproblemas anteriores (n = 2 en = 1) porque esses valores já foram armazenados em fib[] em um momento anterior.

Memoização significa nenhum recálculo, o que torna o algoritmo mais eficiente. Assim, a memoização garante que a programação dinâmica seja eficiente, mas é a escolha do subproblema correto que garante que um programa dinâmico passe por todas as possibilidades para encontrar a melhor.

