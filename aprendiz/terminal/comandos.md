# Comandos básicos

## Manual de comandos
Inicio a lista  de comandos com um altamente importante, pois explica o funcionamento dos demais. Trata-se do *man page*! Um exemplo de seu uso é descobrir como utilizar o comando `ls` (vou falar dele daqui a pouco), neste caso, faça `man ls` e uma janela com a descrição e exemplos do comando `ls` irá aparecer.   

Obs. Para sair do man page, basta digitar a letra 'Q'.

## Criar diretório
Para criar um diretório, utilizamos o comando `mkdir` passando como parâmetro principal o nome do diretório a ser criado, e caso o mesmo não deva ser criado no diretório corrente, devemos passar o caminho. Por exemplo, caso esteja em um diretório diferente de 'Documents', ex: um nível acima de 'Documents' e deseja criar um diretório 'meuDir' dentro de 'Documents', faça, `mkdir Documents/meuDir`.

Um parâmetro interessante de `mkdir` é o `-p` que permite criar um diretório dentro de outro ainda não existente, neste caso, o comando cria cada diretório iterativamente até atingir aquele desejado. Por exemplo, se está no diretório 'Documents' e deseja criar um diretório 'meuDirFilho' dentro do diretório 'meuDirPai' e ambos ainda não existem, faça `mkdir -p meuDirPai/meuDirFilho`.

## Trocar diretório
Para trocar o diretório corrente, tem-se o comando `cd`. Por exemplo, para mudar para o diretório 'meuDir', faça `cd meuDir`. É possível também efetuar a troca de diretório de forma relativa, por exemplo, se na hierarquia de diretórios

Você encontra-se em 'meuDir2' e quer mudar para 'meuDirB', faça `cd ../../meuDirB`.  

## Criando um arquivo
- `Cat > file.txt`  cria o arquivo e abre para edição. Para sair, digitar 'crtl +c'.
- `Cat >> file.txt` adiciona conteúdo no fim do arquivo.
- `Cat file.txt` abre o arquivo.
- `Cat file1.txt file2.txt > file1and2.txt` cria um arquivo chamado 'file1and2.txt' com o conteúdo dos 2 arquivos.


obs: Caso você precise editar o meio de um arquivo, é mais fácil você utilizar o editor de texto [vim](https://opensource.com/article/19/3/getting-started-vim).

## Listar conteúdo de diretórios
Para listar o conteúdo de um diretório, tem-se o comando 'ls', por exemplo `ls .` listará o nome de todos os arquivos/diretórios existentes no diretório corrente.

É possível parametrizar o comando `ls`, por exemplo, para listar diretórios contidos no diretório corrente de forma recursiva, faça `ls -R`.

Já para detalhar informações do arquivo/diretório, faça `ls -l`.

## Apagar arquivos e diretórios
Para apagar arquivos, utilize o comando `rm`. Por exemplo, para apagar o arquivo 'meuArquivo', faça `rm meuArquivo`.

Assim como para apagar um diretório, utiliza-se o comando `rmdir`. Por exemplo, para apagar o diretório 'meuDir', faça `rmdir meuDir`.

## Visualizar o caminho do diretório
Para visualizar o caminho completo até o diretório corrente, faça `pwd` e com isso, será exibido na tela o caminho para o diretório onde encontra-se em  relação ao diretório raiz do atual usuário do sistema.

## Copiar arquivos 
O comando `cp` copia arquivos e diretórios. 

Para criar um novo arquivo a partir de um existente use `cp arquivo novoArquivo`. Se quiser criar a cópia dentro de outro diretório, basta informar o caminho pra ele `cp arquivo diretorio/`.

## Buscar arquivos
O último comando desta lista básica é um pouco mais complexo do que os anteriores, mas com um pouco de prática, torna-se fácil de ser utilizado, trata-se do `find`. Este comando irá procurar recursivamente pelo padrão do nome do arquivo informado como parâmetro.
Por exemplo, se deseja buscar o arquivo 'meuArquivo.c' que, eventualmente, está em algum diretório na hierarquia do diretório corrente e deseja efetuar a busca pelo trecho do nome do arquivo, no caso 'meu' em conjunto com a extensão '.c', deste modo ignorando todos os caracteres entre estas duas palavras, faça `find . -name meu*.c` será exibido o caminho até os arquivos encontrados em relação ao diretório corrente.

