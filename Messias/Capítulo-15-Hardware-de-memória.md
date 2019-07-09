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
