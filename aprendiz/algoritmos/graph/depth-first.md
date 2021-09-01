# Busca em profundidade
A busca em profundidade percorre os elementos da árvore “de cima para baixo” (ou “de baixo para cima”), em sequências de profundidade crescente ou decrescente. Quando um elemento da árvore é acessado e termina de ser avaliado pela busca, antes de verificar os outros elementos do mesmo nível da arvore, o algoritmo percorre os elementos de profundidade mais baixa ou mais alta. Este “mergulho” nos níveis da árvore (que normalmente acontece várias vezes em uma busca) termina quando, em uma de suas chamadas recursivas, a função atinge uma extremidade da árvore.

A função recursiva de busca deve desempenhar o seguinte processo:

1 — Obter o elemento recebido como argumento

2 — Verificar se o elemento obtido é o elemento procurado:

-   **Caso seja**, o escopo corrente da função recursiva deve retornar este elemento
-   **Caso não seja**, o processo continua

3 — Obter os elementos adjacentes do elemento recebido como argumento

4 — Para cada um dos elementos adjacentes, fazer uma chamada recursiva passando o respectivo elemento como argumento

5 — Verificar se alguma das chamadas recursivas retornou o elemento procurado:

-   **Se sim**, o escopo corrente da função recursiva deve retornar este elemento
-   **Se não**, o escopo corrente da função recursiva deve retornar um dado que indique que o elemento buscado não foi encontrado.

No entanto, se esta técnica for aplicada a um grafo que contenha ciclos, a recursão entrará em uma cadeia de acessos repetidos a determinados objetos da estrutura e, por fim, acontecerá uma falha conhecida como **estouro de pilha** (_“stack overflow”_, em inglês). É necessário, nestes casos, usar algum artifício para “marcar” os objetos que já foram acessados durante a busca, para que o algoritmo não verifique um objeto mais de uma vez durante a busca.
