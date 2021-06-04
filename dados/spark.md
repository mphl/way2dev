# Apache Spark

[Apache Spark](https://spark.apache.org/) é uma ferramenta para processar dados em larga escala.

Você pode estar se perguntando o que é "larga escala" ou quando você precisa usar o Spark. A resposta é simples: se a quantidade de dados que você quer trabalhar não cabe na memória de apenas um computador, você precisa de uma ferramenta que distribua esse processamento em várias máquinas e consiga orquestrar esse processo, então você precisa do Spark. 

O Spark considera que um conjuto de dados é um *Dataset*. Esses dados podem ser de qualquer tipo, inclusive classes definidas pelos usuários.

Para trabalhar com os *Datasets* o Spark criou uma abstração chamada RDD (Reslient Distrubuted Datasets), desta forma toda a complexidade da computação distribuída fica escondida e você executa comandos como se todos os dados estivessem juntos.

Considerações importantes sobre RDDs:
- são distribuídos. Desta forma é possível rodar em partições diferentes dentro do cluster.
- são imutáveis. Assim são evitados os problemans de programação concorrente.
- são resilientes. Possibilitando serem recriados a qualquer momento, sendo tolerante a falhas.

Portanto, utilizando o Spark todo o trabalho é definido criando um RDD, transformando um RDD ou chamando operações em RDD para computar um resultado. Abaixo vou explicar algumas funções básicas, mas para se aprofundar mais essa [documentação](https://spark.apache.org/docs/latest/rdd-programming-guide.html) pode te ajudar.

## Transformações
São funções aplicadas em um RDD que resulta em um novo RDD.
Exemplos:
- **Filter**: retorna um RDD formado pelos elementos que passam na função de filtragem.
- **Map**: passa cada elemento do RDD de entrada através de uma função, o resultado dessa função é adicionado no RDD de saída.
- **Flatmap**: funciona da mesma forma que o *Map*, porém cada elemento do RDD de entrada pode gerar mais de um elemento no RDD de saída.

## Operações
