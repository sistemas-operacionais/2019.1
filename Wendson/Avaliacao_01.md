Respostas

Questão 01
Abstração de Recursos e Gerência de Recursos.

Questão 02
Porque prover aos desenvolvedores um ambiente com interfaces mais simples para simplificar a construção de programas e aplicativos,
deixando-os independentes de hardware permitindo aos aplicativos usarem a mesma interface para dispositivos diversos.

Questão 03
Distribuir capacidade de processamento de forma justa entre as aplicações, com isso evita que uma aplicação monopolize esse recurso
respeitando as prioridades dos usuários, fornece também abstrações para sincrônizar atividades interdependentes e prover formas de
comunicação entre elas.

Questão 04
O que caracteriza um Sistema Operacional em Tempo Real e ter um comportamento temporal previsível.
Suas classificações são: soft real-time systems e hard real-time systems.
No sistema soft real-time sistems a perda de prazos na degradação do serviço prestado.
E no sistema hard real-time systems a perda de prazos pelo sisema pode pertubar o objeto controlado, com graves consequências
humans, ecônomicas ou ambientais.

Questão 05
Núcleo tem acesso completo a todo o hardware e pode executar qualquer instrução que a máquina for capaz de executar.
Já o restante do Sistema Operacional opera em modo Usuário onde apenas um subconjuto das intruções da máquina está disponivel.

Questão 06
Construir um sistema operacional seguro usando um processador sem níveis de privilégios não seria possível. Por que sem níveis 
de privilégios os utilitários e aplicativos iriam interferir nas configurações e na gerência, com isso acabaria desestabilizando
o sistema inteiro.

Questão 07
Sim! Se houvesse a divisão de processos entre o níveis.

Questão 08
Difernças entre:
Interrupção: Uma interrupção é sempre gerada por um evento externo ao programa e, sendo assim, independe da instrução que está sendo
executada.
Execeções: A exceção é um evento semelhante à interrupção, pois também de fato interrompe um programa. Sendo que a exceção é o resultado da execução de uma instrução dentro do próprio programa.
Traps: uma instrução especial implementada pelos processadores que permite acionar o mecanismo de interrupção de forma intencional,
sem depender de eventos externos ou internos. com isso comuta o processador para o nível privilegiado e procede de forma similar ao tratamento de uma interrupção.

Questão 09


Questão 10
É uma função pois pertence a biblioteca stdio.h. 



Questão 11

ARQUITETURA 	BENEFÍCIO 	DEFICIÊNCIA 
Monolíticos 	Interação entre componentes(maior desempenho) 	Maior facilidade de colapso do sistema. 
Camadas 	Organização de execução de atividades em camas 	Baixo desempenho devido fragmentação da execução. 
Micronúcleo 	Robustez e flexibilidade	Baixo desempenho devido o custo de trocas de mensagens entre componentes ser bastante elevado.

Questão 12
[T] Deve ter um comportamento temporal previsível, com prazos de resposta
claramente definidos.
[S] Sistema operacional usado por uma empresa para executar seu banco de
dados corporativo.
[E] São tipicamente usados em telefones celulares e sistemas eletrônicos dedicados.
[D] Neste tipo de sistema, a localização física dos recursos do sistema computacional
é transparente para os usuários.
[M] Todos os recursos do sistema têm proprietários e existem regras controlando
o acesso aos mesmos pelos usuários.
[K] A gerência de energia é muito importante neste tipo de sistema.
[K] Sistema que prioriza a gerência da interface gráfica e a interação com o
usuário.
[S] Construído para gerenciar de forma eficiente grandes volumes de recursos.
[E] O MacOS X é um exemplo típico deste tipo de sistema.
[E] São sistemas operacionais compactos, construídos para executar aplicações
específicas sobre plataformas com poucos recursos.



Questão 13
As operações abaixo citadas não deveriam ser executadas pelo usuário, pois poderia causar danos muito graves ao sistema operacional caso executasse uma operação errada.

(a) Ler uma porta de entrada/saída
(c) Escrever um valor em uma posição de memória
(e) Ler o valor dos registradores do processador
(f) Mascarar uma ou mais interrupções

Questão 14
Para que as seguintes ações do processo possam ser realizadas através de chamadas de sistema os processadores implementam um instrução especial que permite acionar o mecanismo de interrupção de forma intencional, sem que dependa de eventos internos ou externos. Com isso, ao ser executada, essa instrução comuta o processador para o nível de privilegiado e procede de forma similar ao tratamento de uma interrupção.

(a) Ler o relógio de tempo real do hardware.
(b) Enviar um pacote através da rede.
(d) Preencher uma área de memória do processo com zeros.

Questão 15

[4] A rotina de tratamento da interrupção de software é ativada dentro do núcleo. 
[6] A função printf finaliza sua execução e devolve o controle ao código do processo. 
[2] A função de biblioteca printf recebe e processa os parâmetros de entrada (a string “Hello world”). 
[ ] A função de biblioteca printf prepara os registradores para solicitar a chamada de sistema write() 
[ ] O disco rígido gera uma interrupção indicando a conclusão da operação. 
[ ] O escalonador escolhe o processo mais prioritário para execução. 
[3] Uma interrupção de software é acionada. 
[1] O processo chama a função printf da biblioteca C. 
[5] A operação de escrita no terminal é efetuada ou agendada pela rotina de tratamento da interrupção. 
[ ] O controle volta para a função printf em modo usuário

Questão 16

(b) Apenas a afirmação V está correta.

Questão 17

(e) As afirmações II e V estão corretas.
Questão18

precisa fazer um SYSCALL para que seja gerada uma interrupção para executar o processo desejado e retornar ao aplicativo os dados solicitados.

Questão 19

