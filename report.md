
# Relatório
* Página do trabalho ([link GitHub](TODO))
* Discente 1
   * Nome: Gabriel Velozo Tojal
   * Matrícula: 18110468
   * Distribuição da nota (%): 33,333%

* Discente 2
   * Nome: Matheus Gomes de Oliveira
   * Matrícula: asdasd
   * Distribuição da nota (%): 33,333%

* Discente 3
    * Nome:  João Lucas Tenório de Menezes
    * Matrícula: 18112703
    * Distribuição da nota (%): 33,333%

# ESPAÇO PARA O GRÁFICO 
##### Gráfico de uso de memória e GPU
* Tons de verde estão relacionados à memória, no caso da porcentagem ao uso e não a quantidade
* Tons de vermelho referem-se ao uso da CPU 
![alt text](https://cdn.discordapp.com/attachments/483406101987983371/497595979155898380/unknown.png "Logo Title Text 1")

##### Gráfico da quantidade de memória em Kylobytes: 
![alt text][logo]

[logo]: https://cdn.discordapp.com/attachments/483406101987983371/497597363553173533/dasd.png "Logo Title Text 2"


## Discussão
######   Após as primeiras falhas no projeto, com visível perda de desempenho e parada de funcionamento de alguns computadores devido ao abuso do processador; previa-se uma curva crescendente que atingiria o limite rapidamente, tornando-se constante em 100% (considerando um de core único). Contudo, ao tratar-se da memória, seu uso ascende até decair significativamente; tal fato ocorre devido da utilização, no processo pai(linhas de código 30 a 47), de um comando "sleep(tempo em segundos)" que ao se aproximar do limite de seu While reduz o gasto de memória para evitar desperdício, benefício que não ocorreria com um timeset . 
