# Técnicas avançadas de Algoritmos

Você já aprendeu os conceitos básicos para programar e na maior parte do tempo você vai utilizar somente eles. Porém, é importante saber algumas técnicas que ajudam a diminuir a complexidade dos algoritmos. Isto porque ao lidar com um grande volume de dados ou quando a performance do seu algoritmo realmente importa, ter algumas cartas na manga podem te ajudar.

*(Não vamos passar por todas técnicas existentes, vamos apenas comentar as mais utilizadas.)*

## [Algoritmos gananciosos (greedy)](greedy)
- **Contexto**: problemas de otimização (máximo ou mínino)
- **Objetivo**: atingir a solução ótima, ou uma boa aproximação.
- **Forma**: tomar uma decisão ótima localmente. Exemplo: que maximiza o ganho (ou minimiza o custo) imediato.

## [Algoritmos de retrocesso (backtracking)](backtracking)
- **Contexto**: problemas sem algoritmos eficientes (convergentes) para chegar à solução.
- **Objetivo**: convergir para uma solução.
- **Forma**: tentativa-erro. Gerar estados possíveis e verificar todos até encontrar solução, retrocedendo sempre que se chegar a um beco sem saída.

## [Divisão e conquista (divide and conquer)](divideandconquer)
- **Contexto**: Problemas passíveis de se conseguirem sub-dividir.
- **Objetivo**: melhorar eficiencia temporal.
- **Forma**: agregação linear da resolução de sub-problemas de dimensão semelhantes até chegar ao caso-base.

## [Programação dinâmica (dynamic programming)](dynamicprograming)
- **Contexto**: Problemas de solução recursiva.
- **Objetivo**: Minimizar tempo e espaço.
-  **Forma**: Induzir uma progressão iterativa de transformações sucessivas de um espaço linear de soluções.

## Algoritmos NP- Completos