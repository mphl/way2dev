# Instalando o git
Você precisa instalar o git em seu computador, basta clicar [aqui](https://git-scm.com/downloads) e escolher o seu sistema operacional.

Se você não leu [Uso básico do terminal](../terminal/terminal), recomendamos a leitura, pois utilizaremos o terminal para controlar o git para fim de aprendizado. 

Depois que você pegar o jeito com o git, pode utilizar de ferramentas visuais como o [GitKraken](https://www.gitkraken.com/) que te ajudam a controlar tudo de forma visual, mas é importante o seu primeiro contato ser com a linha de comando.

Para verificar que tudo está instalado certinho, abra o terminal e digite o comando `git --version` . Se aparecer abaixo do seu comando a versão do git, tudo funcionou, qualquer outra mensagem, tente instalar o git novamente porque não deu certo da primeira vez.

Com o git instalado, vamos começar configurando nossas credenciais. O comando `git config` é capaz de configurar várias coisas, mas no momento, vamos configurar apenas o nosso nome e email.

`git config --global user.name "John Doe"`

`git config --global user.email "john.doe@mail.com"`

Obs. o parâmetro --global indica que essas informações serão válidas para todos os seus projetos. Se por uma acaso você vai ter na mesma máquina projetos pessoais e profissionais ou então mais de um profissional, não coloque o parâmetro --global.
Criando o repositório remoto

Nós utilizaremos o Github por ser a ferramenta mais conhecida para hospedar código, além de ser gratuita. 😉

Primeiro, você vai precisar criar uma conta gratuita no site do [Github](https://github.com/).

Depois você deve criar um repositório, pode chamá-lo de *way2dev* ou qualquer nome que quiser. Cada repositório deve ser utilizado para armazenar um projeto. Que tal o seu primeiro projeto ser o seu aprendizado com esse site? Vou explicar sobre isso mais pra frente, mas por enquanto, vamos começar pelo básico do git. 

## Criando o repositório local
Criando um repositório local e apontando para um repositório remoto vazio
`mkdir way2dev`   // cria um diretório

`cd way2dev`      // acessa o diretório

`echo "# way2dev learning" >> README.md`   // cria um arquivo chamado README.md com o texto way2dev learning

`git init`    // inicializa o git neste diretório

`git add README.md`   // adiciona o arquivo README.md na lista de arquivos controlados pelo git

`git commit -m "first commit"` // informa o git que terminou as alteração e passa uma mensagem do que se trata aquela alteração

`git branch -M main`   // informa para o git a ramificação do repositório que ele deve salvar o arquivo

`git remote add origin` https://github.com/<user>/<prject>.git  // informa para o git o endereço remoto de seu repositório
  
`git push -u origin main` // envia para o repositório remoto  as alterações

## Criando um repositório local a partir de um repositório remoto já existente.
Você apenas precisa entrar no diretório de trabalho do seu computador e executar o comando

`git clone https://github.com/<user>/<project>.git`

## Ignorando arquivos do controle do git
Normalmente quando utilizamos alguma IDE ela gera alguns arquivos ocultos para controle do projeto, também existem situações onde o seu projeto gera arquivos binários ou de testes quando você roda localmente, para todos esses cenário e outros mais, você deve ignorar esses arquivos do controle do git, porque não faz sentido você versionar esses arquivos que são necessários apenas na sua máquina. Nesse [link](https://git-scm.com/docs/gitignore) você pode ter detalhes de como criar um arquivo gitignore de acordo com suas necessidades.
