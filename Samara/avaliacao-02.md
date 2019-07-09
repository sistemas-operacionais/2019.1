## RESPOSTAS DO CAPÍTULO 02

1 - Cada tarefa presente no sistema possui uma estrutura de dados que a representa no núcleo, que é o seu descritor. 
Nessa estrutura são armazenadas as informações relativas ao seu contexto e demais dados necessários à sua gerência. 
Como: identificador da tarefa, estado da tarefa, informações de contexto do processador, áreas de memória utilizadas, 
arquivos abertos, conexões de rede e outros recursos, informações de gerência e contabilização.

2 - O time sharing significa que cada atividade que detém o processador recebe um limite de tempo de processamento, 
denominado quantum. Esgotado seu quantum, a tarefa em execução perde o processador e volta para uma fila de tarefas
“prontas”, que estão na memória aguardando sua oportunidade de executar. É importante pois impede a monopolização
do processador por parte de uma tarefa.

3 - Em um sistema operacional típico o limite de tempo de processamento tem como base as interrupções geradas pelo 
temporizador programável do hardware. Esse temporizador geralmente é programado para gerar interrupções em intervalos 
regulares que são recebidas por um tratador de interrupção. As ativações periódicas do tratador de interrupção são 
chamadas de ticks do relógio.

4 - e1: nova / e5: pronta / e3: executando / e4: suspensa / e2: terminada  
    __Nova:__ a tarefa está sendo criada  
    __Pronta:__ a tarefa está em memória aguardando a disponibilidade do processador.  
    __Executando:__ o processador estpa executando as instruções e fazendo avançar o seu estado.  
    __Suspensa:__ A tarefa não pode executar porque depende de dados externos ainda não disponíveis.  
    __Terminada:__ O processamento foi encerrado e a tarefa pode ser removida da memória do sistema.  
    _t5(nova->pronta):_ terminou de ser carregada em memória  
    _t4(pronta->executando):_ recebe o processador  
    _t2(executando->suspensa):_ aguarda um dado externo ou outro evento  
    _t3(suspensa->pronta):_ dado disponível ou evento ocorreu  
    _t1(executando->terminada):_ termina a execução  
    _t6(executando->pronta):_ fim do quantum 
    
5 - E->P: Possível. Quando o quantum da tarefa chega a fim.  
    E->S: Possível. Caso a tarefa solicite acesso a um recurso não disponível como dado externo.  
    S->E: Não possível.  
    P->N: Não possível.  
    S->T: Não possível.  
    E->T: Possível. Quando a tarefa encerra sua execução ou é abortada em consequência de algum erro.  
    N->S: Não possível.  
    P->S: Não possível.  
    
6 - [N] O código da tarefa está sendo carregado.  
[N] A tarefas são ordenadas por prioridades.  
[E] A tarefa sai deste estado ao solicitar uma operação de entrada/saída.  
[P] Os recursos usados pela tarefa são devolvidos ao sistema.  
[P] A tarefa vai a este estado ao terminar seu quantum.  
[E] A tarefa só precisa do processador para poder executar.  
[S] O acesso a um semáforo em uso pode levar a tarefa a este estado.  
[T] A tarefa pode criar novas tarefas.  
[N] Há uma tarefa neste estado para cada processador do sistema.  
[S] A tarefa aguarda a ocorrência de um evento externo.  

9 - Servem para que o sistema operacional e suporte mais de uma tarefa operando 
no mesmo contexto, ou seja, dentro do mesmo processo. Uma thread é cada fluxo de execução do sistema
seja associado a um processo(threads de usuário que correspondem a uma tarefa a ser executada dentro de
um processo) ou no interior do núcleo (threads de núcleo que reprensentam as tarefas que o núcleo deve realizar).

10 - O modelo de threads N:1 é muito utilizado, por ser leve e de fácil implementação.
Como o núcleo somente considera uma thread, a carga de gerência imposta ao núcleo é
pequena e não depende do número de threads dentro da aplicação. Entretanto esse modelo apresenta problemas em algumas situações,
sendo o mais grave deles relacionado às operações de entrada/saída. Como essas
operações são intermediadas pelo núcleo, se um thread de usuário solicitar uma operação
de E/S o thread de núcleo correspondente será suspenso até a conclusão da operação, fazendo com que todos os threads de usuário
associados ao processo parem de executar enquanto a operação não for concluída. Outro problema desse modelo diz respeito à divisão de recursos entre as tarefas.

11 - aplicações interativas e servidores de rede.

12 - [N:1] Tem a implementação mais simples, leve e eficiente.  
[1:1] Multiplexa os threads de usuário em um pool de threads de núcleo.  
[N:M] Pode impor uma carga muito pesada ao núcleo.  
[N:1] Não permite explorar a presença de várias CPUs pelo mesmo processo.  
[N:1] Permite uma maior concorrência sem impor muita carga ao núcleo.  
[N:M] Geralmente implementado por bibliotecas.  
[1:1] É o modelo implementado no Windows NT e seus sucessores.  
[N:1] Se um thread bloquear, todos os demais têm de esperar por ele.  
[1:1] Cada thread no nível do usuário tem sua correspondente dentro do núcleo.  
[N:M] É o modelo com implementação mais complexa.  

