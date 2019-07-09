### Sistemas-Operacionais-2o-Bimestre-2019.1-parte2-Respostas
### Aluno: Emanoel Messias Gomes de Lima.

### Gestão de entradas e saídas
#### Capítulo 19 - Hardware de entrada/saída
#### Capítulo 20 - Software de entrada e saída
#### °Questões da avaliação
<b> (1) Livro Sistemas operacionais, série livros didáticos, editora bookman. Por que os sistemas
operacionais exigem de todos os drivers de disposito (device-drivers) a mesma interface padrão?
Não seria mais apropriado deixar cada driver de dispositivo definir rotinas de interface que fazem
sentido para aquele tipo específico de dispositivo?</b><br>
O sistema operacional é responsável por oferecer acesso aos dispositivos de
entrada/saída às aplicações e, em consequência, aos usuários do sistema. Prover acesso
eficiente, rápido e confiável a um conjunto de periféricos com características diversas de
comportamento, velocidade de transferência, volume de dados produzidos/consumidos
e diferentes interfaces de hardware é um enorme desafio. Além disso, como cada
dispositivo define sua própria interface e modo de operação, o núcleo do sistema
operacional deve implementar o código necessário para interagir com milhares de tipos
de dispositivos distintos.<br> 
A diversidade de dispositivos de E/S exige que o sistema operacional
implemente uma camada, chamada de subsistema de E/S, com a função de
isolar a complexidade dos dispositivos da camada de sistemas de arquivo e da
aplicação. Dessa forma, é possível ao sistema operacional ser flexível,
permitindo a comunicação dos processos com qualquer tipo de periférico.
Aspectos como velocidade de operação, unidade de transferência,
representação de dados, tipos de operações e demais detalhes de cada um
dos periféricos são tratados pela camada de device driver, oferecendo uma
interface uniforme entre o subsistema de E/S e todos os dispositivos. 

#### Capítulo 21 - Discos rígidos
#### ° Questões da avaliação
<b>(2) página 12, questão 3. Você tem 4 discos rígidos de 8 TB cada, que pode organizar de diversas
formas. Indique os arranjos RAID que escolheria para obter:</b><br>

<b>(a) O maior espaço útil de disco.</b><br>
RAID 5: assim como o RAID 4, esta abordagem também armazena informações de
paridade para tolerar falhas em blocos ou discos. Todavia, essas informações
não ficam concentradas em um único disco físico, sendo distribuídas uniformemente entre eles. A Figura 21.7 ilustra uma possibilidade de distribuição
das informações de paridade. Essa estratégia elimina o gargalo de desempenho
no acesso aos dados de paridade visto no RAID 4 (embora seja necessário, a
cada escrita, ler blocos de todos os discos para poder calcular o novo bloco
de paridade). Esta é uma abordagem de RAID popular, por oferecer um bom
desempenho e redundância de dados, desperdiçando menos espaço que o
espelhamento (RAID 1).

<b>(b) A maior tolerância a falhas de disco.</b><br>
RAID 1: neste nível, o conteúdo é replicado em dois ou mais discos, sendo por isso
comumente chamado de espelhamento de discos. A Figura 21.5 mostra uma
configuração usual deste nível de RAID, com dois discos físicos (embora não
seja usual, o conteúdo pode ser replicado em N discos, para tolerar N −1 falhas).<br>

<b>(c) A maior velocidade média de leitura.</b><br>
RAID 0 (striping): O maior espalhamento dos blocos sobre os discos físicos contribui para distribuir
melhor a carga de acessos entre eles e assim ter um melhor desempenho. Suas
características de suporte a grande volume de dados e alto desempenho em
leitura/escrita tornam esta abordagem adequada para ambientes que precisam processar grandes volumes de dados temporários, como os sistemas de
computação científica.

<b>(d) A maior velocidade média de escrita.</b><br>
RAID 0 (striping): O maior espalhamento dos blocos sobre os discos físicos contribui para distribuir
melhor a carga de acessos entre eles e assim ter um melhor desempenho. Suas
características de suporte a grande volume de dados e alto desempenho em
leitura/escrita tornam esta abordagem adequada para ambientes que precisam processar grandes volumes de dados temporários, como os sistemas de
computação científica.

<b>(e) Equilíbrio entre espaço útil, velocidades e tolerância a falhas.</b><br>
RAID 5: assim como o RAID 4, esta abordagem também armazena informações de
paridade para tolerar falhas em blocos ou discos. Todavia, essas informações
não ficam concentradas em um único disco físico, sendo distribuídas uniformemente entre eles. 
Essa estratégia elimina o gargalo de desempenho
no acesso aos dados de paridade visto no RAID 4 (embora seja necessário, a
cada escrita, ler blocos de todos os discos para poder calcular o novo bloco
de paridade). Esta é uma abordagem de RAID popular, por oferecer um bom
desempenho e redundância de dados, desperdiçando menos espaço que o
espelhamento (RAID 1).

Justifique/explique suas respostas.

#### Gestão de arquivos
#### Capítulo 22 - O conceito de arquivo
#### °Questões da avaliação
página 10
<b>(3) questão 3. Apresente e comente as principais formas de atribuição de tipos aos arquivos.
Quais são as vantagens e desvantagens de cada uma?</b><br>
<b>Sequência de bytes:</b> 
Em sua forma mais simples, um arquivo contém basicamente uma sequência de bytes.<br>
<b>Vanatagens-</b>
Essa sequência de bytes pode ser estruturada de forma a representar diferentes
tipos de informação, como imagens, música, textos ou código executável. Essa estrutura
interna do arquivo pode ser entendida pelo núcleo do sistema operacional ou somente
pelas aplicações que acessam esse conteúdo.<br>
<b>Desvantagens-</b>
Uma aplicação pode definir um formato próprio para armazenar seus dados, ou
pode seguir formatos padronizados.<br>
A adoção de um formato proprietário ou exclusivo limita o uso das
informações armazenadas, pois somente aplicações que reconheçam aquele formato
específico conseguem ler corretamente as informações contidas no arquivo.<br>
<b>Arquivos de registros:</b><br>
<b>Vanatagens-</b>
Alguns núcleos de sistemas operacionais oferecem arquivos com estruturas
internas que vão além da simples sequência de bytes. Por exemplo, o sistema OpenVMS
[Rice, 2000] proporciona arquivos baseados em registros, cujo conteúdo é visto pelas
aplicações como uma sequência linear de registros de tamanho fixo ou variável, e
também arquivos indexados, nos quais podem ser armazenados pares {chave/valor}, de
forma similar a um banco de dados relacional.<br>
<b>Desvantagens-</b>
Nos sistemas operacionais cujo núcleo não suporta arquivos estruturados
em registros, essa funcionalidade pode ser facilmente obtida através de bibliotecas
específicas ou do suporte de execução de algumas linguagens de programação.<br>
<b>Arquivos de texto:</b><br>
<b>Vantagens-</b>
Um tipo de arquivo de uso muito frequente é o arquivo de texto puro (ou plain
text). Esse tipo de arquivo é usado para armazenar informações textuais simples, como
códigos-fonte de programas, arquivos de configuração, páginas HTML, dados em XML,
etc.<br>
<b>Devantagens-</b>
 Diferenças na forma de representação da separação entre linhas pode
provocar problemas em arquivos de texto transferidos entre sistemas Windows e UNIX,
caso não seja feita a devida conversão.<br>
<b>Arquivos de código:</b><br>
<b>Vantagens-</b>
Em um sistema operacional moderno, um arquivo de código (programa executável ou biblioteca) é dividido internamente em várias seções, para conter código,
tabelas de símbolos (variáveis e funções), listas de dependências (bibliotecas necessárias)
e outras informações de configuração. A organização interna de um arquivo de código
depende do sistema operacional para o qual foi definido.<br>
<b>Desvantagens-</b>
Um problema importante relacionado aos formatos de arquivos é a correta identificação de seu conteúdo pelos usuários e aplicações.

<b>(4) questão 4. Sobre as afirmações a seguir, relativas a formatos de arquivos, indique quais
são incorretas, justificando sua resposta:<b>
  
##### (a) Um magic number consiste de um atributo numérico separado que identifica o tipo de arquivo.

Incorreta.<br>
Os magic numbers são bytes que fazem parte do início de um arquivo, não são atributos separados, possibilitando assim a identificação dosmesmos nos sistemas UNIX.

##### (b) A forma mais comum de identificação de tipo de arquivo é o uso de extensões ao seu nome.

Correta.

##### (c) Arquivos de texto em sistemas DOS e UNIX diferem nos caracteres de controle usados para identificar o fim de arquivo.

Incorreta.<br>
As diferenças nos caracteres de controle, influenciam em todo o arquivo. Por exemplo, um arquivo de texto criado em um sistema UNIX, não poderá ser abertoem um sistema DOS, sem a devida conversão, então não são usados para identificar o fim de um arquivo, mas sim a forma em que ele é interpretado pelo SO.<br>

##### (d) Para a maioria dos núcleos de sistema operacional, arquivos são quase sempre vistos como meras sequências de bytes.

Correeta.

##### (e) ELF e PE são dois formatos típicos de arquivos de configuração.

Incorreta.<br>
Os formatos, ELF e PE, São de Execução.<br>

ELF (Executable and Linking Format): formato de arquivo usado para programas
executáveis e bibliotecas na maior parte das plataformas UNIX modernas.<br>

PE (Portable Executable): é o formato usado para executáveis e bibliotecas na
plataforma Windows. <br>

##### (f) O padrão MIME é usado no Linux para identificação de tipos de arquivos pelo sistema operacional.

Correta.

#### Capítulo 23 - Uso de arquivos
#### °Questões da avaliação
página 13

##### (5) questão 3. Comente as principais formas de acesso a arquivos. Qual o uso mais apropriado para cada uma delas?

<b>Acesso sequencial-</b>
No acesso sequencial, os dados são sempre lidos e/ou escritos em sequência,
do início ao final do arquivo. Para cada arquivo aberto por uma aplicação é definido um
ponteiro de acesso, que inicialmente aponta para a primeira posição do arquivo. A cada
leitura ou escrita, esse ponteiro é incrementado e passa a indicar a posição da próxima
leitura ou escrita. Quando esse ponteiro atinge o final do arquivo, as leituras não são
mais permitidas, mas as escritas podem sê-lo, permitindo acrescentar dados ao final
do mesmo. A chegada do ponteiro ao final do arquivo é normalmente sinalizada ao
processo através de um flag de fim de arquivo (EoF – End-of-File).<br>
O acesso sequencial é implementado em praticamente todos os sistemas operacionais de mercado
e constitui a forma mais usual de acesso a arquivos, usada pela maioria das aplicações.<br>
<b>Acesso aleatório-</b>
No método de acesso aleatório (ou direto), pode-se indicar a posição no arquivo
onde cada leitura ou escrita deve ocorrer, sem a necessidade de um ponteiro de posição
corrente. Assim, caso se conheça previamente a posição de um determinado dado
no arquivo, não há necessidade de percorrê-lo sequencialmente até encontrar o dado
desejado. Essa forma de acesso é muito importante em gerenciadores de bancos de
dados e aplicações congêneres, que precisam acessar rapidamente as posições do arquivo
correspondentes ao registros desejados em uma operação.<br>
Na prática, a maioria dos sistemas operacionais usa o acesso sequencial como
modo básico de operação, mas oferece operações para mudar a posição do ponteiro
de acesso do arquivo caso necessário, o que permite então o acesso direto a qualquer
registro do arquivo.<br>
<b>Acesso mapeado em memória-</b>
Uma forma particular de acesso aleatório ao conteúdo de um arquivo é o
mapeamento em memória do mesmo, que faz uso dos mecanismos de paginação em disco.
Nessa modalidade de acesso, o arquivo é associado a um vetor
de bytes (ou de registros) de mesmo tamanho na memória principal, de forma que
cada posição do vetor corresponda à sua posição equivalente no arquivo. Quando uma
posição específica do vetor na memória é lida pela primeira vez, é gerada uma falta de
página. Nesse momento, o mecanismo de memória virtual intercepta o acesso à memória,
lê o conteúdo correspondente no arquivo e o deposita no vetor, de forma transparente
à aplicação, que em seguida pode acessá-lo. Escritas no vetor são transferidas para
o arquivo por um procedimento similar. Caso o arquivo seja muito grande, pode-se
mapear em memória apenas partes dele.<br>
O acesso mapeado em memória é extensivamente usado pelo núcleo para
carregar código executável (programas e bibliotecas) na memória. Como somente as
partes efetivamente acessadas do código serão carregadas em RAM, esse procedimento
é usualmente conhecido como paginação sob demanda (demand paging), pois os dados são
lidos do arquivo para a memória em páginas.<br>
<b>Acesso indexado-</b>
Alguns sistemas operacionais oferecem também a possibilidade de acesso
indexado aos dados de um arquivo, como é o caso do OpenVMS [Rice, 2000]. Esse
sistema implementa arquivos cuja estrutura interna pode ser vista como uma tabela
de pares chave/valor. Os dados do arq.<br>
Como o próprio núcleo desse sistema implementa os mecanismos de acesso
e indexação do arquivo, o armazenamento e busca de dados nesse tipo de arquivo
costuma ser muito rápido, dispensando bancos de dados para a construção de aplicações
mais simples. A maioria dos sistemas operacionais de mercado não implementa essa
funcionalidade diretamente no núcleo, mas ela pode ser facilmente obtida através de
bibliotecas populares como BerkeleyDB ou SQLite.uivo são armazenados em registros com chaves
(índices) associados a eles, e podem ser recuperados usando essas chaves, como em um
banco de dados relacional.<br>
Como o próprio núcleo desse sistema implementa os mecanismos de acesso
e indexação do arquivo, o armazenamento e busca de dados nesse tipo de arquivo
costuma ser muito rápido, dispensando bancos de dados para a construção de aplicações
mais simples. A maioria dos sistemas operacionais de mercado não implementa essa
funcionalidade diretamente no núcleo, mas ela pode ser facilmente obtida através de
bibliotecas populares como BerkeleyDB ou SQLite.
##### (6) questão 4. Apresente e explique os quatro principais tipos de travas sobre arquivos compartilhados disponíveis no sistema operacional.

<b>Travas obrigatórias-</b> (mandatory locks): são impostas pelo núcleo de forma incontornável:
se um processo obtiver a trava de um arquivo, outros processos que solicitarem
acesso ao mesmo arquivo serão suspensos até que aquela trava seja liberada. É
o tipo de trava mais usual em sistemas Windows.<br>

<b>Travas recomendadas-</b> (advisory locks): não são impostas pelo núcleo do sistema operacional, mas gerenciadas pelo suporte de execução (bibliotecas). Os processos
envolvidos no acesso aos mesmos arquivos devem travá-los explicitamente
quando forem acessá-los. Contudo, um processo pode ignorar essa regra e
acessar um arquivo ignorando a trava, caso necessário. Travas recomendadas
são úteis para gerenciar concorrência entre processos de uma mesma aplicação.
Neste caso, cabe ao programador implementar os controles necessários nos
processos para impedir acessos conflitantes aos arquivos compartilhados.<br>

<b>Travas exclusivas-</b> (ou travas de escrita): garantem acesso exclusivo ao arquivo: enquanto
uma trava exclusiva estiver ativa, nenhum outro processo poderá obter outra
trava sobre o mesmo arquivo.<br>

<b>Travas compartilhadas-</b> (ou travas de leitura): impedem outros processos de criar travas
exclusivas sobre aquele arquivo, mas permitem a existência de outras travas
compartilhadas.

##### (7) questão 5. Apresente e explique as quatro principais semânticas de acesso a arquivos compartilhados em um sistema operacional.

<b>Semântica imutável:</b> de acordo com esta semântica, se um arquivo pode ser compartilhado por vários processos, ele é marcado como imutável, ou seja, seu
conteúdo somente pode ser lido e não pode ser modificado. É a forma mais
simples de garantir a consistência do conteúdo do arquivo entre os processos
que compartilham seu acesso, sendo por isso usada em alguns sistemas de
arquivos distribuídos.<br>

<b>Semântica UNIX:</b> toda modificação em um arquivo é imediatamente visível a todos os
processos que mantêm aquele arquivo aberto; Essa semântica é a mais comum
em sistemas de arquivos locais, ou seja, para acesso a arquivos nos dispositivos
locais;<br>

<b>Semântica de sessão:</b> considera que cada processo usa um arquivo em uma sessão,
que inicia com a abertura do arquivo e que termina com seu fechamento.
Modificações em um arquivo feitas em uma sessão somente são visíveis na
mesma seção e pelas sessões que iniciarem depois do encerramento da mesma,
ou seja, depois que o processo fechar o arquivo; assim, sessões concorrentes
de acesso a um arquivo compartilhado podem ver conteúdos distintos para o
mesmo arquivo. Esta semântica é normalmente aplicada a sistemas de arquivos
de rede, usados para acesso a arquivos em outros computadores;<br>

<b>Semântica de transação:</b> uma transação é uma sequência de operações de leitura e
escrita em um ou mais arquivos emitidas por um processo e delimitadas por
comandos de início e fim de transação (begin ... end), como em um sistema
de bancos de dados. Todas as modificações parciais do arquivo durante a
execução de uma transação não são visíveis às demais transações, somente
após sua conclusão. Pode-se afirmar que a semântica de transação é similar à
semântica de sessão, mas aplicada a cada transação (sequência de operações) e
não ao período completo de uso do arquivo (da abertura ao fechamento).

#### Capítulo 24 - Sistemas de arquivos
#### °Questões da avaliação
##### (8) página 20, questão 1. Apresente a arquitetura de gerência de arquivos presente em um sistema operacional típico, explicando seus principais elementos constituintes.
Os principais elementos que realizam a implementação de arquivos no sistema
operacional estão organizados em camadas, sendo apresentados a seguir:<br>
<b>Dispositivos:</b> como discos rígidos ou bancos de memória flash, são os responsáveis
pelo armazenamento de dados.<br>

<b>Controladores:</b> são os circuitos eletrônicos dedicados ao controle dos dispositivos
físicos. Eles são acessados através de portas de entrada/saída, interrupções e
canais de acesso direto à memória (DMA).<br>

</b>Drivers:</b> interagem com os controladores de dispositivos para configurá-los e realizar as
transferências de dados entre o sistema operacional e os dispositivos. Como cada
controlador define sua própria interface, também possui um driver específico.
Os drivers ocultam as diferenças entre controladores e fornecem às camadas
superiores do núcleo uma interface padronizada para acesso aos dispositivos
de armazenamento.<br>

<b>Gerência de blocos:</b> gerencia o fluxo de blocos de dados entre as camadas superiores e
os dispositivos de armazenamento. Como os discos são dispositivos orientados
a blocos, as operações de leitura e escrita de dados são sempre feitas com
blocos de dados, e nunca com bytes individuais. As funções mais importantes
desta camada são efetuar o mapeamento de blocos lógicos nos blocos físicos do
dispositivo e o caching/buffering de blocos.<br>

<b>Alocação de arquivos:</b> realiza a alocação dos arquivos sobre os blocos lógicos oferecidos
pela camada de gerência de blocos. Cada arquivo é visto como uma sequência
de blocos lógicos que deve ser armazenada nos blocos dos dispositivos de forma
eficiente, robusta e flexível.<br>

<b>Sistema de arquivos virtual:</b> o VFS (Virtual File System) constrói as abstrações de diretórios e atalhos, além de gerenciar as permissões associadas aos arquivos e
as travas de acesso compartilhado. Outra responsabilidade importante desta
camada é manter o registro de cada arquivo aberto pelos processos, como a
posição da última operação no arquivo, o modo de abertura usado e o número
de processos que estão usando o arquivo.<br>

<b>Interface do sistema de arquivos:</b> conjunto de chamadas de sistema oferecidas aos
processos do espaço de usuários para a criação e manipulação de arquivos.<br>

<b>Bibliotecas de entrada/saída:</b> usam as chamadas de sistema da interface do núcleo
para construir funções padronizadas de acesso a arquivos para cada linguagem
de programação.<br>

A maior parte da implementação do sistema de arquivos está
localizada dentro do núcleo, mas isso obviamente varia de acordo com a arquitetura do
sistema operacional. Em sistemas micronúcleo,por exemplo, as camadas de
gerência de blocos e as superiores provavelmente estariam no espaço de usuário.

##### (9) página 23, questão 18. Explique como é efetuada a gerência de espaço livre através de bitmaps.
Na abordagem de mapa de bits, um pequeno conjunto de blocos na área
reservada do volume é usado para manter um mapa de bits. Nesse mapa, cada bit
representa um bloco lógico da partição, que pode estar livre ou ocupado.<br>
O mapa de bits tem como vantagens ser simples de implementar e ser bem compacto:
em um disco de 500 GBytes com blocos lógicos de 4.096 bytes, seriam necessários
131.072.000 bits no mapa, o que representa 16.384.000 bytes, ocupando 4.000 blocos (ou
seja, 0,003% do total de blocos lógicos do disco).

#### Capítulo 25 - Diretórios e atalhos
#### °Questões da avaliação
##### (10) página 10, questão 2. Do ponto de vista lógico, quais as principais diferenças entre a estrutura de diretórios Unix e Windows?
No Linux e Unix tudo é um arquivo. Diretórios são arquivos, arquivos são arquivos, e dispositivos são arquivos. Dispositivos são geralmente referidos por nódulos; entretanto, eles ainda são arquivos.<br>

Sistemas de arquivos do Linux e Unix são organizados em uma hierarquia, estilo estrutura de árvore. O nível mais alto do sistema de arquivos é o / ou diretório raiz. Todos os outros arquivos e diretórios existem sob o diretório root.

Sob o diretório root (/) existe um grupo de diretórios comuns à maioria das distribuições Linux.

Em Linux um nome completo deve começar com a barra, como em /home/alunos/fulano/programas/aed1/alomundo.pas. A barra inicial identifica o diretório raiz.

Em Windows, os sistemas de arquivos contém um outro tipo de subdivisão, os drives. Cada drive contém um diretório raiz, que contém subdiretórios e arquivos. Drives são identificados por uma única letra seguida do sinal de dois pontos. Assim, um exemplo de nome completo no Windows é algo como Z:\programas\aed1\alomundo.pas.<br>

O caractere separador de nomes no caminho depende do sistema operacional.
Por exemplo, o sistema Windows usa como separador o caractere “\”, enquanto sistemas
UNIX usam o caractere “/”;,<br>

Windows: Todas as partições existentes no disco são "descobertas" e iniciadas no momento do boot do computador e cada uma recebe uma letra para representação, como C:, D:, etc. O Windows NT (incluindo W2k) vem com o NT Loader, que referencia o setor de boot incluindo múltiplos sistemas operacionais, para partições NTFS. <nr>

Linux: No Linux as partições não são conhecidas até que alguém as monte. Talvez isso não seja a melhor maneira, porém é bem mais flexível do que os demais sistemas operacionais. O Linux conta com ferramentas como o LILO (LInux LOader) e GRUB (GRand, Unified Bootloader) para gerenciar o setor de boot e fazer a carga não só do Linux, mas de outros sistemas operacionais que possam existir no HD. 









