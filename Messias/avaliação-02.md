




#### 1. O que significa time sharing e qual a sua importância em um sistema operacional? 
Time share, em português compartilhamento de tempo, foi um conceito introduzido nos anos 60 
para resolver o a inviabilização do sistema devido a uma tarefa em execução que nunca termina e
nem solicita operações de entrada/saída, monopolizando o processador e impedindo a execução das
demais tarefas. <br>
Nessa solução, cada atividade que detém o processador recebe um limite de tempo de
processamento, denominado quantum. Esgotado seu quantum, a tarefa em execução perde o processador e
volta para uma fila de tarefas“prontas”, que estão na memória aguardando sua oportunidade de executar.
#### 2. Como e com base em que critérios é escolhida a duração de um quantum de processamento?
A duração atual do quantum depende muito do tipo de sistema operacional. No Linux ela varia de 10 a 200 milissegundos,
dependendo do tipo e prioridade da tarefa. 
<br>Vários critérios podem ser definidos para a avaliação de escalonadores 
(quem define a duração dos quantums). Os mais frequentemente utilizados são:
Tempo de execução ou de vida(turnaround time): diz respeito ao tempo total da “vida” de cada tarefa, ou seja,
o tempo decorrido entre a criação da tarefa e seu encerramento, computando todos os tempos de processamento e de espera.<br>
É  uma medida típica de sistemas em lote, nos quais não há interação direta com os usuários do sistema.<br> Não deve ser
confundido com o tempo de processamento, que é o tempo total de uso de processador demandado pela tarefa.<br>
Tempo de espera(waiting time):é o tempo total perdido pela tarefa na fila de tarefas prontas, aguardando o processador.<br> 
Deve-se observar que esse tempo não inclui os tempos de espera em operações de entrada/saída (que são inerentes à aplicação).
#### 5. Relacione as afirmações abaixo aos respectivos estados no ciclo de vida das tarefas 
(N: Nova, P: Pronta, E: Executando, S: Suspensa, T: Terminada):
[N]O código da tarefa está sendo carregado.                                                                                           
[P]A tarefas são ordenadas por prioridades.                                                                                                 
[E]A tarefa sai deste estado ao solicitar uma operação de entrada/saída.                                             
[T]Os recursos usados pela tarefa são devolvidos ao sistema.                                                                
[P]A tarefa vai a este estado ao terminar seu quantum.                                                                           
[E]A tarefa só precisa do processador para poder executar.                                                                    
[S]O acesso a um semáforo em uso pode levar a tarefa a este estado.                                                   
[E]A tarefa pode criar novas tarefas.                                                                                                                                          
[E]Há uma tarefa neste estado para cada processador do sistema.                                                       
[S]A tarefa aguarda a ocorrência de um evento externo.
#### 6. Explique o que é, para que serve e o que contém um TCB - Task Control Block.
TCB é uma estrutura de dados que serve para armazenar as informações relativas ao contexto e os demais dados necessários 
à gerencia de uma tarefa presente no sistema.<br>
Ele serve também para que seja efetuada a Troca de Contexto o que é: 
interromper a execução de uma tarefa e retornar a ela mais tarde, sem corromper seu estado interno.<br>
Um TCB tipicamente contém as seguintes informações:<br>
_ Identificador da tarefa (pode ser um número inteiro, um apontador, uma referência de objeto ou um identificador opaco);<br>
_ Estado da tarefa (nova, pronta, executando, suspensa, terminada,...);<br>
_ Informações de contexto do processador (valores contidos nos registradores);<br>
_ Lista de áreas de memória usadas pela tarefa;<br>
_ Listas de arquivos abertos, conexões de rede e outros recursos usados pela tarefa(exclusivos ou compartilhados com outras tarefas);<br>
_ Informações de gerência e contabilização (prioridade, usuário proprietário, data de início, tempo de processamento já decorrido, volume de dados lidos/escritos, etc.).
#### 6. O que são threads e para que servem?
De forma geral, cada fluxo de execução do sistema, seja associado a um processo ou no interior do núcleo, é denominado thread.<br>
Threads servem para se executar mais de um processo ao mesmo tempo.
#### 7.Quais as principais vantagens e desvantagens de threads em relação a processos?
Vantagens: Leve e de fácil implementação.<br> 
Como o núcleo somente considera uma thread, a carga de gerência imposta ao núcleo é pequena e não depende do número de threads dentro da aplicação.<br>
Desvantagens: Como essas operações são intermediadas pelo núcleo, se um thread de usuário solicitar uma operação de E/S (recepção de um pacote de rede, por exemplo) o thread de núcleo correspondente será suspenso até a conclusão da operação, fazendo com que todos os threads de usuário associados ao processo parem de executar enquanto a operação não for concluí da. 
Outro problema desse modelo diz respeito àdivisão de recursos entre as tarefas. <br>
O núcleo do sistema divide o tempo do processador entre os fluxos de execução que ele conhece e gerencia: as threads de núcleo.<br> 
Assim, uma aplicação com 100 threads de usuário irá receber o mesmo tempo de processador que outra aplicação com apenas um thread (considerando que ambas as aplicações têm a mesma prioridade).<br>
Cada thread da primeira aplicação ir a, portanto receber 1/100 do tempo que recebe o thread único da segunda aplicação, o que não pode ser considerado uma divisão justa desse recurso.
#### 8. Forneça dois exemplos de problemas cuja implementação multi-thread não tem desempenho melhor que a respectiva implementação sequencial. 
O modelo de threads 1:1(multi-thread) é adequado para a maioria das situações e atende bem às necessidades das aplicações interativas e servidores de rede.<br>
No entanto, é  pouco escalável: a criação de um grande número de threads impõe um carga significativa ao núcleo do sistema, inviabilizando aplicações com muitas tarefas (como grandes servidores Web e simulações de grande porte).
#### 9. Associe as afirmações a seguir aos seguintes modelos de threads: a)many-to-one (N:1); b)one-to-one(1:1); c)many-to-many (N:M):                                                                                                                                      
[a]Tem a implementação mais simples, leve e eficiente. <br.                                                
[b]Multiplexa os threads de usuário em um pool de threads de núcleo.<br>                                
[b]Pode impor uma carga muito pesada ao núcleo.<br>                                                              
[a]Não permite explorar a presença de várias CPUs pelo mesmo processo.<br>                      
[c]Permite uma maior concorrência sem impor muita carga ao núcleo.<br>                                
[b]É o modelo implementado no Windows NT e seus sucessores.<br>                                           
[a]Se um thread bloquear, todos os demais têm de esperar por ele.<br.                                      
[c]Cada thread no nível do usuário tem sua correspondente dentro do núcleo.<br>                           
[c]É o modelo com implementação mais complexa.
#### 10. Considere um sistema de tempo compartilhado com valor de quantum tq e duração da troca de contexto ttc. Considere tarefas de entrada/saída que usam em média p% de seu quantum de tempo cada vez que recebem o processador. Defina a eficiência E do sistema como uma função dos parâmetros tq, ttc e p.    
E = tq / tq + ttc
#### 11. Explique o que é, para que serve e como funciona a técnica de aging.
Para evitar a inanição( quando um processo nunca assegura um recurso) e garantir a proporcionalidade expressa através das prioridades estáticas, um fator interno denominado envelhecimento (task aging) deve ser definido.<br> 
O envelhecimento indica há quanto tempo uma tarefa está aguardando o processador e aumenta sua prioridade proporcionalmente.<br>
Dessa forma, o envelhecimento evita a inanição dos processos de baixa prioridade, permitindo a eles obter o processador periodicamente.
#### 12. Explique os conceitos de inversão e herança de prioridade.  
A inversão de prioridades consiste em processos de alta prioridade serem impedidos de executar por causa de um processo de baixa prioridade. 
Um exemplo de como pode ocorrer uma inversão de prioridades: <br>
1.Em um dado momento, o processador está livre e é alocado a um processo de baixa prioridade pb;                                                                                                                                                      
2.durante seu processamento, pb obtém o acesso exclusivo a um recurso R e começa a usá-lo;                                                                                                                                      
3.pb perde o processador, pois um processo com prioridade maior que a dele (pm) foi acordado devido a uma interrupção;
4.pb volta ao final da fila de tarefas prontas, aguardando o processador; enquanto ele não voltar a executar, o recurso R permanecer á alocado a ele e ninguém poderá usá-lo;<br>
5.Um processo de alta prioridade pa recebe o processador e solicita acesso ao recurso R; 
como o recurso está alocado ao processo pb, pa é suspenso até que o processo de baixa prioridade pb 
libere o recurso. Neste momento, o processo de alta prioridade pa não pode continuar sua execução, 
porque o recurso de que necessita está nas mãos do processo de baixa prioridade pb. Dessa forma, 
pa deve esperar que pb execute e libere R,
o que justifica o nome inversão de prioridades.
