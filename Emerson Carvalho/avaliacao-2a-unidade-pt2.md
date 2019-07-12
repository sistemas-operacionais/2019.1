# Avaliação 2o Bimestre S.O - Parte 2
### Emerson Breno Martins Carvalho

### Gestão de entradas e saídas - Capítulo 20 - Software de entrada e saída
#### (1) Q1: Por que os sistemas operacionais exigem de todos os drivers de dispositivo (device-drivers) a mesma interface padrão? Não seria mais apropriado deixar cada driver de dispositivo definir rotinas de interface que fazem sentido para aquele tipo específico de dispositivo?
#### R:
- O sistemas operacionais exigem que os todos os drivers de dispositivo tenham a mesma interface pois será necessário que esses drivers funcionem de "forma universal", para que o sistema operacional não tenha que saber todas as peculiaridades de cada dispositivo instalado.  


###  Gestão de entradas e saídas - Capítulo 21 - Discos rígidos 
#### (2) Q3:  Você tem 4 discos rígidos de 8 TB cada, que pode organizar de diversas formas. Indique os arranjos RAID que escolheria para obter:
#### - ( a ) O maior espaço útil de disco. 
#### R:  RAID 0
#### - ( b ) A maior tolerância a falhas de disco. 
#### R: RAID 6
#### - ( c ) A maior velocidade média de leitura. 
#### R: RAID 3
#### - ( d ) A maior velocidade média de escrita. 
#### R: RAID 3
#### - ( e ) Equilíbrio entre espaço útil, velocidades e tolerância a falhas.
#### R:  RAID 5

### Gestão de arquivos - Capítulo 22 - O conceito de arquivo
#### (3) Q3: Apresente e comente as principais formas de atribuição de tipos aos arquivos. Quais são as vantagens e desvantagens de cada uma?
#### R: 
Temos a extensão por nome e os números mágicos. 
- Extensão por nome: Nesse tipo de abordagem a atribuição do tipo é feita através do próprio nome do arquivo.
- Números Mágicos (Magic Numbers):  Nesse tipo de abordagem  a atribuição é feita em nível de bytes, onde alguns dos bytes no inicio do arquivo são selecionados para definir o formato.

#### (4) Q4: Sobre as afirmações a seguir, relativas a formatos de arquivos, indique quais são incorretas, justificando sua resposta:
#### R:
#### - ( a ) Um magic number consiste de um atributo numérico separado que identifica o tipo de arquivo. - Correto
#### - ( b ) A forma mais comum de identificação de tipo de arquivo é o uso de extensões ao seu nome.  - Correto 
#### - ( c ) Arquivos de texto em sistemas DOS e UNIX diferem nos caracteres de controle usados para identificar o fim de arquivo. - Errado, a diferença está nos caracteres que controlam o fim da linha.
#### - ( d ) Para a maioria dos núcleos de sistema operacional, arquivos são quase sempre vistos como meras sequências de bytes. - Correto
#### - ( e ) ELF e PE são dois formatos típicos de arquivos de configuração. - Errado, são arquivos de código.
#### - ( f ) O padrão MIME é usado no Linux para identificação de tipos de arquivos pelo sistema operacional. - Errado.

### Gestão de arquivos - Capítulo 23 - Uso de arquivos
#### (5) Q3: Comente as principais formas de acesso a arquivos. Qual o uso mais apropriado para cada uma delas?
#### R: 
- Acesso Sequencial: nessa forma de acesso os arquivos são lidos de forma sequencial do inicio ao fim do arquivo.
- Acesso aleatório:  nessa forma de acesso os arquivos é possível que seja indicada a posição no arquivo onde cada leitura ou escrita deve ocorrer.
- Acesso mapeado em memória:  esse é uma forma particular de acesso aleatório onde mecanismos de paginação são utilizados. Nessa modalidade o arquivo é associado a um vetor de bytes do tamanho da memória principal, e cada posição do vetor corresponde à sua posição equivalente no arquivo.
- Acesso indexado: nessa forma de acesso os arquivos são implementados com uma estrutura interna na forma de uma tabela de pares chave/valor. Os dados são salvos em registros com chaves associados a eles, para recupera-los as chaves são utilizadas. Processos que estejam envolvidos no acesso a um mesmo arquivo devem travá-lo explicitamente no momento do acesso.

#### (6) Q4: Apresente e explique os quatro principais tipos de travas sobre arquivos compartilhados disponíveis no sistema operacional.
#### R:
- Travas obrigatórias: são travas impostas pelo núcleo do S.O de forma incontornável, quando um processo obtém a trava de um arquivo, qualquer outro processo que solicite acesso ao mesmo arquivo será suspenso até que a trava seja liberada.
- Travas recomendadas: essa travas não são impostas pelo núcleo do S.O, são gerenciadas por bibliotecas. 
- Travas exclusivas: nessa forma de acesso os processos que possuem a trava ativa do arquivo ganham acesso exclusivo e nenhuma outra trava é liberada no momento do acesso.
-  Travas compartilhadas: servem para impedir que outros processos criem travas exclusivas sobre o arquivo com trava compartilhada.

#### (7) Q5: Apresente e explique as quatro principais semânticas de acesso a arquivos compartilhados em um sistema operacional.
#### R: 
- Semântica imutável: nessa semântica se um arquivo pode ser compartilhado por vários processos, ele é imutável, ou seja, é um arquivo somente leitura, seu conteúdo não pode ser modificado.
- Semântica UNIX:  toda modificação em um arquivo é imediatamente visível a todos os processos que mantêm aquele arquivo aberto.
- Semântica de sessão: considera que cada processo usa um arquivo em uma sessão, que inicia com a abertura do arquivo e que termina com seu fechamento. 
- Semântica de transação: uma transação é uma sequência de operações de leitura e escrita em um ou mais arquivos emitidas por um processo e delimitadas por comandos de início e fim de transação (begin ... end), como em um sistema de bancos de dados.

### Gestão de arquivos - Capítulo 24 - Sistemas de arquivos
#### (8) Q1: Apresente a arquitetura de gerência de arquivos presente em um sistema operacional típico, explicando seus principais elementos constituintes.
#### R:
A arquitetura de gerência em um sistema operacional típico é organizada em camadas, abaixo as explicarei:
- Dispositivos: como discos rígidos ou bancos de memória flash, são os responsáveis pelo armazenamento de dados.
- Controladores: são os circuitos eletrônicos dedicados ao controle dos dispositivos físicos. Eles são acessados através de portas de entrada/saída, interrupções e canais de acesso direto à memória (DMA).
- Drivers: interagem com os controladores de dispositivos para configurá-los e realizar as transferências de dados entre o sistema operacional e os dispositivos. Como cada controlador define sua própria interface, também possui um driver específico. Os drivers ocultam 
- as diferenças entre controladores e fornecem às camadas superiores do núcleo uma interface padronizada para acesso aos dispositivos de armazenamento.
- Gerência de blocos: gerencia o fluxo de blocos de dados entre as camadas superiores e os dispositivos de armazenamento. Como os discos são dispositivos orientados a blocos, as operações de leitura e escrita de dados são sempre feitas com blocos de dados, e nunca com bytes individuais. As funções mais importantes desta camada são efetuar o mapeamento de blocos lógicos nos blocos físicos do dispositivo e o caching/buffering de blocos.
- Alocação de arquivos: realiza a alocação dos arquivos sobre os blocos lógicos oferecidos pela camada de gerência de blocos. Cada arquivo é visto como uma sequência de blocos lógicos que deve ser armazenada nos blocos dos dispositivos de forma eficiente, robusta e flexível.
- Sistema de arquivos virtual: o VFS (Virtual File System) constrói as abstrações de diretórios e atalhos, além de gerenciar as permissões associadas aos arquivos e as travas de acesso compartilhado. Outra responsabilidade importante desta camada é manter o registro de cada arquivo aberto pelos processos, como a posição da última operação no arquivo, o modo de abertura usado e o número de processos que estão usando o arquivo.
- Interface do sistema de arquivos: conjunto de chamadas de sistema oferecidas aos processos do espaço de usuários para a criação e manipulação de arquivos.
- Bibliotecas de entrada/saída: usam as chamadas de sistema da interface do núcleo para construir funções padronizadas de acesso a arquivos para cada linguagem de programação.

#### (9) Q18: Explique como é efetuada a gerência de espaço livre através de bitmaps.
#### R:
- Na gerência de espaço livre através de bitmaps, um mapa de bits é mantido em um pequeno conjunto de blocos na área reservada do volume. Onde cada bit representa um bloco lógico da partição, que pode estar livre ou ocupado.

### Gestão de arquivos - Capítulo 25 - Diretórios e atalhos
#### (10) Q2: Do ponto de vista lógico, quais as principais diferenças entre a estrutura de diretórios Unix e Windows?
#### R:
- As principais diferenças seriam os caracteres separadores de diretórios e a referência utilizada na definição do root. Por exemplo, no UNIX o caractere separador é o "/" e no windows é o "\".
