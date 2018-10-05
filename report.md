
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
######   Ao iniciar o projeto, a expectativa era de uma curva crescente que teria seu fim em 100%. Nos primeiros testes, com a máquina parando de funcionar imediatamente ou simplesmente não rodando o código, esperava uma curva que subiria exponencialmente de 0 a 100 em fração de segundos. Contudo, após diversos testes em máquinas diferentes viu-se que algumas não necessariamente perdiam totalmente seu desempenho após atingir 100% e que outras ultrapassavam esse valor e não necessitavam ser reiniciadas, chegando a cerca de 110% enquanto algumas paravam imediatamente ao limite em cerca de 3 segundos e se tornavam inutilizáveis. Tal fato ocorria porque processadores com mais de um núcleo passavam a parte excedente para o núcleo sobressalente, onde o computador interpretava como 100% de um somando com 10% de outro. Assim, a curva resultante era clara, em um determinado computador teste que possuísse apenas um núcleo e memória suficiente para suportar o alocamento dinâmico por dez segundos, a curva de processamento seria crescente enquanto o processador suportasse, atingido 100% e mantendo-se constante até recuperar desempenho.

###### O processo filho entra em dois loops infinitos ao realizar as seguintes comparações de *strings (strcmp(argv[1],"cpu") == 0)* e *(strcmp(argv[1],"cpu-mem") == 0)*, visível nas linhas 50 e 57; onde a primeira condição (linha 50) executa assim o protocolo de máxima utilização de CPU que é meramente a chamada de um *loop* infinito "for(;;)"(linha 52) em que o contador não existe início e nem limite ou condição de parada são especificados, trabalhando constantemente com lixo de memória até a máquina tornar-se incapacitada de realizar qualquer função de resultar num *crash*. Como visível no gráfico, o processamento chega aos seus 100% e mantêm-se constante até aproximar-se dos nove segundos de utilização, onde oscila razoavelmente de 100% para aproximadamente 90% e deste para 91%. 
######  A utilização de memória, representada no gráfico apresenta uma curva que atinge seu pico tão rapidamente quanto o uso de CPU, porém inicia a oscilação antes e apresenta mais inconstância, decaindo de 100% para 50.2% até chegar em 30%. O protocolo de utilização intensa de memória inicia-se no processo filho, na linha 57 na comparação da *string* *(strcmp(argv[1],"cpu-mem") == 0)* e fundamenta-se numa realocação "interminável" de memória principal dentro de um loop infinito de comando "for" que pode ser encontrado na linha 59. A função em C, responsável pela realocação é denominada "malloc", que realiza essa mudança em forma de bytes.

###### Diferentedo tradicional "printf", utilizado para "imprimir" textos, caracteres ou valores na tela do usuário; a linguagem C permite chamadar de  sistemas derivadas do comando "sprintf", uma representação de um texto do usuário  no terminal. Para fazer o monitoramento usa-se o “pmap” e colocando-o na string “bash2”. O malloc fora implementado para “forçar” a memória dentro do loop infinito (for) assim necessitando testes com vários valores até atingir-se o "(int)x1" que basicamente se trata de uma alocação por variável que irá separar uma certa quantidades de bytes, já no caso deste código viu-se mais coveniente a utilização do  int que já aloca 4 bytes para o valor número. Vale ressaltar que parar chegar neste valor fora necessário passar por vários erros e pesquisas sobre a alocação de memória baseada em variáveis priorizando a observação empírica até atingir a alocação ideal para a quantidade de memória principal disponível e busca de métodos mais eficientes etc. Após testar, apresentou-se necessário o uso da condição de parada while e o uso do sleep, que é uma função em C que faz pausas por intervalo de tempo determinado por parâmetro. Ex: sleep(1) irá fazer pausas de 1 segundo, que no caso do programa iria executar o sleep por 10 seg já que nosso while tem condição de parada de contador equivalente a 10, para atingir o tempo pedido pelo processo. Após este while ser executado com sucesso, matamos o processo filho com a função kill que é bastante conhecida por usuários linux como uma função que mata determinados processos, no nosso caso, o processo filho. Ressaltando que também usamos uma biblioteca em C do sistema para isso.

