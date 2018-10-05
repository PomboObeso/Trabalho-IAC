
# Relatório
* Página do trabalho (https://github.com/gabrielvlz/Trabalho-IAC)
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
* Tons de verde estão relacionados à memória, onde o uso está representado pela porcentagem.
* Tons de vermelho referem-se ao uso da CPU .
![alt text](https://cdn.discordapp.com/attachments/483406101987983371/497595979155898380/unknown.png "Logo Title Text 1")

##### Gráfico da quantidade de memória em Kylobytes: 
![alt text][logo]

[logo]: https://cdn.discordapp.com/attachments/483406101987983371/497597363553173533/dasd.png "Logo Title Text 2"


## Discussão
######   Ao iniciar o projeto, a expectativa era de uma curva crescente que teria seu fim em 100%. Contudo, após as primeiras falhas e com visível perda de desempenho por longos períodos de tempo, inclusive; parada de funcionamento de algumas máquinas testadas devido ao extremo uso do processador e alocamento de memória que sequer tinham disponível; a possibilidade de uma curva de gráfico constante no limite (o que parecia impossível, tornou-se a melhor hipótese).
###### Como o processo pai e o filho são executados simultaneamente; onde esse entra em dois loops infinitos ao comparar as strings *(strcmp(argv[1],"cpu") == 0)* e *(strcmp(argv[1],"cpu-mem") == 0)*, visível nas linhas 50 e 57; executando assim o protocolo de máxima utilização de CPU e memória principal. Como visível no gráfico, o processamento chega aos seus 100% e mantêm-se constante até aproximar- se dos nove segundos de utilização, onde decai razoavelmente. Em processadores com mais de um núcleo, pode apresentar utilização além de 100%, isto significa que um núcleo está completamente ocupado e a porcentagem excedente refere-se a portecentagem do outro dedicada à esta tarefa. 
######

