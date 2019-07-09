## Questão 1

  São descritores de processos que ficam mantidos no núcleo do sistema operacional. Serve para armazenar as informa-
ções referentes aos processos. Cada processo possui um identificador único no sistema, o PID - Process IDentifier.

## Questão 2

  Time-sharing significa "tempo compartilhado"; nesse tipo de solução, cada atividade que detém o processador recebe
um limite de tempo de processamento, denominado quantum. Esgotado seu tempo, a tarefa em execução perde o processador 
e volta para uma fila de tarefas “prontas”, que estão na memória aguardando sua oportunidade de executar.

## Questão 3

  A duração atual do quantum depende muito do tipo de sistema operacional. Em um sistema operacional típico, a imple-
mentação da preempção por tempo tem como base as interrupções geradas pelo temporizador programável do hardware. Esse
temporizador normalmente é programado para gerar interrupções em intervalos regulares, que são recebidas por um trata-
dor de interrupção; as ativações periódicas do tratador de interrupção são normalmente chamadas de ticks do relógio.

## Questão 4

  e1 - nova tarefa
  e2 - tarefa terminada
  e3 - tarefa em execução
  e4 - tarefa suspensa
  e5 - tarefa pronta

  t1 - termina a execução
  t2 - aguarda um dado externo ou outro evento
  t3 - dado disponível ou evento ocorreu
  t4 - recebe o processador
  t5 - carregada na memória
  t6 - fim do quantum (e3 -> e5)

## Questão 5

  Possível. Fim do quantum.
  Possível. Aguardando um dado externo.
  Impossível. 
  Possível. Momento em que uma nova tarefa é admitida no sistema.
  Impossível.
  Possível. Final da execução.
  Impossível.
  Impossível.

## Questão 6

  N
  P
  E
  P
  P
  P
  S
  T
  P
  S

## Questão 7

## Questão 8

## Questão 9

  De forma geral, cada fluxo de execução do sistema, seja associado a um processo ou no interior do núcleo, é denominado
thread. Se dividem em threads de usuário e de núcleo. As threads de usuário são as tarefas que devem ser realizadas pelos
usuários e as de núcleo são as que devem ser realizadas pelo núcleo.

## Questão 10

  O modelo de threads N:1 é muito utilizado, por ser leve e de fácil implementação. Como o núcleo somente considera uma
thread, a carga de gerência imposta ao núcleo é pequena e não depende do número de threads dentro da aplicação. Em compen-
sação, o modelo de threads N:1 apresenta problemas em algumas situações, sendo o mais grave deles relacionado às operações
de entrada/saída. Outro problema desse modelo diz respeito à divisão de recursos entre as tarefas.

## Questão 11
  O modelo de threads 1:1 (multi-thread) é adequado para a maioria das situações e atende bem às necessidades das aplica-
ções interativas e servidores de rede. No entanto, é pouco escalável: a criação de um grande número de threads impõe uma
carga significativa ao núcleo do sistema, inviabilizando aplicações com muitas tarefas (como grandes servidores Web e si-
mulações de grande porte)

## Questão 12

  a
  b
  b
  a
  c
  b
  a
  c
  c

## Questão 13
