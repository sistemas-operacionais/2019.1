1. PCB é uma forma de estrutura de dados ligada diretamente ao controle dos processos, ao uso de memoria, controle de entrada e saida e monitoramento de perfomance.

2. time sharing é uma forma de abordagem em que dois ou mais processos podem dividir um processador para que ambos funcionem "ao mesmo tempo". É extremamente importante para que os processos não mantenham o computador ocioso, à espera de alguma fonte externa de recursos.

3. A duração de um quantum de processamento tem como base as interrupções geradas pelo temporizador programável do hardware. Geralmente é usado para gerar interrupções em intervalos regulares como uma forma de manter um controle temporal sobre o processamento de um processo.

4. A transição que falta se encontra num estado reverso entre e3 e e5, se caracterizando como sendo o fim de um quantum.
  e1 = nova; e2 = terminada; e3 = executando; e4 = suspensa; e5 = pronta;
  t1 = termina a execução; t2 = aguarda um dado externo ou outro evento; t3 = dado disponível ou evento ocorreu; t4 = recebe o processador; t5 = terminou de ser carregado na memoria; t6 = fim do quantum.
  
5. possível, fim do quantum;
  possível, no aguardo de algum dado ou recurso compartilhado;
  impossível, é preciso ir para pronta primeiro;
  impossível, a nao ser que o mesmo processo seja copiado;
  impossível, a nao ser que o processo seja "morto" de forma externa;
  possível, basta que o processo esteja terminado;
  impossível;
  impossível;

6. N; P; E; T; P; P; S; E; E; S

7. Não sei sobre diagrama de tempo de execução (não aparece neste capítulo); 

8. um único x.

9. threads sao fluxos de execução do sistema, associados a um processo ou ao interior do núcleo. São usadas para que um processo possa fazer diversas tarefas ao mesmo tempo.

10. Com threads os processos podem realizar diversas tarefas ao mesmo tempo, porém o seu uso pode gerar conflitos entre processos diferentes, caso eles precisem utilizar o mesmo recurso.

11. Quando dois threads necessitam do mesmo recurso simultaneamente ou quando precisam do mesmo tempo de processamento.

12. N:1; N:M ; N:M; N:1; 1:1; N:1; N:M; N:1; 1:1; N:M
