# Libs

Você sabe o que é uma *lib*?

Se você já é um programor talvez tenha usado essa palavra várias vezes e não sabe o que significa. *Lib* é abreviação de *library*, (biblioteca 📚, em inglês).

E sabe da onde vem esse termo?

Antigamente os programadores faziam todo o seu código num arquivo só, mas alguns trechos do código precisavam ser utilizados em mais de um local. Exemplo: ordernar uma lista. 

Tudo bem que o programdor poderia usar o famoso "Ctrl + C e Ctrl +V", mas já pensou se algum dia alguem achasse um bug nesse código, ou então tivesse uma solução melhor para resolver aquele problema. Teria que ser procurado em todo o código aquele trecho para ser alterado. 

Para evitar esse problema, *libs* são utilizadas para armazenar trechos de código que possam ser reutilizados por outros sistemas.

Portanto, esse tipo de integração de código tem 2 vantagens:
- Reuso de código trazendo velocidade no desenvolvimento.
- Não ocasiona nenhum tipo de latência, pois como o código da lib é adicionado junto ao seu código, não existe chamada de rede aumentando o tempo de execução entre o programa que executa o seu código e o código da lib.

Porém essa abordagem tem 2 problemas que vale a pena ficar atento na hora de usar:
- O seu código deve utilizar a mesma linguagem de programação da lib.
- Manutenções na lib não refletem automaticamente em quem está utilizando, normalmente precisa de um update no número da versão e um novo delivery do código que utiliza a lib.
