# Avaliação 2o Bimestre S.O - Parte 1
### Emerson Breno Martins Carvalho

### Interação entre tarefas - Capítulo 13 - Impasses
#### (1) Q4:  Uma vez detectado um impasse, quais as abordagens possíveis para resolvê-lo? Explique-as e comente sua viabilidade.
#### R:
- A resolução de um impasse pode ser feita de duas formas:  
	- **1 - Eliminar tarefas**: uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais tarefas possam prosseguir. A escolha das tarefas a eliminar deve levar em conta vários fatores, como o tempo de vida de cada uma, a quantidade de recursos que cada tarefa detém, o prejuízo para os usuários que dependem dessas tarefas, etc. 
	 - **2 - Retroceder tarefas**: uma ou mais tarefas envolvidas no impasse têm sua execução parcialmente desfeita (rollback), de forma a fazer o sistema retornar a um estado seguro anterior ao impasse. Para retroceder a execução de uma tarefa, é necessário salvar periodicamente seu estado, de forma a poder recuperar um estado anterior quando necessário.

#### (2) Q8: Nos grafos de alocação de recursos da figura a seguir, indique o(s) ciclo(s) onde existe um impasse:
#### R:
- Grafo 1: A dependência cíclica entre tarefas e recursos deixa evidente o impasse no ciclo t1 --> r2 → t2 --> c1 → t1.
- Grafo 2: A dependência cíclica entre tarefas e recursos deixa evidente o impasse no ciclo t1--> r2 → t2--> r3 → t3--> r1 → t1	.

#### (3) Q9: . A figura a seguir representa uma situação de impasse em um cruzamento de trânsito. Todas as ruas têm largura para um carro e sentido único. Mostre que as quatro condições necessárias para a ocorrência de impasses estão presentes nessa situação. Em seguida, defina uma regra simples a ser seguida por cada carro para evitar essa situação; regras envolvendo algum tipo de informação centralizada não devem ser usadas.
#### R:
- Exclusão mútua: o acesso aos recursos deve ser feito de forma mutuamente exclusiva, controlada por semáforos ou mecanismos equivalentes. No exemplo da figura apresentada, somente as ruas paralelas teriam o trânsito liberado ao mesmo tempo.
- Posse e espera: uma tarefa pode solicitar o acesso a outros recursos sem ter de liberar os recursos que já detém. No exemplo da figura apresentada, o semáforo seria responsável por controlar a "posse e espera" dos carros em cada rua, de forma a evitar conflitos.
- Não-preempção: uma tarefa somente libera os recursos que detém quando assim o decidir, e não os perde de forma imprevista. No exemplo da figura apresentada, o semáforo mantém um padrão para evitar conflitos.
- Espera circular: existe um ciclo de esperas pela liberação de recursos entre as tarefas envolvidas: a tarefa t1 aguarda um recurso retido pela tarefa t2 (formalmente, t1 → t2), que aguarda um recurso retido pela tarefa t3, e assim por diante, sendo que a tarefa tn aguarda um recurso retido por t1. Essa dependência circular pode ser expressa formalmente da seguinte forma: t1 → t2 → t3 → · · · → tn → t1.

### Gestão de memória - Capítulo 14 - Conceitos básicos
#### (4) Q1:  Explique em que consiste a resolução de endereços nos seguintes momentos: codificação, compilação, ligação, carga e execução.
#### R:
-	Codificação: o programador escolhe o endereço de cada uma das variáveis e do código do programa na memória.
-	Compilação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória.
-  Ligação: na fase de compilação, o compilador traduz o código fonte em código binário, mas não define os endereços das variáveis e funções, gerando como saída um arquivo objeto, que contém o código binário e uma tabela de símbolos descrevendo as variáveis e funções usadas, seus tipos, onde estão definidas e onde são usadas. A seguir, o ligador (linker) pega os arquivos objetos com suas tabelas de símbolos, define os endereços de memória dos símbolos e gera o programa executável.
- Carga: também é possível definir os endereços de variáveis e de funções durante a carga do código em memória para o lançamento de um novo processo. Nesse caso, um carregador (loader) é responsável por carregar o código do processo na memória e definir os endereços de memória que devem ser utilizados.
- Execução: os endereços emitidos pelo processador durante a execução do processo são analisados e convertidos nos endereços efetivos a serem acessados na memória real.

#### (5) Q2:  Como é organizado o espaço de memória de um processo?
#### R:
-	O espaço de memória de um processo é organizado na seguinte ordem: TEXT, DATA, BSS, HEAP e STACK.

### Gestão de memória - Capítulo 15 - Hardware de memória
#### (6) Q1:  Explique a diferença entre endereços lógicos e endereços físicos e as razões que justificam o uso de endereços lógicos.
#### R:
-	Os endereços físicos são os endereços dos bytes da memória física do computador e são definidos de acordo com a quantidade de memória instalada na máquina. Já os endereços lógicos são endereços virtuais de memória que são utilizados pelos processos e pelo sistema operacional, portanto são utilizados pelo processador.
-	
#### (7) Q2:  Considerando a tabela de segmentos a seguir (com valores em decimal), calcule os endereços físicos correspondentes aos endereços lógicos 0:45, 1:100, 2:90, 3:1.900 e 4:200.
#### R:
-	0:45	 	= 89
-	1:100		= 300
-	 2:90		= 90
-	 3:1.900	= 3900
-	 4:200		= 1400

#### (8) Q3:  Considerando a tabela de páginas a seguir, com páginas de 500 bytes5, informe os endereços físicos correspondentes aos endereços lógicos 414, 741, 1.995, 4.000 e 6.633, indicados em decimal.
#### R:
-	414 	= 1914 
-	741		=741 
-	1995 	= 495 
-	4000 	= 0 
-	6633 	= 3633

### Gestão de memória - Capítulo 16 - Alocação de memória
#### (9) Q1:  Considere um banco de memória com os seguintes “buracos” não-contíguos: 
#### R:
-	(b) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.

### Gestão de memória - Capítulo 17 - Paginação em disco
#### (10) Q1:  O que é uma falta de página? Quais são suas causa possíveis e como o sistema operacional deve tratá-las?
#### R: 
-	É uma situação que ocorre quando um programa tenta acessar os dados que estão presentes em seu espaço de endereço mas não estão localizados na memória RAM do sistema.

