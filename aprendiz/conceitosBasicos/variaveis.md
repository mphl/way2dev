

# Variáveis

 Variáveis são ferramentas de alocação de dados. Uma variável simplesmente recebe atribuições de valores. Ex:

 ```
	x = 10
	y = x + 5 
 ```

 Nesse exemplo, `y` receberá o valor atual de `x` (10) com a soma do valor 5. Portanto `y` terá o valor de 15.

 Uma variável também pode ter seu valor atualizado:

 ```
	x = 10
	x = x + 1
 ```

Depois de executadas as duas instruções, `x` terá o valor *11* e o antigo valor de *10* será perdido. Isso é um ponto muito importante: toda nova atribuição de valor a uma variável removerá seu valor antigo.

 ## Variáveis imutáveis e Constantes

Variáveis imutáveis não podem ter seu valor alterado após a primeira atribuição, ou seja, variáveis imutáveis recebem valor uma única vez e preserva esse valor por toda a sua existência. 

Esse tipo de variável é usado para <u>garantir que um valor atribuído não seja substituído</u> por engano ou de forma inadvertida, forçando ao desenvolvedor criar uma nova variável que receberá o valor atualizado, caso essa operação seja necessária. 

Alguns exemplos de variáveis imutáveis:

 *Javscript:*

 ```
const valor = 10 //const define que o valor não poder ser alterado
valor = 11 //aconteceria um erro aqui
 ```

 *Java:*

 ```
final Int valor = 10; //final define que o valor não poder ser alterado
valor = 11; //aconteceria um erro aqui
 ```

Já as constantes são uma especialização das variáveis imutáveis. Constantes também são variáveis imutáveis, mas com o objetivo de oferecer um **valor constante dentro da aplicação**. Constantes são usadas para definir configurações, ou evitar que um mesmo valor tenha sua atribuição feita diversas vezes pelo código, o que poderia abrir brechas para erros. 

Normalmente as constantes são aplicadas em letras maiúsculas, mas pode haver variação em relação às **boas práticas aplicadas pela linguagem de programação** em uso. Ex:

```
 const SEPARADOR = ';'

 resultado1 = `valor1${SEPARADOR}valor2` //resultado1 receberia um texto de valor igual a valor1;valor2
 resultado2 = `valor3${SEPARADOR}valor4` //resultado2 receberia um texto de valor igual a valor3;valor4
```

Caso a regra de negócio do exemplo acima mudasse e o `separador` passasse a ser uma barra (/), bastaria mudar o valor da constante para que todo o código seguisse a nova regra. Ex:

```
 const SEPARADOR = '/' // única mudança no código
 
 resultado1 = `valor1${SEPARADOR}valor2` //resultado1 receberia um texto de valor igual a valor1/valor2
 resultado2 = `valor3${SEPARADOR}valor4` //resultado2 receberia um texto de valor igual a valor3/valor4
```

