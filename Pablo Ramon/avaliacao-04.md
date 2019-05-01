## Avaliação - 04 - Capítulo 10 Coordenação entre tarefas
### Info
### Aluno: Pablo Ramon Varela de Souza
### Matrícula: 20181014040009
  
Questão 01:   
Condições de disputa acontecem quando duas tarefas acessam os mesmos recursos compartilhados ao mesmo tempo, podendo gerar 
inconsistências nos valores de tais recursos. Também conhecido como "O Problema da concorrência"  
  
Questão 02:  
a) Está incorreta, pois, essa estratégia só funciona em sistemas mono-processados.  
b) Todos deveriam prover a exclusão mútua, mas não é o que acontece sempre. Por exemplo, usando o algoritmo de solução trivial
duas tarefas podem acessar os mesmos recursos ao mesmo tempo.  
c) A Alternativa está correta.  
d) Não, pois eu posso ter uma situação onde umas tarefa que já está rodando a algum tempo está tentando acessar os mesmos recursos
de uma tarefa que acabou de ser criada.  
e) A Alternativa está correta, com a ressalva de que o código em questão deve acessar recursos compartilhados, se ele não acessa
não pode haver disputa.  
f) A Alternativa está correta, pois ele geralmente é usado para impedir que outras tarefas e outras cpu's acessem essa região
de memória até que ela seja liberada, e para fazer isso ele precisa ser implementado no núcleo para ter acesso a esses elementos
(outras tarefas e cpu's).  
g) Sim, pois ele permite os acessos em ordem, fazendo com que uma mesma tarefa não acesse o pedaço de código duas vezes seguidas.  
h) Não, pois há vários testes de se está ocupado, fazendo a cpu gastar processamento testando.  
i) Funcionaria, usando atrasos aleatórios, mas ainda assim haveria a possibilidade de conflito, mas com menos frequência.  
  
Questão 03:
Espera ocupada é uma estratégia que usa uma espécie de flag (variável) para dizer que aquela área de código está sendo utilizada.
Não é considerada eficiente, pois exige que a cpu fique checando se a área está ocupada continuamente podendo gerar um overhead.
  
Questão 04:  
Na programação de estruturas de controle de concorrência dentro do núcleo do sistema operacional e na construção de sistemas
de computação dedicados, como controladores embarcados mais simples.  
  
Questão 05:  
Se ambos acessarem o teste de ocupado ao mesmo tempo **while(ocupado){};**, eles teriam o mesmo resultado, que não estaria ocupado
e por isso haveria o conflito.
