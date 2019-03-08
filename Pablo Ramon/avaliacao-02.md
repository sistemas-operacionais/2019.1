#Respostas das questões sobre gerência de atividades (Capítulo 02)

##Respostas

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
    t6 - transição entre executando e pronta
    **Completar essa resposta**
    
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
    
7 - 
    
