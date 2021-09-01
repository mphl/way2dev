# Busca em largura
A busca em largura é uma estratégia de busca em grafos na qual, após a verificação de um elemento do grafo, todos os elementos ajacentes são obtidos e verificados. Esta estratégia não possui o mesmo problema que a busca em profundidade com relação aos grafos cíclicos, embora também apresente algumas fragilidades que serão citadas mais adiante.

O artifício utilizado para desempenhar a busca em largura é um algoritmo de  **fila**. Após o primeiro elemento do grafo ser verificado, todos os elementos adjacentes são obtidos e inseridos na fila. A execução do algoritmo prossegue em sucessivas repetições do seguinte processo:

1 — Obter (e remover da fila) o elemento que está a mais tempo na fila

2 — Verificar se o elemento obtido é o elemento procurado:

-   **Caso seja**, a sucessão de repetições é finalizada
-   **Caso não seja**, o processo continua

3 — Obter os elementos adjacentes do último elemento obtido

4 — Inserir na fila todos os elementos adjacentes obtidos

No entanto, esta implementação tem dois problemas:

1 — Caso o elemento procurado não exista no grafo, o procedimento entrará em um  _loop_  infinito, causando o travamento da aplicação.  
2 — Caso o grafo seja cíclico, possivelmente ocorrerá reinserções de objetos (que já foram verificados) na fila, o que é desnecessário e implica em desperdício de memória.

Estes dois problemas podem ser corrigidos se, na implementação da função  **buscar**, a seguinte regra for definida:

**Um objeto só pode ser inserido na fila caso:**

1 — Ele ainda não tenha sido verificado;  
2 — Ele não esteja na fila esperando para ser verificado.
