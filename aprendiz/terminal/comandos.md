# Comandos básicos

## Manual de comandos
Inicio a lista  de comandos com um altamente importante, pois explica o funcionamento dos demais, como uma folha de consulta para sintaxe de comandos. Trata-se do man page! Um exemplo de seu uso é descobrir como utilizar o comando “ls” (a ser descrito nas próximas seções), neste caso, faça `man ls` e uma janela com a descrição e exemplos do comando ls irá aparecer.   
Obs. para sair do man page, basta digitar a letra Q.

## Criar diretório
Para criar um diretório, utilizamos o comando “mkdir” passando como parâmetro principal o nome do diretório a ser criado, e caso o mesmo não deva ser criado no diretório corrente, devemos passar o caminho. Por exemplo, caso esteja em um diretório diferente de “Documents”, ex: um nível acima de “Documents” e deseja criar um diretório “meuDir” dentro de “Documents”, faça, “mkdir Documents/meuDir”.
Um parâmetro interessante de mkdir é o “-p” que permite criar um diretório dentro de outro ainda não existente, neste caso, o comando cria cada diretório iterativamente até atingir aquele desejado. Por exemplo, se está no diretório Documents e deseja criar um diretório “meuDirFilho” dentro do diretório “meuDirPai” e ambos ainda não existem, faça “mkdir -p meuDirPai/meuDirFilho”.

## Trocar diretório
Para trocar o diretório corrente, tem-se o comando “cd”. Por exemplo, para mudar para o diretório “meuDir”, faça “cd meuDir”. É possível também efetuar a troca de diretório de forma relativa, por exemplo, se na hierarquia de diretórios
Você encontra-se em “meuDir2” e quer mudar para “meuDirB”, faça “cd ../../meuDirB”.  

## Criando um arquivo
Cat > file.txt  cria o arquivo e abre para edição. Para sair, digitar crtl +c.
Cat >> file.txt adiciona conteúdo no fim do arquivo.
Cat file.txt abre o arquivo.
Cat file1.txt file2.txt > file1and2.txt
obs: Caso você precise editar o meio de um arquivo, é mais fácil você utilizar o editor de texto [vim](https://opensource.com/article/19/3/getting-started-vim).

## Listar conteúdo de diretórios
Para listar o conteúdo de um diretório, tem-se o comando “ls”, por exemplo “ls .” listará o nome de todos os arquivos/diretórios existentes no diretório corrente.
É possível parametrizar o comando ls, por exemplo, para listar diretórios contidos no corrente de forma recursiva, faça “ls -R”.
Já para detalhar informações do arquivo/diretório, faça “ls -l”.

## Apagar arquivos e diretórios
Para apagar arquivos, utilize o comando “rm”. Por exemplo, para apagar o arquivo “meuArquivo”, faça “rm meuArquivo”.
Assim como para apagar um diretório, utiliza-se o comando “rmdir”. Por exemplo, para apagar o diretório “meuDir”, faça “rmdir meuDir”.

## Visualizar o caminho do diretório
Para visualizar o caminho completo até o diretório corrente, faça “pwd” e com isso, será exibido na tela o caminho para o diretório onde encontra-se em  relação ao diretório raiz do atual usuário do sistema.

## Copiar arquivos 
O comando "cp" copia arquivos e diretórios. 
Para criar um novo arquivo a partir de um existente use "cp arquivo novoArquivo". Se quiser criar a cópia dentro de outro diretório, basta informar o caminho pra ele "cp arquivo diretorio/"

## Buscar arquivos
O último comando desta lista básica é um pouco mais complexo do que os anteriores, mas com um pouco de prática, torna-se fácil de ser utilizado, trata-se do “find”. Este comando irá procurar recursivamente pelo padrão do nome do arquivo informado como parâmetro.
Por exemplo, se deseja buscar o arquivo “meuArquivo.c” que, eventualmente, está em algum diretório na hierarquia do diretório corrente e deseja efetuar a busca pelo trecho do nome do arquivo, no caso “meu” em conjunto com a extensão “.c”, deste modo ignorando todos os caracteres entre estas duas palavras, faça “find . -name meu*.c” será exibido o caminho até os arquivos encontrados em relação ao diretório corrente.

## Permissionamento
Em um sistema Linux, cada arquivo e diretório são atribuídos direitos de acesso para o proprietário do arquivo, os membros de um grupo de usuários relacionados e todos os outros. Os direitos podem ser atribuídos para ler um arquivo, gravar um arquivo e executar um arquivo (ou seja, executar o arquivo como um programa).

Seguindo tutoriais de instalação de softwares na internet, facilmente você vai ver comandos como su, sudo, chmode, chown e chgrp. Basicamente todos esses comandos são utilizados para alterar o permissionamento de arquivos e diretórios. Para entender como cada comando funciona, recomendo fortemente a leitura dessa página com informações de como utilizar esses comandos.

## Controlando entrada e saída dos comandos
Até agora nós executamos comandos e olhamos seus resultados no próprio terminal. Mas é possível você escolher o destino dos dados de entrada e saída de um comando.

### Alterando a saída
Para redirecionar a saída para um arquivo você deve utilizar o caractere ">" na frente do seu comando e definir o nome do arquivo, conforme abaixo:
ls > file_list.txt
Dado que a saída do comando ls foi redirecionada para um arquivo, nenhum resultado vai aparecer na tela.
Todas as vezes que o comando acima for repetido, o arquivo file_list.txt é sobrescrito com o comando a saída do comando ls. Para adicionar os resultados no fim do arquivo utilize ">>" assim:
ls >> file_list.txt

### Alterando a entrada
O padrão de entrada de um comando é o digitado no terminal, mas é possível alterar a sua entrada para dados de um arquivo. Utilize o caracter "<" assim:
sort < file_list.txt
No exemplo acima, nós utilizamos o comando sort para ordernar o conteúdo do arquivo file_list.txt. O resultado vai ser mostrado no terminal. Todavia, é possível alterar a saída do comando para outro arquivo, deixando o comando assim:
sort < file_list.txt > sorted_file_list.txt

## Pipeline
Pipeline é a capacidade do terminal de rodar múltiplos comandos utilizando a saída de um comando como a entrada do próximo. Exemplo:
ls -l | less
Neste exemplo a saída do comando ls alimenta o comando less. Ou seja, utilizando o truque "| less" todos os comandos podem ter scroll em sua saída no terminal.
Conectando comandos, podemos realizar tarefas realmente interessantes.

