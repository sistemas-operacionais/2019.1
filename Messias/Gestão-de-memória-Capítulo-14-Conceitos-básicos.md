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

