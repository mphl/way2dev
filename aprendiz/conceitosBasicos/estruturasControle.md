 # Estruturas de controle

Estruturas de controle tem o objetivo de controlar o fluxo de execução de um código. Trazendo para o dia a dia, imagine as estruturas de controle como uma tomada de decisão com base nas informações existentes. Ex:
Estou na frente de uma máquina de refrigerantes e tenho a intenção de comprar um pois estou com sede.
Se eu tenho dinheiro para usar na máquina, farei a compra, caso contrário seguirei meu caminho e continuarei com sede xD

É exatamente para isso que estruturas de controle servem: para identificar se podemos/devemos seguir por um caminho no fluxo de execução ou não.

 ### If/else

**If/else** são sem sombra de dúvidas a estrutura de controle mais comum. Elas seguem exatamente o raciocínio explicado na introdução deste tópico:

```
tenhoDinheiro = false

if(tenhoDinheiro) {
 comprarRefrigerante()
} else {
 irEmboraComSede()
}
```

Apesar do exemplo acima, muitas vezes o **else** é desnecessário. Isso porque o **else** executa uma instrução que só será executada se a condição aplicada no **if** for **falsa**. Se as ações subsequentes precisarem ser executadas indiferentemente da condição do **if** ser verdadeira ou falsa, não existe a necessidade de usarmos o **else**. Exemplo:

```
tenhoDinheiro = false

indoParaOTrabalho()
encontroMaquinaDeRefrigerantes()

if(tenhoDinheiro) {
  comproRefrigerante()
}

sigoCaminhoParaOTrabalho()
```

No exemplo acima, `sigoCaminhoParaOTrabalho()` deverá ser executado indiferente do código `comproRefrigerante()` ser chamado ou não. Além dessas duas construções, ainda podemos ter uma terceira forma de compor o if/else, que é usada quando temos múltiplas condições. Essa terceira forma é o controle **else if**. Ex:

```
tenhoDinheiro = false
tenhoBilheteDeMetro = false

if(tenhoDinheiro E tenhoBilheteDeMetro) {
  comproUmRefrigerante()

}else if(tenhoDinheiro) { 
/* Não preciso checar se "tenhoBilheteDeMetro" pois essa condição de "else if" só é verificada caso a condição anterior tenha sido falsa, mas como essa condição depende que eu tenha dinheiro, preciso checar se foi ela que falhou na verificação anterior ou não */
  comproBilheteDeMetro()
 
}else {
 // se nenhuma das condições acima foi executada, executo o terceiro caminho
  vouAteUmCaixaEletronicoSacarDinheiro()
}
```

A estrutura de **if**, **else if**, e **else** pode ter várias condições encadeadas (usando **else if**), mas normalmente não é uma boa prática por atraplhar a leitura de seu código e pode ser mitigado com algumas estratégias de construção de código mais avançadas que veramos em outros tópicos.

**Importante**: *if*, *else if* e *else* são termos **genéricos** e algumas linguagens apresentam variação nesses nomes. Mas indiferente dos nomes a **função de controlar o fluxo com base em condicionais** é a mesma.



 ### Switch

O **switch** é um recurso de controle muito parecido com o **if/else**, com algumas mudanças importantes:

- Suas condições **não são exclusivas**, você deve interromper a execução de outras cláusulas usando o comando **break** ou equivalente para torná-las exclusivas;
- O **switch** normalmente opera em cima de um único valor e oferece caminhos usando como base o valor apresentado (ficará mais claro no exemplo abaixo).

```
quantidadeDeFigurinhasRepetidas = 5

switch (quantidadeDeFigurinhasRepetidas) {
  case 1:
   aguardarTerMaisFigurinhasRepetidas();
  break;
  case 2:
   tentarTrocarMasContinuarComprando();
  break;
  case 3:
   pararDeComprarFigurinhas();
  break;
  default: 
   // essa cláusula será executada caso nenhum dos valores das cláusulas anteriores seja o definido na variável
   desistirDaColecaoEFocarNoVideoGame();
}
```

A última cláusula do switch não precisa do comando **break**, já que não existem cláusulas abaixo dela. A estrutura do switch também sofre algumas alterações dependendo da linguagem de programação utilizada.

Como foi possível ver, no **switch** você não usa uma "**condição**" como no **if**, e sim, avalia uma variável recebida para tomar uma decisão **com base em seu valor**. 
