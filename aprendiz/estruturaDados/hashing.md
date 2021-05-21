# Hashing
Alguns nomes conhecidos para a estrutura de dados que utilizam hashing são hash table e hash map, ou talvez esses nomes sejam totalmente desconhecidos para você, mas não se preocupe você vai entender já já como ela funciona.

Imagina que você chega numa livraria e gostaria de saber se eles tem livros de culinária, procurar um a um levaria muito tempo, mas se você soubesse que os livros de culinária  estivessem na prateleira azul à sua esquerda, seria muito mais fácil. 
Isso quer dizer que necessariamente vai ter o livro que você quer ler ? Não.
Isso quer dizer que vai ter somente um livro de culinária ? Não.
Agora se você chegar na livraria e perguntar se eles tem livros de culinária e eles responderem que não, você nem precisa gastar tempo procurando o livro que deseja.

Exatamente dessa forma que funciona o Hashing. Você pode criar uma função hash que dado o tema de um livro essa função retorna a prateleira que ela se encontra. Então a sua estrutura de dados guardaria em suas chaves os temas e em seus valores as prateleiras correspondentes.

Idealmente, cada chave representa somente um valor, dessa forma é muito rápido achar o que está procurando. Porém, criar chaves com essa precisão às vezes é uma tarefa muito complexa, então quando uma mesma chave encontra mais de um valor, essa situação é chamada de colisão, e procurar o item dentro dos valores é uma tarefa mais demorada. 

## Checkpoint
<details>
<summary>Quando é melhor usar uma estrutura de Hashing do que um array?</summary>
<p>Quando saber se um elemento existe é mais importante do que saber a ordem dos itens.
</p>
</details>
