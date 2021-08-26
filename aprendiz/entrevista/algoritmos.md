
# Algoritmos
Ser capaz de pensar, codificar e comunicar simultaneamente pode parecer uma façanha impossível, mas é possível com prática.


Um dos melhores livros para aprender todo conteúdo relacionado a algoritmos é o [Cracking the Coding Interview](http://www.crackingthecodinginterview.com/), mas se você é um aprendiz que prefere aprender fazendo, uma dica é utilizar de algum destes sites com exercícios [LeetCode](https://leetcode.com/) , [HackerRank](https://www.hackerrank.com/) e [CodeForces](http://codeforces.com/).

Para se manter sempre afiado neste assunto, a dica é se inscrever no site https://www.dailycodingproblem.com/ assim todos os dias você vai receber um email com um exercício para resolver. 

Sem mais delongas, segue dicas valiosas para sua entrevista de algoritmos:
  
Escute o entrevistador, ele sempre vai te dar boas dicas, se ele esta entrevistando é porque precisa de alguém, ele esta ali para te passar e não reprovar.
- Se comunique com o entrevistador o tempo todo.
- Se certifique de que tenha entendido o problema, valide com o entrevistador o que você pretende resolver.

Considere fazer as seguintes perguntas:
-   Quão grande é o tamanho da entrada? Como vou receber esses dados?
-   Que tipos de valores existem? Preciso validar as entradas ? Existem números negativos? Pontos flutuantes?
-   Existem valores duplicados dentro da entrada?
-   Quais são alguns dos casos extremos da entrada?

Antes de codificar, faça uma explicação em alto nível da solução, isso garante que o entrevistador saiba sua linha de raciocínio pra te ajudar e guiar na solução. 

Neste ponto, justifique sua motivação de resolver o problema desta forma. Quando você for codificar, terá que pensar apenas  na linguagem de programação, pois o entrevistador não vai precisar interromper sua linha de raciocínio para entender porque você esta desenvolvendo daquela forma.

- Faça primeiro uma Solução trivial

Dica: adie as implementações “helpers”… faça o seu método de validação depois, isso mostra um clean code, facilidade em abstração e ajuda a ganhar tempo. 

De um exemplo simples para resolver o problema, não comece pensando em muitos corner cases, mas também não se limite ao caminho feliz. Desta forma, execute seu código em voz alta fazendo anotações dos valores gerados. Isso vai fazer você encontrar possíveis problemas de execução. 

Assim que terminar o trivial pense no que pode ser diferente para entregar mais performance (tanto de tempo quanto de espaço). Pense em problemas relacionados que você viu antes e como eles foram resolvidos.

Para você conseguir otimizar a sua solução, parta do principio da complexidade atual do seu exercício. Exemplo se sua solução trivial teve a complexidade O(nˆ2) então pense em uma O(n) ou O(n*log n ), mas se sua solução já foi O(n) então pense em uma solução O(log n) ou O(1). Muitas vezes a única forma de melhorar a performance de tempo é aumentando a complexidade de espaço. Avalie essa escolha e mostre para seu entrevistador a troca de complexidade, que isso depende da quantidade de dados que você vai precisar processar (tenho certeza que ele vai achar incrível você fazer essa avaliação).

Dicas de otimização de algoritmos:
Lembre-se das estruturas de dados e qual pode resolver o seu problema da melhor forma, por exemplo buscar um elemento por valor num conjunto é mais performático que buscar num array, porém buscar elementos por posição é melhor no array do que no conjunto.

Lembre-se que pré processar os dados pode gerar uma melhor performance do que iterar pelos elementos processando. Ou seja, fazer um looping depois do outro é mais performático que um looping dentro de outro.

Caso a ordem dos elementos não tenha importância, ordenar para buscar um elemento pode ser  uma boa escolha para evitar uma busca sequencial.

Lembre-se que você não precisa resolver o exercício com apenas uma estrutura de dados, as vezes você vai precisar de duas para conseguir a melhor performance de tempo, mesmo dobrando o espaço. Um exemplo clássico é a implementação de um [cache LRU](https://www.geeksforgeeks.org/lru-cache-implementation/).

E por último, caso seu algoritmo seja complexo, apenas estruturas de dados não vão te ajudar, então pense nas técnicas avançadas como greedy, backtracking, divisão e conquista ou programação dinâmica.
