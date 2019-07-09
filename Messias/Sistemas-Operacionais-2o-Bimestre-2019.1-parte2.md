### Gestão de entradas e saídas
#### Capítulo 19 - Hardware de entrada/saída
#### Aluno:Emanoel Messias Gomes de Lima.
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
<b>vanatagens-</b>
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
<b>vanatagens-</b>
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
<b>vantagens-</b>
Em um sistema operacional moderno, um arquivo de código (programa executável ou biblioteca) é dividido internamente em várias seções, para conter código,
tabelas de símbolos (variáveis e funções), listas de dependências (bibliotecas necessárias)
e outras informações de configuração. A organização interna de um arquivo de código
depende do sistema operacional para o qual foi definido.<br>
<b>desvantagens-</b>
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
(5) questão 3. Comente as principais formas de acesso a arquivos. Qual o uso mais
apropriado para cada uma delas?

(6) questão 4. Apresente e explique os quatro principais tipos de travas sobre arquivos
compartilhados disponíveis no sistema operacional.

(7) questão 5. Apresente e explique as quatro principais semânticas de acesso a arquivos
compartilhados em um sistema operacional.


