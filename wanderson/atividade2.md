1- PCB é uma estrutura de dados para armazenar as informações e os dados necessários para a gerencia de uma tarefa do sistema e para interromper a execução de uma tarefa e retornar a ela mais tarde sem corromper seu estado interno. Ele contém um identificador da tarefa, estado da tarefa, informações de contexto do processador, lista de áreas de memória usadas pela tarefa, listas de arquivos abertos, conexões de rede e outros recursos usados pela tarefa, informações de gerência e contabilização.

2- Time share, em português compartilhamento de tempo, veio para resolver com processos que nunca terminavam consumindo o processador assim impedindo a execução de outras tarefas.

3- O desenvolvedor do sistema tem de escolher o que priorizar, em função do perfil das aplicações a suportar. Vários critérios podem ser definidos para a avaliação de escalonadores; os mais frequentemente utilizados são: tempo de execução ou de vida, tempo de espera, tempo de resposta, justiça e eficiência.

4- e1- Nova (A tarefa está sendo criada, seu código está sendo carregado em memória, junto com as bibliotecas necessárias, e as estruturas de dados do núcleo estão sendo atualizadas para permitir sua execução), e5- Pronta (A tarefa está em memória, pronta para executar, apenas aguardando a disponibilidade do processador),  e3- Executando (O processador está dedicado à tarefa, executando suas instruções e fazendo avançar seu estado.), e4- Suspensa (A tarefa não pode executar porque depende de dados externos ainda não disponíveis, aguarda algum tipo de sincronização ou simplesmente espera o tempo passar), e5- terminada (O processamento da tarefa foi encerrado e ela pode ser removida da memória do sistema).
T5 - terminou de ser carregada em memória (ocorre quando a nova tarefa termina de ser carregada em memória, juntamente com suas bibliotecas e dados, estando pronta para executar.), t4- recebe o processador (esta transição ocorre quando a tarefa é escolhida pelo escalonador para ser executada, dentre as demais tarefas prontas), t2- aguarda um dado externo ou outro evento (caso a tarefa em execução solicite acesso a um recurso não disponível, como dados externos ou alguma sincronização, ela abandona o processador e fica suspensa até o recurso ficar disponível), t3- dado disponível ou evento ocorreu (quando o recurso solicitado pela tarefa se torna disponível, ela pode voltar a executar, portanto volta ao estado de pronta), t1- termina a execução (ocorre quando a tarefa encerra sua execução ou é abortada em consequência de algum erro), t6- fim do quantum (esta transição ocorre quando se esgota a fatia de tempo destinada à tarefa, como nesse momento a tarefa não precisa de outros recursos além do processador, ela volta à fila de tarefas prontas, para esperar novamente o processador).

5- • E → P tarefa é escolhida pelo escalonador para ser executada
• E → S  tarefa em execução solicite acesso a um recurso não disponível
• S → E não
• P → N não
• S → T não
• E → T tarefa encerra sua execução ou é abortada por algum erro
• N → S não
• P → S não

6- N, P, P, S, P, E, S, N, E, S.

8- 1

9- São fluxo de execução do sistema, seja associado a um processo ou no interior do núcleo. 

10- Por ser leve e de fácil implementação. Como o núcleo somente considera uma thread, a carga de gerência imposta ao núcleo é pequena e não depende do número de threads dentro da aplicação. Entretanto, se um thread de usuário solicitar uma operação de E/S o thread de núcleo correspondente será suspenso até a conclusão da operação, fazendo com que todos os threads de usuário associados ao processo parem de executar enquanto a operação não for concluída.

11- Como desvantagens desta abordagem podem ser citadas sua complexidade de implementação e maior custo de gerência dos threads de núcleo, quando comparado ao modelo 1:1.

12- 1:1, N:1, N:M, N:1, N:1, N:1, 1:1, N:1, 1:1, N:M
