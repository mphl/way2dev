# A* (pronúncia *"A estrela"*)
O algoritmo de  _Dijkstra_  é bastante custoso e pode não ser uma solução viável em algumas situações por conta do tempo que ele leva para dar uma resposta. Uma alternativa menos custosa ao algoritmo de  _Dijkstra_  é o algoritmo  **A***. Este algoritmo se assemelha muito ao algoritmo de  _Dijkstra._  A diferênça do algoritmo  **A***  para o algoritmo de  _Dijkstra_  está no fato de que o algoritmo  **A***  usa uma  **heurística**  para otimizar o processo de busca pelo menor caminho. Esta  **heurística**  é basicamente uma estimativa da distância de um vértice  **_V_** qualquer do grafo para o vértice final  **_Vf_**. No algoritmo  **A***, a chave dos vértices na fila são calculadas como a soma da distância exata para  **_Vi_**  com a distância heurística para  **_Vf_**. Consequentemente, o algoritmo sempre obterá para análise os vértices que provavelmente estão mais próximos de  **_Vf_**  em cada iteração, e precisará analisar menos vértices do que o algoritmo de  _Dijsktra_  para encontrar o caminho mínimo entre  **_Vi_**  e  **_Vf_**.

Quanto menos errática for a heurística, menos custoso será o trabalho do algoritmo.