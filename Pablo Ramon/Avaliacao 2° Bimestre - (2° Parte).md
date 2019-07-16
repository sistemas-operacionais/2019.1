**Avaliação**  
**Discente: Pablo Ramon Varela de Souza**  
**Matricula: 20181014040009**  
  
1)  
  
2)  
a) Usaria o RAID 0 Linear ou Striping por permitir ter todo o espaço dos discos disponíveis.    
b) RAID 6 por permitir correção de falhas em até dois discos.  
c) RAID 1 Por que o desempenho em leituras é distribuido entre as cópias dos dados sendo assim beneficiado.  
d) RAID 5 por ter os dados de paridade distribuidos nos discos beneficiando em muito a escrita.  
e) RAID 5 pois é o que tem o melhor equilíbrio entre espaço, velocidade e confiabilidade.  
  
3)
A atribuição de tipos aos arquivos acontece de várias formas. Pode ser feita colocando a extensão do arquivo no final do nome do mesmo, ou utilizando alguns bytes do conteúdo para dizer ao sistema que tipo de arquivo é aquele, ou ainda incluindo um *atributo adicional* para identificar o arquivo. No caso dos arquivos a serem transferidos por email utiliza-se o tipo MIME que identifica os arquivos por *tipo/subtipo*.  
Cada forma tem as suas vantagens e desvantagens começando pela forma com extensão. A forma de identificação por extensão permite ao usuário identificar rapidamente o tipo do arquivo só de olhar para o nome dele, o problema é que o nome (incluindo a extensão) pode ser alterado pelo usuário podendo causar assim problemas ao ler ou escrever no arquivo, culminando na sua inutilização.  
A forma de identificação pelos bytes ajuda muito o sistema que não precisa se preocupar com a extensão e para identificar o arquivo ele observa os bytes iniciais e a estrutura do arquivo.  
Já o método de adicionar atributos permite saber diretamente o tipo, e que aplicativo criou aquele arquivo permitindo até sugerir os aplicativos que podem abrir aquele tipo de arquivo sem observar mais nada do arquivo, porém ainda é possível ser alterado pelo usuário assim estando sujeita aos mesmos problemas das extensões.  
O uso so tipo MIME ajuda muito na identificação já que ele divide em tipo e subtipo permitindo saber se um arquivo é um audio sem saber se ele é midi ou mpeg por exemplo. O maior problema seria que esses tipos tem que ser todos armazenados em um padrão não permitindo a inserção de novos de forma mais simples.  

4)  
a) **Incorreta** *Magic Number* são os bytes iniciais usados para identificar um arquivo.  
b) **Correta** A forma mais usada em quase todos os sistemas operacionais é a de nome - extensão.  
c) **Correta** No UNIX é utilizado o caracter *New Line* (\n) enquanto que no DOS é utilizado o *Carriage Return* seguido de um *New Line* (\r\n)  
d) **Correta** O núcleo só se preocupa em escrever, ler e manipular os bits dos arquivos deixando a responsabilidade de tipos, extensões e etc para as camadas superiores.  
e) **Incorreta** ELF e PE são arquivos de código no sistema UNIX  
f) **Incorreta** MIME é o tipo para arquivos que serão enviados por email.  
  
5)  
Existem algumas formas de acesso aos arquivos nos sistemas operacionais. O acesso sequencial é o mais comum onde os dados sempre são lidos do começo até o final do arquivo. Ao chegar ao final não é mais permitida a leitura, mas é permitida a escrita para ter a possibilidade de adicionar dados ao final do arquivo.  
O acesso aleatório é muito importante pois permite pular para um ponto conhecido do arquivo e começar a leitura por lá. Também permite esses *pulos* durante a execução. Nos sistemas POSIX esses pulos são feitos usando o lseek() e fseek().  
O acesso mapeado em memória consiste em usar a paginação em disco associando o arquivo a um vetor de bytes na memória, e ir carregando do disco só quando necessário. Ele é usado extensivamente no núcleo do sistema para carregar códigos executáveis.  
No acesso indexado o sistema implementa os arquivo de forma que eles possam ser vistos como *chave/valor* permitindo que o acesso a esses arquivos seja feito de forma extremamente alta.  
  
6) 
Existem quatro tipos de travas de arquivos compartilhados. As travas obrigatórias são impostas pelo núcleo de forma incontornável: se um processo obtiver a trava de um arquivo, outros processos que solicitarem acesso ao mesmo arquivo serão suspensos até que aquela trava seja liberada.  
As travas recomendadas não são impostas pelo núcleo do sistema operacional, mas gerenciadas pelo suporte de execução (bibliotecas). Os processos
envolvidos no acesso aos mesmos arquivos devem travá-los explicitamente
quando forem acessá-los. Contudo, um processo pode ignorar essa regra e
acessar um arquivo ignorando a trava, caso necessário. Travas recomendadas
são úteis para gerenciar concorrência entre processos de uma mesma aplicação.
Neste caso, cabe ao programador implementar os controles necessários nos
processos para impedir acessos conflitantes aos arquivos compartilhados.  
As travas exclusivas garantem acesso exclusivo ao arquivo: enquanto
uma trava exclusiva estiver ativa, nenhum outro processo poderá obter outra
trava sobre o mesmo arquivo.  
As travas compartilhadas impedem outros processos de criar travas
exclusivas sobre aquele arquivo, mas permitem a existência de outras travas
compartilhadas.  

7)  
Existem quatro semânticas de acesso.  
A semântica imutável diz que se um arquivo pode ser compartilhado por vários processos, ele é marcado como imutável, ou seja, seu
conteúdo somente pode ser lido e não pode ser modificado.  
A semântica UNIX diz que toda modificação em um arquivo é imediatamente visível a todos os processos que mantêm aquele arquivo aberto.  
A semântica de sessão considera que cada processo usa um arquivo em uma sessão,
que inicia com a abertura do arquivo e que termina com seu fechamento.
Modificações em um arquivo feitas em uma sessão somente são visíveis na
mesma seção e pelas sessões que iniciarem depois do encerramento da mesma,
ou seja, depois que o processo fechar o arquivo. Assim, sessões concorrentes
de acesso a um arquivo compartilhado podem ver conteúdos distintos para o
mesmo arquivo.  
A semântica de transação trabalha com transações que é uma sequência de operações de leitura e
escrita em um ou mais arquivos emitidas por um processo e delimitadas por
comandos de início e fim de transação (begin ... end), como em um sistema
de bancos de dados. Todas as modificações parciais do arquivo durante a
execução de uma transação não são visíveis às demais transações, somente
após sua conclusão.  
  
8)  
Todos os sistemas operacionais atuais dividem o disco em blocos lógicos que podem ser utilizados das mais diversas formas para armazenar os arquivos, permitindo uma grande miscelânea ao fazer esse armazenamento.  
  
9)  
Nessa forma de gerência é utilizada uma cadeia de bits que representam todos os blocos do disco e eles são atribuidos em 1 se estiverem sendo utilizados, ou 0 se estiverem vazios.  
  
10)  
Do ponto de vista lógico, somente o fato do Windows utilizar a atribuição de letras as partições, enquanto o UNIX não faz o mesmo. A única outra diferença é que o UNIX implemente a árvore de diretórios como mostra na interface, enquanto o Windows apesar de mostrar a árvore, por baixo ele não funciona como uma.
