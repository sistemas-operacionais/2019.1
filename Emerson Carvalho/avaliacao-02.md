# Exercicios Capitulo 2
## Aluno: Emerson Breno Martins Carvalho

1. Explique o que é, para que serve e o que contém um PCB - Process Control Block.

    R:  É um elemento descritor de processos pertencente ao núcleo do sistema operacional, utilizado para armazenar as informações
referentes aos processos ativos no sistema.

2. O que significa time sharing e qual a sua importância em um sistema operacional?

    R:  O conceito de time sharing(compartilhamento de tempo) foi criado para que cada atividade que detenha o 'controle' do processador receba um limite de tempo de processamento, conhecido como quantum. Através deste controle qualquer atividade que ultrapasse o tempo limite irá perder o processamento e irá voltar para a fila de tarefas que estão aguardando para serem executadas. Portanto, esse conceito é muito importante para manter o sistema operacional em funcionamento.  

3. Como e com base em que critérios é escolhida a duração de um quantum de processamento?

    R:  A duração do quantum é definida com base no sistema operacional e de acordo com o tipo e prioridade da tarefa.

5. Indique se cada uma das transições de estado de tarefas a seguir definidas é possível ou não. Se a transição for possível, dê um exemplo de situação na qual ela ocorre (N: Nova, P: pronta, E: executando, S: suspensa, T: terminada).

    • E → P   Possível

    • E → S   Possível

    • S → E   Não Possível

    • P → N   Não Possível

    • S → T   Não Possível

    • E → T   Possível

    • N → S   Não Possível

    • P → S   Não Possível

6. Relacione as afirmações abaixo aos respectivos estados no ciclo de vida das tarefas (N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada):

    [N] O código da tarefa está sendo carregado.

    [P] A tarefas são ordenadas por prioridades.

    [N] A tarefa sai deste estado ao solicitar uma operação de entrada/saída.

    [T] Os recursos usados pela tarefa são devolvidos ao sistema.

    [S] A tarefa vai a este estado ao terminar seu quantum.

    [P] A tarefa só precisa do processador para poder executar.

    [S] O acesso a um semáforo em uso pode levar a tarefa a este estado.

    [E] A tarefa pode criar novas tarefas.

    [E] Há uma tarefa neste estado para cada processador do sistema.

    [S] A tarefa aguarda a ocorrência de um evento externo.

8. Indique quantas letras “X” serão impressas na tela pelo programa abaixo quando for executado com a seguinte linha de comando:
    
    a.out 4 3 2 1

    R:  XXXXX

9. O que são threads e para que servem?

    R:  Threads é basicamente um fluxo de execução de tarefas que operam dentro de um mesmo processo, ou seja, tarefas que são executadas dentro de um mesmo contexto. Por exemplo, um aplicativo 'x' de edição de fotos terá várias tarefas sendo executadas simultaneamente no mesmo contexto.

10. Quais as principais vantagens e desvantagens de threads em relação a processos?

    R:  Uma das vantagens que pode ser citada diz respeito ao ganho de desempenho do sistema. Já uma desvantagem é o aumento da complexidade de implementaçaõ.

11. Forneça dois exemplos de problemas cuja implementação multi-thread não tem desempenho melhor que a respectiva implementação sequencial.

12. Associe as afirmações a seguir aos seguintes modelos de threads: a) many-to-one (N:1); b) one-to-one (1:1); c) many-to-many (N:M):
    
    [A] Tem a implementação mais simples, leve e eficiente.

    [B] Multiplexa os threads de usuário em um pool de threads de núcleo.

    [B] Pode impor uma carga muito pesada ao núcleo.

    [A] Não permite explorar a presença de várias CPUs pelo mesmo processo.

    [C] Permite uma maior concorrência sem impor muita carga ao núcleo.

    [B] Geralmente implementado por bibliotecas.

    [A] É o modelo implementado no Windows NT e seus sucessores.

    [C] Se um thread bloquear, todos os demais têm de esperar por ele.

    [C] Cada thread no nível do usuário tem sua correspondente dentro do núcleo.
    
    [C] É o modelo com implementação mais complexa.
