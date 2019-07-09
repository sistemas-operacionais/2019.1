Wanderson Costa da Silva Av2 (1 a 10)

Q1) as abordagens possíveis para resolvê-lo são:
Eliminar tarefas de modo a romper os ciclos, selecionar tarefas de acordo com alguma regra, como eliminar as mais antigas, menos prioritarias, mais lentas de acordo com as necessidades.
Retroceder tarefas, retornando o sistema a um estado seguro, como uso de backups para retorno ao um ponto onde não havia o impasse.

Q3) Exclusão mútua : os carros não podem acessar a mesma lacuna da pista por ser mão unica;
Posse e espera : requer que o outro carro libere a pista;
Não-preempção : pista so é liberada quando o carro pode proseguir;
Espera circular : carros requerendo as pistas em que outro carro esta;
poderiam adotar uma regra de dar a preferencia de quem vem a esquerda e sempre mantendo um quadrado de distancia do carro a frente.

Q4) Na codificação: o programador escolhe o endereço de cada uma das variáveis e do código do programa na memória;
Na compilação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória;
Na ligação: pega os arquivos objetos com suas tabelas de símbolos, define os endereços de memória dos símbolos e gera o programa executável;
Na carga: também é possível definir os endereços de variáveis e de funções durante a carga do código em memória para o lançamento de um novo processo;
Na execução: os endereços emitidos pelo processador durante a execução do processo são analisados e convertidos nos endereços efetivos a serem acessados na memória real.

Q5) Em várias áreas:
TEXT: código binário (executável);
DATA: variáveis globais/estáticas inicializadas;
BSS: Block Started by Symbol, variáveis globais não inicializadas;
HEAP: dados alocados dinamicamente (malloc); tem tamanho variável (ponteiro program break);
STACK: pilha de execução; tem tamanho variável e cresce “para baixo”;

Q6) Endereços físicos : endereços acessadas na memória RAM;
Endereços lógicos : endereços gerados pelo processador ao executar;
Seu uso vem de sua versatilidade do uso da memória, já que não importando onde a informação seja salva, para o processador, ela será lida como uma linearidade, passando todo o trabalho da tradução da procura para o MMU. Além disso, há um aumento na segurança do acesso à memória, já que o processo não poderá acessar áreas das memórias de outros processos.

Q7) 91, 300, 90, fault error, 1400.

Q9) Resp. (b)

Q10) uma interrupção gerada quando se tenta acessar uma pagna em um espaço no qual ela não esta alocada, quando a pagina é movida para liberação de espaço ou erro no mapeamento.
