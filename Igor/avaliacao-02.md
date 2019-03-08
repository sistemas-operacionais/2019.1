>### Cap. 2
#### Gerência de atividades - Respostas

1. _PCB (Process Control Block) ou TCB (Task Control Block)_ é a nomeclatura dada à estrutura de dados responsável por armazenar as informações relativas ao seu contexto e os demais dados necessários à sua gerência de uma determinada tarefa presente no sistema, em outras palavras, essa estrutura de dados representa o núcleo.  
  __Em um PCB está contido:__  
    + Identificador da Tarefa;
    + Estado da tarefa;
    + Informações de contexto do processador;
    + Lista de áreas de memória usadas pela tarefa;
    + Listas de arquivos abertos, coneões de redes e outros recursos usados pela tarefa;
    + Informaçções de gerência e contabilização;  
2. __Time Sharing:__ O tempo que a _CPU(Central Processing Unit)_ leva para partilhar os seus processamentos, em outras palavras, o usuário manda um determinado processo que custará um determinado tempo e após este, devolver o controle, que será repassado para outro processo e assim até o __n-égismo__ processo. Graças a isso, hoje com os sistemas operacionais, podemos ter vários processos e várias janelas abertas, aumentando então nossa produtividade.
3. A duração atual do _quantum_ depende muito do tipo de _S.O (Sistema Operacional)_. No Linux ela varia de __10 a 200 milissegundos__, este tempo está diretamente relacionado ao tipo e prioridade da tarefa. Vários critérios podem ser definidos para a avaliação de _escalonadores (quem define a duração dos quantums)_ são eles: tempo de execução ou de vida;tempo de espera;tempo de resposta;justiça;eficiência.
4.  
   + E1 = Nova Tarefa;          //          + T1 = Termina a execução;
   + E2 = Terminada;            //        + T2 = Aguarda um dado externo/evento;
   + E3 = Execução;             //          + T3 = Dado disponível/evento ocorreu;
   + E4 = Suspensa;             //         + T4 = Recebe o processador;
   + E5 = Finalizada (Pronta);  //          + T5 = Carregada na memória;                          //        __+ T6 = End of quantum;__
5.  
  + E → P: Possível (Final de quantum);
  + E → S: Possível (Esperando por um dado externo/evento);
  + S → E: Nop;
  + P → N: Nop;
  + S → T: Nop;
  + E → T: Possível (Processo terminado);
  + N → S: Nop;
  + P → S: Nop;
6.  __N;P;E;T;P;P;S;T;E;S__
7.  _I don't know!_
8. Saída: ```x```
9. Cada fluxo de execução do sistema, seja ele asssociado a um processo ou no interior do núcleo, é denominado __thread__. As threads tem o poder de fazer com que o usuário faça várias tarefas ao mesmo tempo.
10. Vantagem x Desvantagem  
  Vantagem: Processos podem realizar diversas tarefas ao mesmo tempo;  
  Desvantagem: Pode ocasionar conflitos entre processos diferentes, caso os mesmos precisem utilizar o mesmo recurso.
11. Modelo como o 1:1 é mais adequado para situações que requerem maior números de interatividade e serviçõs de rede (servidores), uma vez que, ao criar várias threads uma carga excessiva é imposta ao núcleo do sistema, fazendo então aplicações com diversas tarefas (Web-Services) serem afetadas; Outrossim, o uso de várias threads podem ocasionar conflitos entre processos distintos, de modo que eles necessitem partilhar do mesmo recurso;
12. __A;B;B;A;C;B;A;C;C__
13. [Array index out of página 9]
