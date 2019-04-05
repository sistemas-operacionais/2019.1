# Aluno: João Vitor dos Santos Venceslau
# Avaliação 02

## 1 -
Process Control Block. Estruturas que representam uma tarefa no núcleo e que contém
informações necessárias sobre a mesma. Nela está contido o identificador da tarefa/estado
da tarefa/informações de contexto do processador/ Lista de áreas de memória usadas pela
tarefa/Listas de arquivos abertos, conexões de rede e outros recursos usados pela
tarefa/Informações de gerência e contabilização.

## 2 -
Uma solução que foi elaborada para estabelecer um tempo limite de processamento de
cada tarefa, evitando que o processador permaneça por muito tempo em uma atividade só,
prosseguindo com a próxima atividade na fila.

## 3 -
Com base nas interrupções geradas pelo temporizador programável do hardware, que gera
interrupções em um intervalo X. Essas interrupções são tratados por um tratador de
interrupções, onde as ativações desse tratador são chamadas de ticks do relógio, que é
ajustado pelo núcleo. Ou seja, seu quantum é definido pelo número de ticks.

## 4 -
- e1 = Criação da tarefa, e carregamento dos itens necessários para sua execução.
- e2 = A tarefa foi terminada, e já pode ser removida da memória.
- e3 = A tarefa está sendo executada.
- e4 -= A tarefa foi suspensa, pois depende de dados externos para ser executada, assim,
fica esperando alguma sincronização para poder ser executada ou fica esperando o tempo
passar.
- e5 = A tarefa está na memória, e pronta em uma fila aguardando ser executada apenas
aguardando o processador liberar.
- t1 - A tarefa termina sua execução ou aborta por ocorrência de algum erro.
- t2 - A tarefa está sendo executada, mas necessita de algum dado externo ou sincronização
para poder continuar, então, ela passa por essa transição.
- t3 - A tarefa já conseguiu o recurso necessária, e volta para a fila no estado de "pronta".
- t4 - A tarefa foi "selecionada" e está sendo executada no processador.
- t5 - A tarefa sai do estado de nova, e fica pronta esperando para ser executada pelo
processador.
- t6 - A tarefa está pronta para ser executada, porém não pode ser executada por algum
problema e acaba sendo removida da fila.

## 5 -
- a - Sim. Quando o quantum de uma tarefa é esgotado, e ela não precisa de outros recursos
além do processador.
- b - Sim. Quando a tarefa necessita de algum dado que está no disco.
- c - Não.
- d - Não.
- e - Não.
- f - Sim. Divisão por zero.
- g - Não.
- h - Não.


## 6 -
- a - N
- b - P.
- c - E.
- d - .T.
- e - P
- f - P.
- g - S
- h - N.
- i - E.
- j - S.

## 9 -
São fluxos de execução no sistema, associado a um processo ou no interior do núcleo.
Permitem que mais de uma tarefa seja executada em um processo.

## 10 -
O modelo N:1 é o que tem a implementação mais fácil, e é a mais indicada para aplicações
que exijam muitas threads. Porém, a principal desvantagem dessa implementação é
relacionado às operações de entrada e saída, pois, se uma thread relacionado a um
processo X solicitar alguma operação com dispositivos de E/S, irá gerar uma suspensão de
várias threads relacionadas a esse mesmo processo, até ela ser concluída.

Já o modelo 1:1 foi pensado para que cada thread a nível de usuário tenha a sua respectiva
thread no nível do núcleo, evitando o mesmo problema que ocorria na implementação
anterior. Porém, apresenta um grande problema de escalabilidade, ou seja, várias threads
pode impor uma carga alta sobre o núcleo do sistema, inviabilizando aplicações com muitas
tarefas.

Por último, o modelo N:M permite que os N threads do processo sejam mapeados em um
conjunto de M threads de núcleo, possuindo uma maior escalabilidade, porém, apresenta
algumas desvantagens como a sua complexidade de implementação e maior custo de
gerência dos threads de núcleo.

## 11 -
Aplicações interativas e servidores de rede.

## 12 -
- a
- c
- b
- a
- b
- a
- b
- a
- b
- c
