#Respostas das questões sobre gerência de atividades (Capítulo 02)

##Respostas

## Info
## Aluno: Pablo Ramon Varela de Souza

1 - O PCB (process control block) é uma estrutura de dados presente no núcleo do sistema operacional que é vinculado a um processo.
Dentro dela encontram-se informações vitais sobre o processo, como o PID (identificador do processo), os registradores da CPU, o espaço
alocado aquele processo, prioridade, status e etc. Ela serve para armazenar toda a informação necessária
para tratar um determinado processo.

2 - *time sharing* é o compartilhamento de tempo de processador dado a cada processo. Nos computadores atuais
os processos compartilham tempo de processamento usando as regras definidas no sistema. Se não houvesse
esse compartilhamento os computadores ainda usariam a forma antiga de processamento, onde um processo
que recebia o processador utilizava-o até o fim do processamento, não permitindo a utilização de modo
multitarefa, monopolizando o processador. Nos sistemas atuais os processos recebem o processador por uma
quantidade de tempo, ou até que haja uma interrupção.

3 - Um *quantum* de processamento é definido baseado nos ticks do relógio de hardware do computador
    assim como na prioridade e tipo da tarefa. Quando uma tarefa recebe o processador é definido o tempo
    de seu quantum de acordo com esses parâmetros, e ela recebe um certo número de ticks de execução. 
    No linux por exemplo, esse quantum pode ser de 10 a 200 milissegundos.

4 - e1 - nova
    e5 - pronta
    e3 - executando
    e4 - suspensa
    e2 - terminada
    Nova - A tarefa está sendo criada
    Pronta - A tarefa está em memória pronta para executar
    Executando - A tarefa está usando o processador
    Suspensa - A tarefa está esperando dados externos ou um evento
    Terminada - A tarefa já executou o processamento e devolverá os recursos usados para o sistema
    t1 - transição entre executando e terminada, a tarefa terminou ou foi abortada.
    t2 - transição entre executando e suspensa, a tarefa está esperando uma entrada, ou evento
    t3 - transição entre suspensa e pronta, a tarefa acabou de receber a entrada, ou o evento esperado aconteceu
    t4 - transição entre pronta e executando, a tarefa foi escolhida para ser executada.
    t5 - transição entre nova e pronta, a tarefa terminou de ser carregada na memória.
    t6 - transição entre executando e pronta, o quantum da tarefa se esgotou.
    
    
5 - [E -> P] É possível, por exemplo o fim do quantum
    [E -> S] É possível, por exemplo quando o processo está esperando algo (dado ou etc)
    [S -> E] Não é possível.
    [P -> N] Não é possível.
    [S -> T] Não é possível.
    [E -> T] É possível, por exemplo quando o processo terminou o seu processamento e está pronta para ser apagada da memória
    [N -> S] Não é possível.
    [P -> S] Não é possível.
    
    
6 - [N]
    [P]
    [E]
    [T]
    [P]
    [P]
    [S]
    [E]
    [E]
    [S]
    
8 - O programa com a entrada (a.out 4 3 2 1) vai imprimir um único X.

9 - *threads* são fluxos de execução do sistema. Cada processo pode se dividir em uma ou mais threads, permitindo a um mesmo
processo executar várias tarefas ao mesmo tempo.

10 - A principal vantagem é o fato do processo poder executar mais de uma tarefa ao mesmo tempo. Por 
exemplo, se um navegador não pudesse se dividir em threads a navegação demoraria muito mais, pois 
cada passo do programa teria que ser executado sequencialmente. Ao usar threads, ele pode executar mais 
de uma tarefa do programa de uma vez. A desvantagem é que essa subdivisão torna a gerência de processos
bem mais complexa com a possibilidade de conflitos e problemas de gerenciamento.

11 - Em um problema em que é necessária uma entrada e saída o sequencial se sairá melhor, assim como
em um sistema com poucos recursos.

12 - [N:1]
     [N:M]
     [1:1]
     [N:1]
     [N:M]
     [N:1]
     [N:M]
     [N:1]
     [1:1]
     [N:M]
     

    
