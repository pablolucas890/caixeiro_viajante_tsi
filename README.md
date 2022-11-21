# caixeiro_viajante_tsi

Projeto do Caixeiro Viajante da Disciplina de TSI desenvolvido em Java

## Resumo do Código

O projeto foi desenvolvido em Java utilizando orientação a objetos. Para executá-lo basta abrir o projeto no NetBeans 8.2 com o jdk 1.8 ou superior. Os códigos estão listados na pasta src conforme a estrutura de projetos em Java. O projeto contém duas classes executáveis.

## Algoritmo BackTracking

A Classe CaixeiroViajante.java dentro do pacote caixeiroviajante corresponde a solução do problema do caixeiro viajante utilizando backtracking, nesta solução obtemos uma solução ótima para o problema, isto é, temos certeza que o caminho obtido é o melhor de todos, o custo disso é um alto poder de processamento pelo computador, para poucas cidades este código funciona muito bem, porém para uma quantidade grande de cidades ele se comporta mal visto que a árvore de opções começa a ficar muito grande. Saída do programa para 5 cidades:

```bash
	Matriz
40	50	99	0	32	
50	45	4	42	0	
99	4	0	1	0	
0	42	1	0	78	
32	0	0	78	0	

	Caminhos
0 - 1 - 2 - 3 - 4 - 
0 - 2 - 1 - 3 - 4 - 
0 - 4 - 3 - 1 - 2 - 
0 - 4 - 3 - 2 - 1 - 

	Distancias
165
255
255
165

	Menor Caminho e Menor Distância:
0 - 1 - 2 - 3 - 4 - [165]

```

As estruturas utilizadas foram ArrayLists, Estruturas de Repetição como For e While, e busca em profundidade para a árvore de possibilidades.
---

## Algoritmo genético

## A Classe CaixeiroViajante.java dentro do pacote algoritmogenetico corresponde à solução do problema do caixeiro viajante utilizando um algoritmo genético. Nele utilizamos a lógica de criação de populações, cruzamento, mutação e seleção para um grande número de gerações. Esta solução resulta em um processamento mais rápido o'que faz com que consigamos utilizar um grande número de cidades. O custo disso é o fato de não conseguirmos obter o melhor resultado, nele obtemos resultados bons conforme modificamos parâmetros no código.
As estruturas utilizadas foram ArrayLists, Estruturas de Repetição como For e While, Ordenação de Array Por Funções Próprias do Java (Collections).

## Comparação

Para conseguir uma comparação válida, foi testado um algoritmo ótimo com um número de cidades de maneira crescente até que se encontrasse um número chegando ao limite de 10 minutos de execução.
Após encontrar este limite de número de cidades para o primeiro algoritmo, foi comparado os algoritmos com o valor de cidades encontradas:

  - Algoritmo BackTracking
    - Máximo de Cidades
      - 12 Cidades para um tempo menor que 10 minutos
    - Tempo de execução
      - 38 Segundos para 12 Cidades
    - Consumo de Memória
      - 5930  Mb para 12 Cidades
  - Algoritmo Genético
    - Tempo de execução
      - 3 Segundos para 12 Cidades
    - Consumo de Memória
      - 50 Mb para 12 Cidades

Melhores Configurações Paramétricas
```
int numeroIndividuos = 1000;
Representa o número de indivíduos em cada geração
float porcentagemCruzamento = (float) 0.05;
Representa a porcentagem de cruzamento em cada geração
float porcentagemMutacao = (float) 0.5;
Representa a porcentagem de mutação em cada geração
float porcentagemProximaPopulacao = (float) 0.2;
Representa a porcentagem de indivíduos que passará para próxima geração
int numeroGeracao = 500;
Representa a quantidade de gerações que o algoritmo terá até apresentar o melhor resultado
Estas Configurações paramétricas foram obtidas testando a variacao de parametros até que se encontrasse o melhor valor para 12 cidades com o menor número de gerações possíveis
Gráficos e Dados

```
---

## Complexidade

A complexidade do código com backtracking é n!, o'que faz com que quando uma cidade é adicionada, o tempo sobe drasticamente

## Conclusões

Notou-se que até 11 cidades o algoritmo se com backtracking se comporta bem, finalizando com apenas 4 segundos para executar. Porém quando sentamos o número de cidades igual a 12, o algoritmo cria uma árvore de possibilidades tão grande que começa o comportamento fatorial e isto torna praticamente impossível mensurar o tempo para um número de cidades muito grande (complexidade igual a n!). Esta complexidade fica bem evidenciada no gráfico de número de cidades em função da memória:

Para o algoritmo genético, notou-se que o tempo de execução e a memória crescem com o aumento dos parâmetros (gerações, indivíduos, etc …), desta forma para parâmetros fixos, como foi utilizado, o gráfico se comporta relativamente linear.
Vale Ressaltar que para obter valores ótimos (backtracking) para um número de cidades maior que 11, é necessário aumentar o tamanho da memória heap utilizada pela IDE. Além disso, para computadores com baixo poder de processamento e memória o algoritmo ótimo se torna muito complexo de se observar resultados.
