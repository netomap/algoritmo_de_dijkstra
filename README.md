# Algoritmo_de_dijkstra

## Descrição

- Solução para encontrar a menor distância entre dois pontos em grafos.  
- Esse repositório é a proposta de desenvolvimento do algoritmo de [Dijkstra](https://pt.wikipedia.org/wiki/Algoritmo_de_Dijkstra) para o [problema 83](https://projecteuler.net/problem=83), do projeto Euller. 
- O problema consiste em dar uma matriz 80x80 com valores inteiros positivos aleatórios e pede que encontre o caminho entre esses valores de menor soma, podendo transitar na vertical e horizontal somente (não na diagonal). 
- Assim, foi feita uma adaptação que é colocar o "custo" nos nós por onde se passava o caminho de valor mínimo e considerar todas as arestas de valor nulo (zero). Existe uma limitação para esse algoritmo de Djikstra que não pode ter valores de arestas negativos, que não é o caso em questão.

## Sobre o algoritmo
- O algoritmo consiste, basicamente, nos seguintes passos:

1) Criar uma matriz "distancias" do mesmo tamanho da matriz "valores" orignal com valores infinitos.
2) Depois, considerar na matriz distancias[0, 0] = valores[0,0], pois vamos começar por esse ponto e vamos calcular até o último ponto (inferior, direita).
3) Para cada nó visitado nessa matriz, avaliamos quem são seus vizinhos (os vizinhos só podem ser na vertical ou horizontal, não na diagonal).
4) Para cada vizinho possível, calculamos o "custo atual" do determinado nó somado ao custo do vizinho. Se essa conta for menor do que o valor "custo" já calculado naquele vizinho, então substituímos, pois queremos o menor "custo" global né. Se o valor for maior, não fazer nada. 
5) Criamos uma lista de nós visitados e atualizamos para cada nó que passa.
6) Dada a matriz de distãncias, pegamos o próximo nó que tem o menor valor dos nós não visitados ainda. 
7) Repetimos esse ciclo até que todos os nós estejam visitados.

## Resultado
- O custo mínimo para este problema é de 425185 é o certo, conforme mostrado o "print" da página quando postado como resultado.

## Próximos passos
- Esse algoritmo que desenvolvi não calcula o trajeto, apenas o custo global mínimo do ponto (0, 0) até o (N, N).
- A matriz distâncias final já é uma matriz onde cada ponto (n, n) é o custo mínimo para se chegar naquele ponto, podendo ser pego facilmente qualquer custo mínimo para cada ponto. 
- Como a matriz é muito grande, não dá para desenhar, mas seria interessante implementar também o "trajeto" percorrido. Talvez fazer com uma matriz menor para implementar esse trajeto percorrido.