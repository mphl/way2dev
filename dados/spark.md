# Apache Spark

[Apache Spark](https://spark.apache.org/) é uma ferramenta para processar dados em larga escala.

Você pode estar se perguntando o que é "larga escala" ou quando você precisa usar o Spark. A resposta é simples: se a quantidade de dados que você quer trabalhar não cabe na memória de apenas um computador, você precisa de uma ferramenta que distribua esse processamento em várias máquinas e consiga orquestrar esse processo, então você precisa do Spark. 

O Spark considera que um conjuto de dados é um *Dataset*. Esses dados podem ser de qualquer tipo, inclusive classes definidas pelos usuários.

Para trabalhar com os *Datasets* o Spark criou uma abstração chamada RDD (Reslient Distrubuted Datasets), desta forma toda a complexidade da computação distribuída fica escondida e você executa comandos como se todos os dados estivessem juntos.

Considerações importantes sobre RDDs:
- são distribuídos. Desta forma é possível rodar em partições diferentes dentro do cluster.
- são imutáveis. Assim são evitados os problemas de programação concorrente.
- são resilientes. Possibilitando serem recriados a qualquer momento, sendo tolerante a falhas.

Portanto, utilizando o Spark todo o trabalho é definido criando um RDD, transformando um RDD e chamando operações e computando resultados. Abaixo vou explicar algumas funções básicas, mas para se aprofundar mais essa [documentação](https://spark.apache.org/docs/latest/rdd-programming-guide.html) pode te ajudar.

### Transformações
São funções aplicadas em um RDD que resulta em um novo RDD.
Exemplos:
- **Filter**: retorna um RDD formado pelos elementos que passam na função de filtragem.
- **Map**: passa cada elemento do RDD de entrada através de uma função, o resultado dessa função é adicionado no RDD de saída.
- **Flatmap**: funciona da mesma forma que o *Map*, porém cada elemento do RDD de entrada pode gerar mais de um elemento no RDD de saída.

### Operações
Recebem um ou dois RDDs como entrada e retornam um RDD de saída
Exemplos:
- **Sample**: retorna um subgrupo do RDD de entrada. Útil para testes.
- **Distinct**: retorna elementos distintos no RDD de entrada. Essa operação é bem custosa para ser executada.
- **Union**: retorna a união dos elementos de dois RDDs. Se tiver elemntos repetidos, eles serão duplicados.
- **Intersection**: retorna elementos comuns de dois RDDs. Lembre-se que se tiver elemntos repetidos dentro de um RDD, eles serão deduplicados.
- **Subtract**: retorna os elementos que existem no primeiro RDD e não existe no segundo.
- **Cartesian product** retorna todos os pares possíveis de elementos entre os dois RDDs.

### Ações
Computam o resultado baseado no RDD.
Exemplos:
- **First**: retorna o primeiro elemento de um RDD.
- **Collect**: retorna a coleção inteira ou o valor para o programa executando os RDDs. Atenção pois todos o *Dataset* deve caber na memória de apenas uma máquina.
- **Count e CountByValue**: *count* vai retornar a quantidade de elementos no *Dataset* e o *CountByValue* vai contar a quantidade de vezes que um elemento aparece no *Dataset*.
- **take**: retorna N elementos de um *Dataset*.
- **reduce**: passa todos os elementos de um *Dataset*, de dois em dois, numa função de *reduce*. Exemplo se seu *Dataset* é [1,2,3,4,5] e a função de reduce for "X*Y" então o resultado será 120. 
- **SaveAsTextFile**: usado para escrever dados em um sistema de armazenamento distribuído como Amazon S3, HDFS ou até no seu sistema de arquivo local.

### Bônus: Persistência
Algumas vezes vamos precisar chamar ações no mesmo RDD múltiplas vezes. Se você fizer isso de forma ingênua, os RDDs e todas suas dependências serão recomputados cada vez que uma ação for chamada num RDD. Se você for reutilizar um RDD, você deve persistir chamando o método **persist()** no seu RDD. Isso vai manter os dados na memória e todos os nós do cluster. Existem diferentes níveis para você persistir os dados levando em consideração se será utilizada a memória e/ou o disco e se os dados serão serializados ou não.


## Conclusão
Até aqui você aprendeu conceitos básicos do Spark para trabalhar com um grande volume de dados. Mas ele consegue ser ainda mais poderoso, sendo possível adicionar libs de *Machine Learning* ([MLlib](https://spark.apache.org/docs/latest/ml-guide.html)), libs para trabalhar com gráfos ([GraphX](https://spark.apache.org/docs/latest/graphx-programming-guide.html)), escrever sus consultas e agregações no formato SQL ([SparkSQL](https://spark.apache.org/docs/latest/sql-programming-guide.html)) e ainda trabalhar com streaming de dados!

Sobre esse último ponto, existe o [Spark Streaming também conhecido como DStreams](https://spark.apache.org/docs/latest/streaming-programming-guide.html) e o [Structured Streaming Programming](https://spark.apache.org/docs/latest/structured-streaming-programming-guide.html). Eu fiquei bem confuso para entender a diferença dos dois olhando apenas na documentação oficial, mas esse [link aqui](https://blog.knoldus.com/spark-streaming-vs-structured-streaming/) explica bem a diferença deles. Em resumo, o Structured Streaming Programming é mais recomendado para você que esta utilizando streamings de verdade, o DStreams é mais para rodar jobs periódicos.

Gostou de Spark?! Quer colocar em prática?! A [documentação oficial](https://spark.apache.org/docs/latest/quick-start.html) é bem completa e fácil de seguir. Basta escolher a sua linguagém de programação favorita, seguir o tutorial e ser feliz 🙂.
