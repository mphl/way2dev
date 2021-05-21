# Aprendendo um pouco mais

## Permissionamento
Em um sistema Linux, cada arquivo e diretório são atribuídos direitos de acesso para o proprietário do arquivo, os membros de um grupo de usuários relacionados e todos os outros. Os direitos podem ser atribuídos para ler um arquivo, gravar um arquivo e executar um arquivo (ou seja, executar o arquivo como um programa).

Seguindo tutoriais de instalação de softwares na internet, facilmente você vai ver comandos como `su`, `sudo`, `chmode`, `chown` e `chgrp`. Basicamente todos esses comandos são utilizados para alterar o permissionamento de arquivos e diretórios. Para entender como cada comando funciona, recomendo fortemente a leitura [dessa](http://linuxcommand.org/lc3_lts0090.php) página com informações de como utilizar esses comandos.

## Controlando entrada e saída dos comandos
Até agora nós executamos comandos e olhamos seus resultados no próprio terminal. Mas é possível você escolher o destino dos dados de entrada e saída de um comando.
 
### Alterando a saída
Para redirecionar a saída para um arquivo você deve utilizar o caractere '>' na frente do seu comando e definir o nome do arquivo, conforme abaixo:

`ls > file_list.txt`

Dado que a saída do comando `ls` foi redirecionada para um arquivo, nenhum resultado vai aparecer na tela.

Todas as vezes que o comando acima for repetido, o arquivo 'file_list.txt' é sobrescrito com a saída do comando `ls`. Para adicionar os resultados no fim do arquivo utilize '>>' assim:
`ls >> file_list.txt`

### Alterando a entrada
O padrão de entrada de um comando é o digitado no terminal, mas é possível alterar a sua entrada para dados de um arquivo. Utilize o caracter '<' assim:

`sort < file_list.txt`

No exemplo acima, nós utilizamos o comando `sort` para ordernar o conteúdo do arquivo 'file_list.txt'. O resultado vai ser mostrado no terminal. Todavia, é possível alterar a saída do comando para outro arquivo, deixando o comando assim:

`sort < file_list.txt > sorted_file_list.txt`
 

## Pipeline
Pipeline é a capacidade do terminal de rodar múltiplos comandos utilizando a saída de um comando como a entrada do próximo. Exemplo:
`ls -l | less`
Neste exemplo a saída do comando `ls` alimenta o comando `less`. Ou seja, utilizando o truque `| less` todos os comandos podem ter *scroll* em sua saída no terminal.
Conectando comandos, podemos realizar tarefas realmente interessantes. Alguns exemplos pra você testar:
 
| Comando | O que faz | 
| --- | --- | 
| <code>ls -lt | head<\code> | Lista os 10 arquivos mais recentes do diretório atual. |
| <code>du | sort -nr.<\code> | Lista os diretórios e o espaço que eles utilizam no disco ordenados do maior para o menor. | 
| <code>find . -type f -print | wc -l<\code> | Lista o número total de arquivos no diretório e todos seus subdiretórios. | 

