# Controle de versão (Git)
Imagine que você queira escrever um livro e esteja utilizando um caderno para isso. Já pensou se esse caderno molhar e estragar tudo ? E se você escreveu um capítulo que não gostou e acabou jogando fora as folhas, mas depois de um tempo, achou que poderia encaixar aquele capítulo novamente na história e teria que reescrever tudo de novo? Para evitar problemas como esses, foram criados sistemas para controlar as alterações de um documento, onde cada alteração gera uma nova versão. Desta forma, você poderia recuperar documentos com facilidade apenas apontando para uma versão anterior.

Esses sistemas para controlar as versões são chamados de SCM (do inglês, Source Code Management) e apesar de existirem diversas ferramentas gratuitas e pagas que os implementam, nós vamos focar no Git, por ser a ferramenta mais utilizada para esse propósito em grandes empresas e até mesmo a recomendada para você armazenar seus projetos pessoais.

A tarefa de escrever programas basicamente consiste em criar um arquivo, alterar seu conteúdo, salvar o arquivo, alterar o arquivo, salvar o arquivo e assim por diante até que tenha terminado. Usar uma ferramenta de controle de versão para esse cenário já daria a vantagem de você conseguir voltar facilmente a uma versão anterior. Mas na vida real, provavelmente você vai trabalhar com várias pessoas alterando o mesmo código de forma paralela, então usando o Git, você tem a vantagem dele mostrar a diferença entre as duas versões, quando foi feita a alteração, mostrar quem fez a alteração (caso você tenha alguma dúvida, já sabe para quem perguntar) e ainda é possível fazer um comentário do porque a alteração foi feita.

Falando em colaboração no desenvolvimento, você deve estar pensando como uma ferramenta que está no seu computador vai conseguir comparar o que seu amigo fez no computador dele. O git trabalha de forma local (sua máquina) e remota (utilizando um servidor). Para a parte remota, você precisa utilizar alguma plataforma para hospedar o código. Dessa forma, sempre que você terminar sua alteração local você pode enviar para o servidor, assim seu amigo pode baixar a alteração do servidor e dar continuidade no código. Tudo isso facilitado pelas vantagens de Git para controlar as alterações.

[Siga por esse caminho para configurar o Git do seu computador.](config)

[Esse é o atalho para que já tem o Git e quer saber apenas os comandos do dia a dia.](diadia)

[Dicas e truques](dicas)

[Gitflow](gitflow)

[Git hooks](hooks)

Espero que você tenha aprendido o básico aqui, mas se tiver gostado e quiser aprender mais, siga o link para a [documentação oficial](https://git-scm.com/doc) onde você vai encontrar o manual de referências, vídeos, livros, etc.
Um ótimo local para ficar fera em git é realizando esse [tutorial](https://www.atlassian.com/git/tutorials) da Atlassian.

## Checkpoint
<details><summary>Qual a diferença de Git e Github?</summary>
<p>Git é a ferramenta para controlar as diferentes versões de um arquivo, já o Github é a plataforma para hospedagem de documentos que utiliza os conceitos do Git de forma remota em um servidor.</p>
</details>  
<details><summary>Qual a diferença do comando pull e merge?</summary>
<p>Os dois comandos trazem as alterações remotas para sua máquina, mas o pull vai dar erro se você tiver alterações localmente, nesse caso, será necessário realizar um merge das alterações.</p>
</details>  
<details><summary>Qual a diferença de um commit para um stash?</summary>
<p>O stash salva suas alterações em uma pilha de mudanças temporária enquanto o commit gera um hash de alteração que pode ser utilizado com outros comandos do git.</p>
</details>  

- git checkout "[Algoritmos](../algoritmos/algoritmos)"
