>### Capítulo 20 - Software de entrada e saída

#### Questão 1.

* Devido as inúmeras semelhanças de dispositivo, existe por sua vez, 
muitos modelos de diferentes fabricantes com IO (Interface) divergentes. Então acima dos drivers existe uma camada de código,
denominado (GDI) Dispositivo Generico de Interface, deste modo, tornar-se mais fácil conter uma generalização entre os dispostivos,
fazendo então uma alusão ao sistema operacional a ponto dele não precisar conhecer total caracteristicas de cada dispositivo, 
mas ainda podendo acontecendo o tratamento dos mesmos seja por famílias ou até classes.

---

>### Capítulo 21 - Discos rígidos

#### P. 12 Questão 3.

| Arranjos RAID     |
|-------------------|
| RAID 0 (Striping) |
| RAID 1            |
| RAID 5            |

---

>### Capítulo 22 - O conceito de arquivo

#### P. 10 Questão 3.

* Pode-se atribuir o tipo do arquivo das seguintes maneiras  

**1. Extensão do nome:** O nome do arquivo possui uma parte indicativa com o tipo do conteúdo. Vantagens de adicionar o indicativo é o fácil entendimento do usuário.  
**2. Números mágicos:**  Utilização de alguns bytes no inicio do conteúdo do arquivo para definir o seu tipo. Trata-se como vantagem a utilização 
dos sistemas UNIX, onde o utilitário file permite identificar o tipo de arquivo através da análise de bytes iniciais, sem levar em conta o nome do arquivo.  
**3. Atributos adicionais:**  Os S.O's definem os atributos adicionais no (File) ou SDA (Sistema de Arquivos) para identificar o conteúdo de cada arquivo presente.  
**4. Tipos MIME:** São definidos os tipos de arquivo através de uma notação uniformizada na forma “tipo/subtipo”. Geralmente, é utilizada para identificar arquivos transferidos como anexos de e-mail e conteúdos obtidos de páginas web.  

#### P. 10 Questão 4.

* A) Incorreta. Justificativa: Um magic number (número mágico) é correspondente aos bytes iniciais do arquivo usados para identificar seu tipo, e não um atributo numérico separado.
* C) Incorreta. Justificativa: UNIX usam bytes inseridos no começo do arquivo, em vez de caracteres inseridos no final. 
* E) Incorreta. Justificativa: Tanto um quanto o outro são arquivos de código. O ELF (Executable and Linking Format) é um formato de arquivo usado para programas executáveis e bibliotecas na maior parte das plataformas UNIX modernas. O PE (Portable Executable) é o formato usado para executáveis e bibliotecas na plataforma Windows.

---

>### Capítulo 23 - Uso de arquivos

#### P. 13 Questão 3.

* Acesso sequencial: Neste tipo de acesso, os dados são lidos ou escritos de maneira sequencial, do início até o final do arquivo. É o mais popular e utilizado em quase todos os S.O's do mercado e a forma mais usual de acesso aos arquivos.
* Acesso aleatório: Neste tipo de acesso, a posição no arquivos de leitura são indicadas onde a leitura ou escrita deve ocorrer sem a necessidade do ponteiro que indica o início do arquivo. Deste modo, quando conhecida a posição do dado no arquivo não há necessidade de percorrer sequencialmente todo o arquivo. É usado em gerenciadores de bancos de dados.
* Acesso mapeado em memória: Neste tipo de acesso, o arquivo é associado a um vetor de bytes de mesmo tamanho na memória principal, de forma que cada posição do vetor corresponda à sua posição equivalente no arquivo. É usado pelo núcleo para carregar código executável software e library na memória.
* Acesso indexado: Neste tipo de acesso, os dados do arquivo são armazenados em registros com chaves (keys) associados a eles, um conceito parecido com o HashMap do Java, e podem ser recuperados usando essas chaves. A maioria dos sistemas operacionai não implementa essa funcionalidade diretamente no núcleo.

#### P. 13 Questão 4.

* Travas obrigatórias: Uma vez que um processo obtiver a trava de um arquivo, outros processos que solicitam acesso 
ao mesmo arquivo serão suspensos até que aquela trava seja liberada.
* Travas recomendadas: Estas são impostas pelo próprio núcleo do S.O, entretanto, são gerenciadas pelo suporte da execução um exemplo
deste suporte são as bibliotecas. São muitos os processos envolvendo o acesso dos mesmos arquivos, todavia, devem travá-los explicitamente quando forem acessá-los.
* Travas exclusivas: Funciona como um valor booleano, se uma trava exclusiva estiver ativa, nenhum outro processo poderá obter outra trava sobre o mesmo arquivo.
* Travas compartilhadas: Estas por sua vez, impedem outros processos de criarem travas 
exclusivas sobre aquele determinado arquivo, por outro lado, permitem a existência de outras travas compartilhadas.

#### P. 13 Questão 5.

* Semântica imutável: Em sua definição, um arquivo quando compartilhado entre vários processos, este arquivo não pode ser alterado, only read (apenas leitura). De tal forma que, arquivos compartilhados recebem a marcação de imutáveis, garantido total integridade do conteúdo;  

* Semãntica UNIX: Em sua definição, um arquivo quando modificado é imediatamente modificado em todos os outros processos que possuem o arquivo aberto;  

* Semântica de sessão: Em sua definição, cada processo que usar o arquivo deverá trabalhar com o mesmo em uma sessão, tal sessão se inicia com a abertura do arquivo e seu encerramento acontece com o fechamento. O contéudo centrato no arquivo é determinado pela última sessão ativa, pois nesta, aconetece a última atualização;  

*  Semântica de transação: Em sua definição, trata-se de um conceito parecido com o de semântica de sessão, sua diferença acontece no momento que um conjunto de operações é realizada o arquivo é atualizado. Todas as modificações parciais do arquivo durante a execução de uma transação não são visíveis às demais transações, somente após sua conclusão;   

---

>### Capítulo 24 - Sistemas de arquivos

#### P. 20 Questão 1.

* Dispositivos: Responsáveis pelo armazenamento dos dados. Exemplos de dispositivos: discos rígidos e bancos de memória flash;  

* Controladores: São constituídos por circuitos eletrônicos dedicados ao controle dos dispositivos físicos. Eles são acessados por portas de entrada/saída;  

* Drivers: Responsáveis pela interação entre os controladores, sistema operacional e os dispositivos. Cada controlador possuí sua própria interface, deste modo, torna-se necessário um drive específico para cada controlador;    

* Gerência de blocos: Camada responsável pelo gerenciamento do fluxo de blocos de dados entre as camadas superiores e dispositivos de armazenamento. Todos os discos são dispositivos orientados a blocos, deste modo, leitura e escrita de dados são sempre feitas com blocos de dados;  

* Alocação de arquivos: É uma estrturua que realiza a alocação dos arquivos sobre os blocos lógicos oferecidos pela camada de gerência de blocos. Os arquivos por sua vez, são vistos como uma sequência de blocos lógicos que devem ser armazenados nos blocos dos dispositivos;  


* Sistema de arquivos virtual: É uma camada responsável por abstrações de pastas e atalhos, também gerencia permissões de arquivos que acontecem devido ao acesso compartilhado, também registra arquivo aberto pelos processo;  

* Interface do sistema de arquivos: É um grupo de chamadas de sistema que estão disponíveis aos processos para a criação e modificação de arquivos;  


#### P. 23 Questão 18.

* Nesta abordagem é utilizado um pequeno conjunto de blocos no próprio volume em uma área reservada para criação de um registro de mapa de bits. Valores 0 e 1 da base 2 em bit são utilizados para representar se o bloco está livre ou ocupado, desta maneira mapeia-se os blocos utilizados e os blocos disponíveis de toda a partição;  

---

>### Capítulo 25 - Diretórios e atalhos


#### P. 10 Questão 2.

* A diferença encontrada a partir da leitura do capitulo foi: no S.O desenvolvido pela microsoft (Windows) o caractere separados utilizado é o \"\\" e a referência ao diretório raiz do sistema é o "[label do disco]:" geralmente o "C:\". Já no sistema UNIX, o caractere separador utlizado é o "/" e sua refêrencia raiz tambem é o "/", entretanto, o utilizador do sistema pode usar qualquer diretório como raiz e não se limitar apenas a um;  
