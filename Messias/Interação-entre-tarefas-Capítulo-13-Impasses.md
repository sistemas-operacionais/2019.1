### Sistemas Operacionais - 2º Bimestre - 2019.1
#### Aluno: Emanoel Messias Gomes de Lima.
### Interação entre tarefas - Capítulo 13 - Impasses

#### ° Questões da avaliação
#### (1) página 10, questão 4. Uma vez detectado um impasse, quais as abordagens possíveis para resolvê-lo? Explique-as e comente sua viabilidade.

R: Uma vez detectado um impasse e identificadas as tarefas e recursos envolvidos, o sistema deve proceder à resolução do 
impasse, que pode ser feita de duas formas:<br>
<b>Eliminar tarefas:</b> uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais 
tarefas possam prosseguir. A escolha das tarefas a eliminar deve levar em conta vários fatores, como o tempo de vida de
cada uma, a quantidade de recursos que cada tarefa detém, o prejuízo para os usuários que dependem dessas tarefas, etc.

<b>Retroceder tarefas:</b> uma ou mais tarefas envolvidas no impasse têm sua execuçãoparcialmente desfeita (uma técnica chamada rollback), de forma a fazer o sistema
retornar a um estado seguro anterior ao impasse. Para retroceder a execução de uma tarefa, é necessário salvar periodicamente 
seu estado, de forma a poder recuperar um estado anterior quando necessário. Além disso, operações envolvendo a rede ou 
interações com o usuário podem ser muito difíceis ou mesmo impossíveis de retroceder: como desfazer o envio de um pacote de 
rede,ou a reprodução de um arquivo de áudio na tela do usuário?

#### (2) página 11, questão 8. 8. Nos grafos de alocação de recursos da figura a seguir, indique o(s) ciclo(s) onde existe um impasse:
No grafo da figura da esquerda percebe-se claramente a dependência cíclica entre tarefas e recursos no ciclo
t1 --> r2 → t2 --> c1 → t1, que neste caso evidencia um impasse. <br>


No grafo da figura da direita percebe-se claramente a dependência cíclica entre tarefas e recursos no ciclo
t1--> r2 → t2--> r3 → t3--> r1 → t1, que neste caso evidencia um impasse. 


#### (3) página 11, 9. A figura a seguir representa uma situação de impasse em um cruzamento de trânsito. Todas as ruas têm largura para um carro e sentido único. Mostre que as quatro condições necessárias para a ocorrência de impasses estão presentes nessa situação. Em seguida, defina uma regra simples a ser seguida por cada carro para evitar essa situação; regras envolvendo algum tipo de informação centralizada não devem ser usadas. data de entrega: 05/07/2019

<b>Exclusão mútua:</b> o acesso aos recursos deve ser feito de forma mutuamente exclusiva,
controlada por semáforos ou mecanismos equivalentes. No exemplo da figura
, apenas um carro por vez pode acessar cada rua.<br>

<b>Posse e espera:</b> uma tarefa pode solicitar o acesso a outros recursos sem ter de liberar
os recursos que já detém. No exemplo da figura, cada carro detém
o semáforo de uma rua e solicita o semáforo da outra rua para poder
prosseguir.

<b>Não-preempção:</b> uma tarefa somente libera os recursos que detém quando assim o
decidir, e não os perde de forma imprevista (ou seja, o sistema operacional não
Sistemas Operacionais: Conceitos e Mecanismos cap. 13 – pg. 150
retira à força os recursos alocados às tarefas). No exemplo da figua,
cada carro detém os mutexes obtidos até liberá-los explicitamente.

<b>Espera circular:</b> existe um ciclo de esperas pela liberação de recursos entre as tarefas
envolvidas: a tarefa t1 aguarda um recurso retido pela tarefa t2 (formalmente,
t1 → t2), que aguarda um recurso retido pela tarefa t3, e assim por diante, sendo
que a tarefa tn aguarda um recurso retido por t1. Essa dependência circular pode
ser expressa formalmente da seguinte forma: t1 → t2 → t3 → · · · → tn → t1. No
exemplo da figura, pode-se observar claramente que carro1 → carro2 → carro3 → carro4 → ...carroN.<br>
Formalmente, um conjunto de N tarefas se encontra em um impasse se cada
uma das tarefas aguarda um evento que somente outra tarefa do conjunto poderá
produzir.
no caso da figura uma carro dar passagem para o outro.<br>
Posse e espera: caso as tarefas usem apenas um recurso de cada vez, solicitando-o e
liberando-o logo após o uso, impasses não poderão ocorrer.

