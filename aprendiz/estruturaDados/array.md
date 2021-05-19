# Array

O array é a estrutura de dados mais simples da computação. Basicamente, itens do mesmo tipo são armazenados em memória de forma contínua.

Quando um array é definido, uma parte da memória do computador é separada para armazenar uma quantidade específica daqueles itens, e cada posição (preenchida ou não) já tem um índice e um espaço para ser acessada facilmente. Quando você deseja adicionar um item no array, você sempre escolhe a posição que aquele item será inserido. 

Uma questão interessante é que os arrays não aumentam ou diminuem de tamanho automaticamente. Para isso, as linguagens de programação oferecem métodos ou estruturas adicionais para ajudar com essas tarefas.

O lado negativo do array é quando você precisa buscar um elemento mas não sabe em qual posição ele se encontra. Nesse caso será necessário percorrer o array inteiro procurando o elemento desejado. 


Achou a explicação técnica muito difícil ? Vamos de exemplo da vida real:

Considere que o array é uma cômoda em seu quarto. Quando você quer colocar meias, sabe que deve usar a gaveta um, quando vai guardar camisas é na gaveta dois e quando vai guardar calças é a gaveta três. O espaço para você guardar as suas roupas já está definido mesmo se você não estiver utilizando, e se você precisar de mais espaço vai precisar comprar mais uma cômoda (alocar mais espaço em memória). O fato de você colocar todas as suas roupas para lavar (o array estiver vazio), não vai vender automaticamente sua cômoda, mas sempre que você precisa de mais espaço e comprar uma cômoda nova, ela ocupa espaço no seu quarto. 
Se você sabe que todas as calças estão na terceira gaveta, então é mais fácil de achar uma calça, agora se você não sabe onde guardou um chapéu, teria que abrir todas as gavetas, uma a uma, deixando o processo de busca lento.

## Checkpoint 
<details>
<summary>Dadas as informações acima, quando devemos usar arrays para armazenar os dados?</summary>
<p>Quando a posição para acesso ao elemento é mais importante do que a busca se o elemento existe.</p>
</details>
<details>
<summary>Como selecionar um número de forma aleatória em um array?</summary>
<p>Basta escolher um número menor que o tamanho do array e acessar o elemento daquela posição. </p>
</details>
