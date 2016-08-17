# T1 - Aquecimento de PAD

Mestrado em Ciência da Computação

Programação de Alto Desempenho - Profa. Adrea Charão

Diogo Cardoso - 201660655

**Programa utilizado**: BOTS versão 1.1.2 [link](https://pm.bsc.es/projects/bots/downloads)

## Fibonacci
**Entrada:** 20
**1 Thread**
  - Execução 1: 0,00464100 s
  - Execução 2: 0,00319500 s
  - Execução 3: 0,00463100 s
  - Execução 4: 0,00460300 s
  - Execução 5: 0,00457800 s

**2 Threads**
  - Execução 1: 0,01129300 s
  - Execução 2: 0,01107600 s
  - Execução 3: 0,01119600 s
  - Execução 4: 0,01113200 s
  - Execução 5: 0,01114800 s

## Análise
A implementação do algoritmo de Fibonacci utilizado é uma implementação recursiva. Foi feita de uma maneira para que em cada passo é calculado 2 valores da soma por vez (passando n-1 e n-2 como parâmetros da recursão).

Porém a própria implementação recursiva do algoritmo de Fibonacci é conhecida por não ter muita compatibilidade com o uso de multithreads, quando o assunto é ganho de desempenho.

No caso desse trabalho, a execução com 2 threads obteve um resultado mais lento, com uma média de 2.4 vezes mais tempo de execução. A ideia de calcular 2 valores por thread é boa, mas no caso do Fibonacci onde cada execução depende do resultado da anterior, possivelmente há threads que ficam em espera do resultado de outras sendo assim afetando o tempo de execução final.
