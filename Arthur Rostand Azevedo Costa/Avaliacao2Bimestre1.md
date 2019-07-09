Entre o capítulo 13 e 17:

1) Uma vez detectados os impasses, existem duas formas de se lidar com eles: eliminando tarefas e retrocedendo tarefas. Na eliminação das tarefas são escolhidas uma ou mais tarefas a serem eliminadas, levando em conta fatores como o tempo de vida, a quantidade de recursos e o prejuízo de usuários. No retroceder das tarefas, uma ou mais tarefas são escolhidas para terem parte da sua execução desfeita, retornando para um ponto seguro, mas para isso é necessário manter um registro periódico do estado da tarefa, sem contar que é pouco ou nada viável quando envolve a rede ou interações com usuários.

2) Os ciclos com impasse são t1 ⤏ r2 ⇾ t2 ⤏ r1 ⇾ t1 no primeiro exemplo e t1 ⤏ r2 ⇾ t2 ⤏ r3 ⇾ t3/t4 ⤏ r1 ⇾ t1 no segundo exemplo.

3) Levando em conta a imagem fornecida é fácil notar que ela atende as 4 condições necessárias para o impasse:
Exclusão mútua: Dois carros não podem acessar o mesmo espaço da via, pela via ser única, e pelos carros serem objetos sólidos.
Posse e espera: Os carros que ocupam um lugar da via precisam esperar que outro carro libere um novo espaço para que possam ocupá-lo, já que os demais espaços válidos estão ocupados.
Não-preempção: Seria tirania política retirar o direito do dono do carro a dirigi-lo ou mover o carro externamente por meios invasivos, logo o motorista carro só pode liberar o seu espaço na via se ele se mover voluntariamente para um outro espaço.
Espera circular: cada carro envolvido está esperando que o próximo carro faça algo, liberando um outro espaço para que ele possa circular. Sem poder retornar ou avançar, ele está preso.
Como evitar: O carro que se aproxima do cruzamento esperar 10 segundos e então buzinar antes de começar a cruzar. Se outro motorista que se aproxima do cruzamento ouvir uma buzina antes do fim dos seus 10 segundos, ele precisar pausar a contagem e só poderá voltar a contar/buzinar quando um carro terminar de cruzar.

4)  Na edição: O programador escolhe o endereço.
Na compilação: O compilador escolhe as posições na memória.
Na ligação: O ligador (linker) pega os arquivos objeto criados pelo compilador e define os endereços.
Na carga: O carregador (loader) define os endereços de memória durante o carregamento.
Na execução: Os endereços emitidos pelo processador durante a execução do processo são analisados e convertidos nos endereços efetivos.

5) O espaço de memória é organizado da seguinte forma: TEXT, que contém o código binário a ser executado pelo processo; DATA, que contém as variáveis globais e variáveis estáticas inicializadas; BSS, que contém as variáveis estáticas não inicializadas; HEAP, que armazena variáveis alocadas dinamicamente, e que possui ao seu final um ponteiro chamado Program Break (ou só Break); STACK, que é usada para manter a pilha de execução do processo, os parâmetros, variáveis locais e o valor de retorno das funções.

6) Endereços lógicos são mapas que apontam para o endereço físico na memória. Seu uso é ótimo para versatilidade do uso da memória, já que não importando onde a informação seja salva, para o processador, ela será lida como uma linearidade, passando todo o trabalho da tradução da procura para o MMU. Além disso, há um aumento na segurança do acesso à memória, já que o processo não poderá acessar áreas das memórias de outros processos.

7) Em ordem: 91, 300, 90, fault error, 1400.

8)

9) (b) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.

10) Falta de página é o nome dado para quando o processador busca uma página na memória RAM e a mesma não se encontra no endereço buscado. Ela pode ocorrer quando a página foi movida para o disco para liberar espaço na RAM ou quando devido a um problema de mapeamento/gerência a mesma se encontra inválida/vazia. O sistema então busca checar nos bits de flag se a mesma é válida ou não (consequentemente se ela está apenas no disco), e a puxa do disco quando é ou aborta o processo quando não.
