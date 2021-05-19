# Binary Tree (árvores binárias)
Uma árvore binária funciona de forma parecida com a [LinkedList](linkedlist), com a diferença que cada elemento (nó) aponta para outros dois, um conhecido como folha esquerda e outro como folha direita. O elemento principal desta estrutura de dados é conhecido como raiz, que é o primeiro nó da árvore.

A profundidade de um nó é a distância deste nó até a raiz. Um conjunto de nós com a mesma profundidade é denominado nível da árvore. E a altura, é a maior profundidade existente na árvore.
 
Existem 3 formas de atravessar uma árvore:
- **Pré ordem**: visite a raiz, então visite a subárvore da esquerda, depois a subárvore da direita.
- **Em ordem**: visite a subárvore da esquerda, então visite a raiz, depois a subárvore da direita. 
- **Pós ordem**: visite a subárvore da esquerda, então visite a subárvore da direita, depois a raiz.
 
#### Mas quando eu vou usar isso na vida real?
As árvores são ótimas para representar hierarquia, por exemplo, representar uma árvore genealógica ou a estrutura dos trabalhadores de uma empresa. Além disso, mais pra frente você vai aprender também que essa estrutura é muito utilizada para fazer buscas, exemplo, usando uma árvore binária de busca. (vamos aprender mais pra frente nessa jornada).
 
Existem árvores que não são binárias, ou seja, que tem mais de duas folhas? Sim, meu caro aprendiz, mas tenha calma, quando você for conhecer mais sobre grafos, vamos tirar essa sua dúvida.
 
Ah, tem mais uma coisa, na verdade, existem vários tipos de árvores como: árvore AVL, árvore rubro negra, heap, árvore B, etc. Mas essas estruturas são mais avançadas e não estão no escopo básico de um aprendiz. Porém, se você estiver sedento por conhecimento, esse site tem um resumo legal de algumas delas e o Google tem conhecimento infinito :-)
 
## Checkpoint
<details>
<summary>Considerando que uma árvore binária define uma ordem dos itens, por que fazer uma busca em uma árvore binária é mais fácil do que em um array?</summary>
<p>Porque cada decisão de seguir na árvore pela direita ou esquerda já elimina um subgrupo de itens que não precisam ser verificados.</p>
</details>

	
