## Respostas do Capítulo 20 - Software de entrada e saída  

1 - Porque entre dispositivos similares há centenas de modelos de diferentes fabricantes com interfaces distintas. Então acima dos drivers existe uma camada de código, denominada generic device interface, que tem a finalidade de contruir uma visão genérica dos dispositivos para que o sistema operacional não precise conhecer todas as características próprias de cada dispositivo mas possa tratá-los por famílias ou classes.

## Respostas do Capítulo 21 - Discos rígidos  

2 - RAID 0 (striping), RAID 1, RAID 5.

## Respostas do Capítulo 22 - O conceito de arquivo

3 - **Extensão do nome**: usar parte do nome do arquivo para indicar o tipo do conteúdo. Uma vantagem é a fácil identificação do tipo do arquivo pelo usuário.  
**Números mágicos**: usar alguns bytes no início do conteúdo do arquivo para a definição de seu tipo. Nos sistemas UNIX, o utilitário file permite identificar o tipo de arquivo através da análise de seus bytes iniciais e do restante de sua estrutura interna, sem levar em conta o nome do arquivo.   
**Atributos adicionais**: sistemas operacionais definem atributos adicionais no sistema de arquivos para identificar o conteúdo de cada arquivo.  
**Tipos MIME**:  define tipos de arquivos através de uma notação uniformizada na forma “tipo/subtipo”. É usado para identificar arquivos transferidos como anexos de e-mail e conteúdos obtidos de páginas Web.

4 - a) **Incorreta.** Porque um magic number corresponde ao bytes iniciais do arquivo para identificar seu tipo. Não é um atributo numérico separado.  
b) **Correta.**  
c) **Correta.**  
d) **Correta.**  
e) **Incorreta**. Ambos são arquivos de código. O ELF (Executable and Linking Format) é um formato de arquivo usado para programas executáveis e bibliotecas na maior parte das plataformas UNIX modernas. O PE (Portable Executable) é o formato usado para executáveis e bibliotecas na plataforma Windows.

## Respostas do Capítulo 23 - Uso de arquivos

5 - **Acesso sequencial**: os dados são sempre lidos e/ou escritos em sequência, do início ao final do arquivo. É o mais utilizado em quase todos os sistemas operacionais do mercado e é a forma mais usual de acesso a arquivos.  
**Acesso aleatório**: É indicado a posição no arquivos onde a leitura ou escrits deve ocorrer sem a necessidade do ponteiro que indica o início do arquivo (como no acesso sequencial). Assim caso já conheça a posição do dado no arquivo não há necessidade de percorrê-lo sequencialmente. É usado em gerenciadores de bancos de dados e aplicações congêneres (que precisam acessar rapidamente as posições do arquivo correspondetes ao registros desejados em uma operação).  
**Acesso mapeado em memória**: o arquivo é associado a um vetor de bytes (ou de registros) de mesmo tamanho na memória principal, de forma que cada posição do vetor corresponda à sua posição equivalente no arquivo. Usado pelo núcleo para carregar código executável (programas e bibliotecas) na memória.  
**Acesso indexado**: Os dados do arquivo são armazenados em registros com chaves (índices) associados a eles, e podem ser recuperados usando essas chaves, como em um banco de dados relacional. A maioria dos sistemas operacionai não implementa essa funcionalidade diretamente no núcleo, mas ela pode ser obtida através de bibliotecas como BerkeleyDB ou SQLite.  

6 - **Travas obrigatórias**: se um processo obtiver a trava de um arquivo, outros processos que solicitarem acesso ao mesmo arquivo serão suspensos até que aquela trava seja liberada.  
**Travas recomendadas**: não são impostas pelo núcleo do sistema operacional, mas gerenciadas pelo suporte de execução (bibliotecas). Os processos envolvidos no acesso aos mesmos arquivos devem travá-los explicitamente quando forem acessá-los.  
**Travas exclusivas**: enquanto uma trava exclusiva estiver ativa, nenhum outro processo poderá obter outra trava sobre o mesmo arquivo.  
**Travas compartilhadas**:  impedem outros processos de criar travas exclusivas sobre aquele arquivo, mas permitem a existência de outras travas compartilhadas.  

7 - **Semântica imutável**: de acordo com esta semântica, se um arquivo pode ser compartilhado por vários processos, ele é marcado como imutável, ou seja, seu conteúdo somente pode ser lido e não pode ser modificado.  
**Semântica UNIX**: toda modificação em um arquivo é imediatamente visível a todos os processos que mantêm aquele arquivo aberto. É a mais comum em sistemas de arquivos locais.  
**Semântica de sessão**: considera que cada processo usa um arquivo em uma sessão, que inicia com a abertura do arquivo e que termina com seu fechamento. Modificações em um arquivo feitas em uma sessão somente são visíveis na mesma seção e pelas sessões que iniciarem depois do encerramento da mesma.  
**Semântica de transação**: uma transação é uma sequência de operações de leitura e escrita em um ou mais arquivos emitidas por um processo e delimitadas por comandos de início e fim de transação (begin ... end). Todas as modificações parciais do arquivo durante a
execução de uma transação não são visíveis às demais transações, somente após sua conclusão.  

## Respostas do Capítulo 24 - Sistema de arquivos

8 - **Dispositivos**: Responsáveis pelo armazenamento de dados.  
**Controladores**: são os circuitos eletrônicos dedicados ao controle dos dispositivos físicos.  
**Drivers**: interagem com os controladores de dispositivos para configurá-los e realizar as
transferências de dados entre o sistema operacional e os dispositivos.  
**Gerência de blocos**: gerencia o fluxo de blocos de dados entre as camadas superiores e os dispositivos de armazenamento.
**Alocação de arquivos**: realiza a alocação dos arquivos sobre os blocos lógicos oferecidos
pela camada de gerência de blocos.  
**VFS (Virtual File System)**: constrói as abstrações de diretórios e atalhos, além de gerenciar as permissões associadas aos arquivos e
as travas de acesso compartilhado. Mantém o registro de cada arquivo aberto pelos processos.  
**Interface do sistema de arquivos**: conjunto de chamadas de sistema oferecidas aos processos do espaço de usuários para a criação e manipulação de arquivos.  
**Bibliotecas de entrada/saída**: usam as chamadas de sistema da interface do núcleo para construir funções padronizadas de acesso a arquivos para cada linguagem de programação.  

9 - No bitmap um pequeno conjunto de blocos na área reservada do volume é usado para manter um mapa de bits. Nesse mapa, cada bit
representa um bloco lógico da partição, que pode estar livre ou ocupado. Ele tem como vantagens ser simples de implementar e ser bem compacto.

## Respostas do Capítulo 25 - Diretórios e atalhos

10 - Uma diferença entre eles é o caractere separador de nomes no caminho. No sistema Windows usa como separador o caractere “\”, enquanto sistemas UNIX usam o caractere “/”. Outra diferença é que internamente a lista ou índice do diretório pode ser implementado como uma tabela simples como é o caso do MS-DOS e do Ext2(Linux). Essa implementação é mais simples porém possui baixo desempenho. Sistemas de arquivos mais sofisticados como o Ext4, ZFS e NTFS usam estrutura de dados com maior desempenho de busca como hashes e árvores.
