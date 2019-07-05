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


### Gestão de memória
### Capítulo 14 - Conceitos básicos 
#### Aluno: Emanoel Messias Gomes de Lima.

#### °Questões da avaliação
página 10
#### (4) questão 1. Explique em que consiste a resolução de endereços nos seguintes momentos: codificação, compilação, ligação, carga e execução.

<b>Codificação:</b> programa escolhe a posição de cada variável e do código do programa (Sistemasembarcados em linguagem de 
máquina).<br>
<b>Compilação:</b> compilador escolhe a posição das variáveis na memória, código fonte faz e parte doprograma deve ser conhecido
no momento da compilação para evitar conflito em endereços namemória.<br> 
<b>Ligação:</b> compilador gera símbolos que representem as variáveis.<br>
<b>Carga:</b> define os objetos de variáveis e funções de carga do código em memória para lançamento denovo processo.
<b>Execução:</b> são analisados e convertidos pelo processador para a memória final (real).

#### (5) questão 2. Como é organizado o espaço de memória de um processo? data de entrega: 05/07/2019
Cada processo é implementado pelo sistema operacional como uma “cápsula”
de memória isolada dos demais processos, ou seja, uma área de memória exclusiva que
só o próprio processo e o núcleo do sistema podem acessar.<br>
A área de memória do processo contém as informações necessárias à sua execução: código binário, variáveis,
bibliotecas, buffers, etc. Essa área é dividida em seções ou segmentos, que são intervalos
de endereços que o processo pode acessar. A lista de seções de memória de cada
processo é mantida pelo núcleo, no descritor do mesmo.
As principais seções de memória de um processo são:<br>
TEXT: contém o código binário a ser executado pelo processo, gerado durante a compilação e a ligação com as 
bibliotecas e armazenado no arquivo executável. Esta seção se situa no início do espaço de endereçamento do processo e
tem tamanho fixo, calculado durante a compilação.<br>
DATA: esta seção contém as variáveis estáticas inicializadas, ou seja, variáveis que
estão definidas do início ao fim da execução do processo e cujo valor inicial é
declarado no código-fonte do programa. Esses valores iniciais são armazenados
no arquivo do programa executável, sendo então carregados para esta seção
de memória quando o processo inicia. Nesta seção são armazenadas tanto
variáveis globais quanto variáveis locais estáticas (por exemplo, declaradas
como static em C).<br>
BSS: historicamente chamada de Block Started by Symbol, esta seção contém as variáveis
estáticas não-inicializadas. Esta seção é separada da seção DATA porque as
variáveis inicializadas precisam ter seu valor inicial armazenado no arquivo
executável, o que não é necessário para as variáveis não-inicializadas. Com essa
separação de variáveis, o arquivo executável fica menor.<br>
HEAP: esta seção é usada para armazenar variáveis alocadas dinamicamente, usando
operadores como malloc(), new() e similares. O final desta seção é definido
por um ponteiro chamado Program Break, ou simplesmente break, que pode ser
ajustado através de chamadas de sistema para aumentar ou diminuir o tamanho
da mesma.<br>
STACK: esta seção é usada para manter a pilha de execução do processo, ou seja, a
estrutura responsável por gerenciar o fluxo de execução nas chamadas de
função e também para armazenar os parâmetros, variáveis locais e o valor de
retorno das funções. Geralmente a pilha cresce “para baixo”, ou seja, inicia em
endereços maiores e cresce em direção aos endereços menores da memória. O
tamanho total desta seção pode ser fixo ou variável, dependendo do sistema
operacional.
Em programas com múltiplas threads, esta seção contém somente a pilha do programa principal. Como threads podem ser criadas e destruídas dinamicamente,
a pilha de cada thread é mantida em uma seção de memória própria, alocada
dinamicamente no heap ou em blocos de memória alocados na área livre para
esse fim.

### Capítulo 15 - Hardware de memória

#### Aluno: Emanoel Messias Gomes de Lima.

#### °Questões da avaliação
página 21
#### (6) questão 1. Explique a diferença entre endereços lógicos e endereços físicos e as razões que justificam o uso de endereços lógicos.
Endereços físicos (ou reais) são os endereços dos bytes de memória física do computador. Estes endereços são definidos pela quantidade de memória disponível na
máquina.<br>
Endereços lógicos (ou virtuais) são os endereços de memória usados pelos processos e
pelo sistema operacional e, portanto, usados pelo processador durante a execução. Estes endereços são definidos de acordo com o espaço de endereçamento
do processador.<br>
Para ocultar a organização complexa da memória física e simplificar os procedimentos de alocação da memória aos processos, os sistemas de computação modernos
implementam a noção de memória virtual.
Ao executar, os processos “enxergam” somente a memória virtual. Assim,
durante a execução de um programa, o processador gera endereços lógicos para acessar a memória.



#### (7) página 7. Considerando a tabela de segmentos a seguir (com valores em decimal),calcule os endereços físicos correspondentes aos endereços lógicos 0:45, 1:100, 2:90, 3:1.900 e 4:200.

R:<br>
0:45; ef = 89.<br>
1:100; ef= 300.<br>
2:90; ef = 90.<br>
3:1.900; ef = inválido.<br>
4:200; ef = 1.400.



#### (8) página 8. Considerando a tabela de páginas a seguir, com páginas de 500 bytes5, informe os endereços físicos correspondentes aos endereços lógicos 414, 741, 1.995, 4.000 e 6.633, indicados em decimal. data de entrega: 05/07/2019


### Capítulo 16 - Alocação de memória

#### Questões da avaliação
#### (9) página 9, questão 5. Considere um banco de memória com os seguintes “buracos” não-contíguos: data de entrega: 05/07/2019

Nesse banco de memória devem ser alocadas áreas de 5MB, 10MB e 2MB, nesta ordem, usando os algoritmos de alocação
First-fit, Best-fit ou Worst-fit. Indique a alternativa correta:<br>
(a) Se usarmos Best-fit, o tamanho final do buraco B4 será de 6 Mbytes.<br>
<b>(b) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.<-- correta</b><br>
(c) Se usarmos First-fit, o tamanho final do buraco B4 será de 24 Mbytes.<br>
(d) Se usarmos Best-fit, o tamanho final do buraco B5 será de 7 Mbytes.<br>
(e) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 9 Mbytes.

R:
A alternativa 'B' está correta pois o Worst-fit utiliza sempre o maior buraco para preencher a solicitação. 
Nesse caso, com o valor (seguindo a sequência) de 5MB adicionado, o B4 será 25MB de espaço (30 - 5),
seguindo com a alocação de 10MB, o buraco B4 passaria a ser 15MB (25-10MB). A próxima inserção será de 2MB, 
mas será realizada, seguindo a propriedade do Worst-fit, em B6, pois é o maior buraco.

### Capítulo 17 - Paginação em disco

#### ° Questões da avaliação
#### (10) página 19, questão 1. O que é uma falta de página? Quais são suas causa possíveis e como o sistema operacional deve tratá-las? data de entrega: 05/07/2019
Páginas que foram transferidas da memória para o disco possivelmente serão
acessadas no futuro por seus processos. Quando um processo tentar acessar uma página
que está em disco, esta deve ser transferida de volta para a memória para possibilitar o
acesso, de forma transparente ao processo. Conforme exposto na Seção 15.6, quando
um processo acessa uma página, a MMU verifica se a mesma está presente na memória
RAM; em caso positivo, faz o acesso ao endereço físico correspondente. Caso contrário,
a MMU gera uma interrupção de falta de página (page fault) que desvia a execução para
o sistema operacional.
O sistema operacional verifica se a página é válida, usando os flags de controle da tabela de páginas. 
Caso a página seja inválida, o processo tentou acessar um endereço inválido e deve ser abortado. Por outro lado, caso a página solicitada seja válida, o
processo deve ser suspenso enquanto o sistema transfere a página de volta para a memória RAM e faz os ajustes necessários na tabela de páginas. Uma vez a página
carregada em memória, o processo pode continuar sua execução.





