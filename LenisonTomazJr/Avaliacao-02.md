### Exercicios do capitulo 2 - Gerência de atividades 

1. Explique o que é, para que serve e o que contém um PCB - Process Control Block 

        - PCB é uma estrutura de dados que armazena informações necessárias para a gerência de uma tarefa e também armazena 
        informações relativas ao seu contexto. 

 Um PCB contém: 

    - Identificador da tarefa. 

    - Estado da tarefa. 

    - Informações de contexto do processador. 

    - Lista de áreas de memória usadas pela tarefa. 

    - Listas de arquivos abertos, conexões de rede e outros recursos usados pela tarefa. 

    - Informações de gerência e contabilização. 



2- O que significa time sharing e qual a sua importância em um sistema operacional? 

    -São sistemas que compartilham o tempo de uso da CPU entre diversos programas, esse s sistemas conseguem executar diversas 
    tarefas simultaneamente, pois existe a divisão do tempo do processador em pequenos intervalos. Caso a tarefa não termine 
    durante o intervalo a ela determinada, há uma interrupção e ela volta para a fila, aguardando novamente sua vez. Esse tipo de 
    sistemas é muito importante para a gerência de tarefas. 


3- Como e com base em que critérios é escolhida a duração de um quantum de processamento? 

    -Tempo de de execução, tempo de espera, tempo de resposta, tempo de eficiência.



5. Indique se cada uma das transições de estado de tarefas a seguir definidas é possível ou não. Se a transição for possível, dê um exemplo de situação na qual ela ocorre (N: Nova, P: pronta, E: executando, S: suspensa, T: terminada).  

• E → P - possível(esta transição ocorre quando se esgota a fatia de tempo destinada à tarefa (ou seja, o fim do quantum)) 

• E → S-possível: caso a tarefa em execução solicite acesso a um recurso não disponível, como dados externos ou alguma sincronização, 
                      ela abandona o processador e fica suspensa até o recurso ficar disponível.) 

• S → E  -  não é possível  

• P → N  - não e possível 

• S → T  -   não é possível 

• E → T  - possível : ocorre quando a tarefa encerra sua execução ou é abortada em consequência de algum erro 
                        (acesso inválido à memória, instrução ilegal, divisão por zero, etc.).) 

• N → S  -  não é possível 

• P → S - não é possível 



6- Relacione as afirmações abaixo aos respectivos estados no ciclo de vida das tarefas (N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada):  

[N ] O código da tarefa está sendo carregado. 

 [ P] A tarefas são ordenadas por prioridades.  

[ E] A tarefa sai deste estado ao solicitar uma operação de entrada/saída.  

[T ] Os recursos usados pela tarefa são devolvidos ao sistema.  

[P ] A tarefa vai a este estado ao terminar seu quantum.  

[ E] A tarefa só precisa do processador para poder executar.  

[ S] O acesso a um semáforo em uso pode levar a tarefa a este estado.  

[E ] A tarefa pode criar novas tarefas.  

[ E] Há uma tarefa neste estado para cada processador do sistema.  

[ S] A tarefa aguarda a ocorrência de um evento externo. 



9- O que são threads e para que servem? 

    -Thread é um pequeno programa que trabalha como um subsistema é uma forma de um processo dividir a si mesmo em duas ou mais 
    tarefas que podem ser executadas concorrencialmente.  



10. Quais as principais vantagens e desvantagens de threads em relação a processos? 

Vantagens: 

      - facilita o desenvolvimento. 

      - não deixam o processo parado.

      -leve. 

 Desvantagens: 

      - trabalho fica mais complexo. 

     - operações de entrada/saída. 
     
     
 11. Forneça dois exemplos de problemas cuja implementação multi-thread não tem
desempenho melhor que a respectiva implementação sequencial.

    -situações aonde se precisar de mais escalabilidade


12. Associe as afirmações a seguir aos seguintes modelos de threads: a) many-to-one (N:1); b) one-to-one (1:1); c) many-to-many (N:M):  

[ a] Tem a implementação mais simples, leve e eficiente.  

[b ] Multiplexa os threads de usuário em um pool de threads de núcleo.  

[ b] Pode impor uma carga muito pesada ao núcleo.  

[a ] Não permite explorar a presença de várias CPUs pelo mesmo processo.  

[ c] Permite uma maior concorrência sem impor muita carga ao núcleo. 

 [b ] Geralmente implementado por bibliotecas.  

[ b] É o modelo implementado no Windows NT e seus sucessores.  

[ a] Se um thread bloquear, todos os demais têm de esperar por ele.  

[ c] Cada thread no nível do usuário tem sua correspondente dentro do núcleo.  

[c ] É o modelo com implementação mais complexa. 
     


