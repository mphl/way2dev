# Comandos Bash
Scripts bash são bastante poderosos e componentes importantes para desenvolvimento. Eles podem diminuir tarefas simples e repetitivas em uma única linha de função. Diversos comandos longos podem ser consolidados em códigos executáveis únicos.

O bash está disponível em praticamente todas as distribuições Linux e não exige nenhuma instalação a parte. A lista de shells disponíveis pode ser verificada executando o seguinte comando:
`cat /etc/shells`

## Comandos básicos
Para começarmos com opções de comando básicas, você pode conferir o manual do bash com o comando:

`man bash`

Em seguida, iremos criar o arquivo com extensão **.sh**. Para isso, iremos utilizar o *Editor VIM*. Criamos um novo arquivo com o seguinte comando:

`vim sampleFunction.sh`

O arquivo **.sh** será aberto e iremos editá-lo.

Cada script bash deverá começar com os seguintes caracteres:

`which bash`

O comando abaixo exibe o caminho do script bash.
`/bin/bash`

Um exemplo de função está demonstrado abaixo, quando criamos um diretório e mudamos o caminho para apontar para o novo diretório:
```
sampleFunction () {
  mkdir -p $1
  cd $1
}
```
**$1** significa a variável sendo inserida na função. O bash pode criar variáveis dinâmicas dentro do comando. Para verificar esta função, execute:

`sampleFunction myDir`

Neste caso, o *myDir* é o nome de um diretório válido a ser criado. Se você verificar o diretório em que se encontra atualmente com o comando `pwd`, irá notar que está dentro do novo diretório *myDir*.

Da mesma maneira, qualquer comando comumente utilizado por ser adicionado como uma função bash.

Lembre-se, quando tiver terminado de usar o editor VIM para editar seu arquivo **.sh**, você pode salvar e fechar o arquivo apertando *ESC* para entrar em modo de comando e então digitar `:wq` para salvar e sair.

### Exemplos de funções Bash
Um dos exemplos básicos de uma função bash está destacado abaixo:
```
#!/bin/bash
testfunction(){
echo "My first function"
}
testfunction
```
Se você salvar este script em *testFunction.sh* e executá-lo como `./testFunction.sh`, então você vai ver o resultado:
`My first function`

A função Echo exibe o resultado no console. Se você mudar a posição da definição de função com o calling, então o resultado vai ser um erro. O snippet abaixo irá gerar um erro.
```
#!/bin/bash
testfunction
testfunction(){
  echo "My first function"
}
```
Então, primeiro é preciso definir a função e então invocá-la.

Funções bash podem aceitar qualquer número de parâmetros. O exemplo abaixo aceita dois parâmetros:
```
#!/bin/bash
testfunction(){
  echo $1
  echo $2
}
```

`testfunction "Hello" "World"`

Você também pode utilizar a input interativa e performar funções bash, como mostrado abaixo:

```
#!/bin/bash
addition(){
  sum=$(($1+$2))
  return $sum
}
read -p "Enter a number: " int1
read -p "Enter a number: " int2
add $int1 $int2
echo "The result is : " $?
```
No exemplo acima, o valor da adição está designado em uma soma de variáveis, e isto é retornado da função. Inputs interativas são usadas utilizando *read* para ambos os números. Finalmente, o resultado é exibido utilizando *$?* que armazena o valor retornado de $sum da função.

Funções bash sempre retornam um único valor.

Você pode deixar comentários dentro do arquivo adicionando o símbolo # para deixar notas de ajuda.

Scripts bash suportam:
- Loop While
- Loop For
- Instrução If
- Lógica And
- Lógica Or
- Instrução Else If
- Instrução Case

Abaixo é um exemplo curto do loop While.
```
#!/bin/bash
isvalid=true
count=1
while [ $isvalid ]
do
echo $count
if [ $count -eq 5 ];
then
break
fi
((count++))
done
```
O exemplo acima utiliza as instruções *while* e *if*. Isso executa o *loop while* 5 vezes antes de sair depois de checar a instrução condicional *if*.

O resultado será:
```
1
2
3
4
5
```
O *loop For* pode ser usado para incrementar assim como agravar os contadores. Um exemplo do *loop for* está mostrado abaixo:
```
#!/bin/bash
for (( count=10; count>0; count-- ))
do
echo -n "$count "
done
```
O resultado deste loop será:
`10 9 8 7 6 5 4 3 2 1`

No bash, os símbolos **&&** representam a lógica *AND*, enquanto que **||** representam a lógica *OR*.

Com instruções *if*, também podemos definir *Else if*. Veja abaixo:
```
#!/bin/bash
echo "Enter a valid number"
read n
if [ $n -eq 101 ];
then
echo "This is first number"
elif [ $n -eq 510 ];
then
echo " This is second number "
elif [ $n -eq 999 ];
then
echo " This is third number "
else
echo "No numbers over here"
fi
```
Este mesmo exemplo também pode ser escrito com a instrução case:
```
#!/bin/bash
echo " Enter a valid number"
read n
case $n in
101)
Echo " This is the first number " ;;
510)
echo " This is the second number " ;;
999)
echo " This is the third number " ;;
*)
echo " No numbers over here " ;;
esac
```
Em instruções case, **;;** significa o término do case.

* [referência do texto](https://www.hostinger.com.br/tutoriais/comandos-bash-linux)





