# Dicas de situações comuns

## Remover branch antigos
Às vezes baixamos algum branch remoto para nossa máquina local para ver alguma alteração e esquecemos de excluir depois, então é bom ter uma rotina de apagar todos os branchs que estão na sua máquina mas que não estão mais no servidor remoto. Para isso basta utilizar o `git prune`.

## Guardar o que estava fazendo e entregar outra antes
Já aconteceu de você estar no meio de uma alteração, mas perceber que precisa entregar alguma coisa antes de terminar essa primeira? Nessas horas, a melhor coisa é utilizar o git stash para armazenar sua tarefa. Aí você pode fazer a nova alteração enviar para o servidor remoto e depois retomar a tarefa que estava fazendo antes.
O ideal é que você não tenha que realizar esse procedimento muitas vezes, mas se você precisar, é possível dar um nome para essa sua ação `git stash <motivo>` para verificar a lista de arquivos guardados você pode utilizar o git stash list e para recuperar uma alteração você pode usar git stash apply (para pegar a última alteração) ou então `git stash apply <motivo>` para recuperar uma alteração específica. Depois que tiver feito o seu commit ou se tiver desistido daquela alteração, não se esqueça de deletar fazendo um `git stash drop <motivo>`. Se estiver com medo de esquecer de rodar o comando, no lugar de usar um `apply` e um `drop`, você pode utilizar um `pop`.

## Recomeçar tudo que estava fazendo
Às vezes a gente percebe que não ficou bom o que estávamos fazendo, então queremos zerar o nosso trabalho. Basta rodar um  `git reset --hard HEAD` que você volta para o estado do último commit do branch.

## Modificar commit feito
Você estava todo feliz fazendo uma alteração já tinha até confirmado ela com commit, mas percebeu que esqueceu de fazer um teste. Para voltar adicionar informações em um commit já feito rode o `git commit --amend`

## Restaurar arquivo de um commit específico
Seu amigo pode estar trabalhando em outro branch e você precisa somente de um arquivo que ele fez. Para isso utilize o comando `git checkout <commit-sha> -- <nome-arquivo>`

## Restaurar um commit específico
Caso você queira recuperar o commit que alguém fez em um projeto, mas não quer pegar exatamente o estado mais recente. O comando para isso é o `git cherry-pick id-do-commit`

## Achando o culpado
Por diversos motivos você pode querer saber quem fez um pedaço do código, para isso existe o comando blame. Você pode rodar ele assim `git blame nome-do-arquivo` para saber a última pessoa que fez uma alteração ou passar um intervalo de linhas para fazer a consulta `git blame -w -L 1,12 nome-do-arquivo` (no caso o -w ignora espaços em branco).

## Unificando branches
Em alguns cenários você quer unificar dois branches mas não quer gerar um novo commit utilizando o comando de merge, um exemplo disso é quando você gostaria de preservar o histórico de quem fez as alterações. Nesse caso, você deve utilizar o comando `git rebase`. Mas tome cuidado ao utilizar este comando, pois ao unificar os branches o git pode considerar que o arquivo mais recente é o que deve ser mantido, mas talvez você queira uma versão antiga, então algum código pode acabar se perdendo no caminho.

## Não lembro como funciona um comando
Nesse caso, utilize o comando `git help` que ele vai te ajudar a encontrar o comando que você precisa e te explicar como ele funciona.

## Quero continuar o trabalho de um projeto já existente
Imagine que seu amigo fez um projeto e você queira continuar de onde ele parou, mas ele não quer que suas alterações atrapalhem o que ele está fazendo, nesse caso você precisa fazer um `FORK` do projeto dele. Assim será criado um novo projeto em seu repositório que você poderá criar seus branches e continuar evoluindo. Essa [documentação](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project) explica certinho como fazer um fork.
