# Git do dia a dia
O Git é uma ferramenta muito poderosa e possui diversos recursos, mas no nosso dia-a-dia utilizamos apenas uma dúzia de comandos. Segue abaixo os comandos básicos que você precisa saber.

Garanta que você está na branch principal
`git checkout main`
Garanta que você está com a branch principal atualizada
`git pull`
Para começar uma nova tarefa, você deve criar um branch
`git checkout -b feature_x`
Faça suas alterações no projeto e veja os arquivos que foram alterados
`git status`
Você pode remover algum arquivo que não queira enviar para o git
`git rm <nome_arquivo>`
Informe ao git que para adicionar esses arquivos em sua árvore de alterações
`git add *` (o * significa que é pra adicionar todos os arquivos alterados)
Se quiser ver a diferença do seus arquivos com os que estão na branch principal
`git diff <branch origem> <branch destino>`
Confirme para o git que você terminou as alterações
`git commit -m "motivo da mudança"`
Faça com que o git envie suas alterações para o repositório remoto
`git push origin <feature_x>`

Se você tiver trabalhando com mais pessoas na mesma branch, é possível que alguém tenha feito alguma alteração antes de você terminar a sua. Portanto, antes de enviar suas alterações, recomendo sempre puxar as atualizações do repositório remoto para o seu local (`git pull`). 

Quando terminar sua tarefa naquela branch você deve enviar as alterações para a branch principal.
`git merge main`

Em alguns casos você precisará trocar de branch ativa entre branches já criadas. Para isso use o comando checkout sem a flag -b
`git checkout feature_x`
`git checkout main`

Se achar que não vai precisar mais daquele branch, você pode deletar
`git branch -d feature_x`

Pronto, com esses comandos você já é capaz de criar um novo branch para fazer suas alterações e depois enviá-las de forma segura para a branch principal.
