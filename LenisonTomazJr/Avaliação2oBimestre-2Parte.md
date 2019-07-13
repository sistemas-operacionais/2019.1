### Capítulo 20 - Software de entrada e saída
  ## Respostas
        (1)-não, pois ficaria mais difícil para o gerenciar os drivers já que cada drive teria sua própria interface, 
            fica mais fácil  para o SO gerenciar os drives com uma interface padrão para todos dispositivos.
            
        
### Capítulo 21 - Discos rígidos
  ## Respostas
       2) página 12, questão 3- 
            c e d - Raid 0 (striping);
            a Raid 0;
            b Raid 1; 
            e-Raid 5;
            
            
            
            
 ### Capítulo 22 - O conceito de arquivo
  ## Respostas    
        (3) questão 3:
             -extensão do nome : o arquivo segue uma estrutura de NomeDOArquivo.TipoDOArquivo, por exemplo, foto.png.Tem como 
             vantagens a fácil identificação do tipo do arquivo.

            -números mágicos (magic numbers)-  nessa estratégia se usa alguns bytes no início do conteúdo do arquivo para a 
            definição de seu tipo que  são convencionados para muitos tipos de arquivos.A vantagem dessa estratégia é que se 
            consegue identificar o tipo do arquivo sem precisar do  nome do arquivo.


            -Tipos MIME (da sigla Multipurpose Internet Mail Extensions)-  O padrão MIME é usado para identificar arquivos 
            transferidos como anexos de e-mail e conteúdos obtidos de páginas Web. Alguns sistemas operacionais, como o BeOS e 
            o MacOS X, definem atributos adicionais usando esse padrão para identificar o conteúdo de cada arquivo dentro do 
            sistema de arquivos.
            
            
       (4) questão 4:
              a- incorreta : nessa estratégia se usa alguns bytes no início do conteúdo do arquivo e não em arquivos 
                             separados.                
             b - correta
             c- Incorreta. o sistema UNIX usa bytes no início  do arquivo   e não no final.
             d- correta
             e- correta
             f- correta.
             
      
      
          
 ### Capítulo 23 - Uso de arquivos
  ## Respostas 
        (5) questão 3:
             Acesso sequencial: os dados são sempre lidos e/ou escritos em sequência, do início ao final do arquivo. Para 
             cada arquivo aberto por uma aplicação é definido um ponteiro de acesso, que inicialmente aponta para a primeira
             posição do arquivo.

             Acesso aleatório: pode-se indicar a posição no arquivo onde cada leitura ou escrita deve ocorrer, sem a 
             necessidade de um ponteiro de posição corrente. Assim, caso se conheça previamente a posição de um determinado 
             dado no arquivo, não há necessidade de percorrê-lo sequencialmente até encontrar o dado desejado. Essa forma de 
             acesso é muito importante em gerenciadores de bancos de dados e aplicações congêneres, que precisam acessar 
             rapidamente as posições do arquivo correspondentes ao registros desejados em uma operação.

             Acesso mapeado em memória: faz uso dos mecanismos de paginação em disco (Capítulo 17). Nessa modalidade de acesso,
             o arquivo é associado a um vetor de bytes (ou de registros) de mesmo tamanho na memória principal, de forma que 
             cada posição do vetor corresponda à sua posição equivalente no arquivo. Quando uma posição específica do vetor na
             memória é lida pela primeira vez, é gerada uma falta de página. 

             Acesso indexado : Esse sistema implementa arquivos cuja estrutura interna pode ser vista como uma tabela de pares 
             chave/valor. Os dados do arquivo são armazenados em registros com chaves (índices) associados a eles, e podem ser
             recuperados usando essas chaves, como em um banco de dados relacional.
             
         
        (6) questão 4
             Travas obrigatórias (mandatory locks): são impostas pelo núcleo de forma incontornável: se um processo obtiver 
             a trava de um arquivo, outros processos que solicitarem acesso ao mesmo arquivo serão suspensos até que aquela 
             trava seja liberada. É o tipo de trava mais usual em sistemas Windows. 

             Travas recomendadas (advisory locks): Os processos envolvidos no acesso aos mesmos arquivos devem travá-los 
             explicitamente quando forem acessá-los. Contudo, um processo pode ignorar essa regra e acessar um arquivo 
             ignorando a trava, caso necessário.

            Em relação ao compartilhamento das travas de arquivos, elas podem ser: 

            Travas exclusivas (ou travas de escrita): garantem acesso exclusivo ao arquivo: enquanto uma trava exclusiva 
            estiver ativa, nenhum outro processo poderá obter outra trava sobre o mesmo arquivo. 

            Travas compartilhadas (ou travas de leitura): impedem outros processos de criar travas exclusivas sobre aquele 
            arquivo, mas permitem a existência de outras travas compartilhadas.
            
       (7) questão 5
            Semântica imutável: o arquivo pode ser compartilhado por vários processos, ele é marcado como imutável, ou seja,
            seu conteúdo somente pode ser lido e não pode ser modificado. É a forma mais simples de garantir a consistência 
            do conteúdo do arquivo entre os processos que compartilham seu acesso.

            Semântica UNIX: toda modificação em um arquivo é imediatamente visível a todos os
            processos que mantêm aquele arquivo aberto; Essa semântica é a mais comum
            em sistemas de arquivos locais, ou seja, para acesso a arquivos nos dispositivos
            locais;

            Semântica de sessão: cada processo usa um arquivo em uma sessão,
            que inicia com a abertura do arquivo e que termina com seu fechamento.
            Modificações em um arquivo feitas em uma sessão somente são visíveis na
            mesma seção e pelas sessões que iniciarem depois do encerramento da mesma,
            ou seja, depois que o processo fechar o arquivo; assim, sessões concorrentes
            de acesso a um arquivo compartilhado podem ver conteúdos distintos para o
            mesmo arquivo.

            Semântica de transação: uma transação é uma sequência de operações de leitura e
            escrita em um ou mais arquivos emitidas por um processo e delimitadas por
            comandos de início e fim de transação (begin ... end), como em um sistema
            de bancos de dados.





 ### Capítulo 24 - Sistemas de arquivos
  ## Respostas 
        (8) página 20, questão 1.
              Dispositivos: como discos rígidos ou bancos de memória flash, são os responsáveis pelo armazenamento de dados.
              
             Controladores: são os circuitos eletrônicos dedicados ao controle dos dispositivos físicos. Eles são acessados 
             através de portas de entrada/saída, interrupções e canais de acesso direto à memória (DMA). 

             Drivers: interagem com os controladores de dispositivos para configurá-los e realizar as transferências de dados 
             entre o sistema operacional e os dispositivos. 

             Gerência de blocos: gerencia o fluxo de blocos de dados entre as camadas superiores e os dispositivos de 
             armazenamento. Como os discos são dispositivos orientados a blocos, as operações de leitura e escrita de dados 
             são sempre feitas com blocos de dados, e nunca com bytes individuais. 

             Alocação de arquivos: realiza a alocação dos arquivos sobre os blocos lógicos oferecidos pela camada de gerência 
             de blocos. Cada arquivo é visto como uma sequência de blocos lógicos que deve ser armazenada nos blocos dos 
             dispositivos de forma eficiente, robusta e flexível. 

             Sistema de arquivos virtual: o VFS (Virtual File System) constrói as abstrações de diretórios e atalhos, além de 
             gerenciar as permissões associadas aos arquivos e as travas de acesso compartilhado. Outra responsabilidade 
             importante desta camada é manter o registro de cada arquivo aberto pelos processos, como a posição da última 
             operação no arquivo, o modo de abertura usado e o número de processos que estão usando o arquivo. 

             Interface do sistema de arquivos: conjunto de chamadas de sistema oferecidas aos processos do espaço de usuários 
             para a criação e manipulação de arquivos. 

             Bibliotecas de entrada/saída: usam as chamadas de sistema da interface do núcleo para construir funções 
             padronizadas de acesso a arquivos para cada linguagem de programação.
        
       (9) página 23, questão 18
            Na abordagem de mapa de bits ou bitmaps, um pequeno conjunto de blocos na área reservada do volume é usado para
            manter um mapa de bits. Nesse mapa, cada bit representa um bloco lógico da partição, que pode estar livre ou 
            ocupado. 




 ### Capítulo 25 - Diretórios e atalhos
  ## Respostas 
       (10) página 10, questão 2.
            DIFERENÇAS: 
              -definição do root.
              -separadores diferentes,“\” para o windows e “/” para o linux.


