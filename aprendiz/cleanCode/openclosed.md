# Open Closed Principle 

O princípio do aberto/fechado nos diz que entidades de software (classes, métodos, módulos, funções, etc ) devem estar abertas para extensão, mas fechadas para modificação. 

Isso pode parecer um pouco confuso, então vou explicar na prática!

Imagina que você tem uma classe que escolhe um profissional para arrumar um veículo. E você desenvolve assim:

```
if (veiculo == carro){
  procurarMecanicoDeCarro()
}else if (veiculo == moto){
  procurarMecanicoDeMoto()
}else {
  veiculoNaoIdentificado()
}
```

Agora você precisa arrumar barcos também. Essa é uma opção de código:

```
if (veiculo == carro){
  procurarMecanicoDeCarro()
}else if (veiculo == moto){
  procurarMecanicoDeMoto()
}else if (veiculo == barco){
  procurarMecanicoDeBarco()
}else {
  veiculoNaoIdentificado()
}
```

Mas poxa, parece que o código não está muito legal. 

Algum amigo pode chegar e falar que seu código tem muito **IF** e você resolve fazer o código assim:

```
swith(veiculo){
  case carro: procurarMecanicoDeCarro()
              break
  case moto: procurarMecanicoDeMoto ()
              break
  case barco: procurarMecanicoDeBarco ()
              break
  default: veiculoNaoIdentificado()
}
```

Mas na prática não faz muita diferença certo? Se amanhã você precisar arrumar jet-ski, ainda vai precisar alterar o seu código.

Como você faz para ter um código extensível e de fácil manutenção?

Em orientação a objetos isso se resolve com polimorfismo, assim:

Deve-se criar uma *interface Veiculo* que declara um método *procurarMecanico*. Assim todos os veículos que implementarem essa interface, terão esse método, e o seu código fica muito mais limpo

```
Veiculo veiculo = new Carro() // ou moto ou barco ou qualquer outra Classe que implemente a interface Veiculo
veiculo.procurarMecanico()
```

Certo, mas e se meu código é funcional, como eu resolvo isso?

Deve-se declarar uma função *ProcurarMecanico* que recebe um *veiculo* como parâmetro.

Esta função possui um mapa de seus veículos e seus métodos de procurar mecânico. Portanto, se algum dia você precisar procurar mecânico de um jet-ski, basta adicionar neste mapa e não alterar nenhum código existente:

```
ProcurarMecanico{
  funcMap = Map<Veiculo, funcProcurarMecanico>
  funcMap.add(carro, procurarMecanicoDeCarro)
  funcMap.add(moto, procurarMecanicoDeMoto)
  funcMap.add(barco, procurarMecanicoDeBarco)
  
  const func = (veiculo) => {
    return funcMap.get(veiculo)
  }

  export default func
}
```

Agora ficou mais claro né?

Um grande abraço e bons estudos.
