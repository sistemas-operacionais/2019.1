### Sistemas Operacionais - 2º Bimestre - 2019.

>#### Interação entre tarefas - Capítulo 13 - Impasses

         Página 10 - questão 4
        Quando ocorrer um impasse, o sistema deve detectá-lo, determinar quais as tarefas e recursos envolvidos e tomar medidas para desfazê-lo.Para a detectar o impasse o sistema pode utilizar inspeção do grafo de alocação de recursos. Depois de detectado quais recursos e tarefas estão envolvidas no impasse, será escolhida a estratégia para tratar o impasse, que são:
        Eliminar tarefas:
        uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais tarefas possam prosseguir. A escolha das tarefas a eliminar deve levar em conta vários fatores, como o tempo de vida de cada uma, a quantidade de recursos que cada tarefa detém. Normalmente será  viável utilizar essa estratégia quando a eliminação da tarefa  não irá  prejudicar o usuário.
        Retroceder tarefas: uma ou mais tarefas envolvidas no impasse têm sua execução parcialmente desfeita (uma técnica chamada rollback), de forma a fazer o sistema retornar a um estado seguro anterior ao impasse. Para retroceder a execução de uma tarefa, é necessário salvar periodicamente seu estado, de forma a poder recuperar um estado anterior quando necessário.Essa estratégia não será  viável para tarefas que não tem como fazer o “rollback”, por exemplo, desfazer o envio de um pacote de rede, ou a reprodução de um arquivo de áudio na tela do usuário, mas será muito utilizada em  sistemas de bancos de dados, pois são providos mecanismos para criar checkpoints dos registros envolvidos antes da transação  para efetuar o rollback.
        
    Página 11 - questão 8. 8
       Grafo 1:
        Ciclo: T1 -> R2 -> T2 -> R1 -> T1
        
        Grafo 2:
        Ciclo: T1 -> R2 -> T2 -> R3 -> T3 -> R1 -> T1

    Página 11 - questão 9
            Exclusão mútua: No exemplo dos carros não há nenhum semáforo  para controlar o fluxo.
            
            Posse e espera: Os carros que estão em um cruzamento solicita acesso ao outro cruzamento sem liberar o cruzamento que ele está ocupando.

            Não-preempção: Os carros que ocupam um cruzamento só libera quando assim decidir.

            Espera circular: Os carros vermelhos dependente da liberação do cruzamento dos carros azuis, que depende dos verdes, que depende dos amarelos e os amarelos dependem dos vermelhos, entrando em um ciclo de esperas.

            Regra: definir semáforo em cada um dos sentidos, possibilitando o prosseguimento das tarefas em um sentido por vez.

#### Gestão de memória

>#### Capítulo 14 - Conceitos básicos

    Página 10 - questão 1.
            Codificação: o programador escolhe o endereço de cada uma das variáveis e do código do programa na memória. Esta abordagem normalmente só é usada na programação de sistemas embarcados simples, programados diretamente em Assembly.

            Compilação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória. Para isso, todos os 
         códigos-fontes necessários ao programa devem ser conhecidos no momento da compilação.

            Ligação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória. Para, isso, todos os códigos-fontes necessários ao programa devem ser conhecidos no momento da compilação, para evitar conflitos de endereços entre variáveis em diferentes arquivos ou bibliotecas. Essa restrição impede o uso de bibliotecas pré compiladas.
            
            Carga: Responsável por definir os objetos de variáveis e funções de carga do código-fonte em memória para iniciar um novo processo;

            Execução: os endereços emitidos pelo processador durante a execução do processo são analisados e convertidos nos endereços efetivos a serem acessados na memória real. Por exigir a análise e a conversão de cada endereço gerado pelo processador, este método só é viável com o auxílio do hardware.

    Questão 2. 
            
           Text: Responsável por conter o código-fonte a ser executado durante o processo, gerado durante a compilação e a inclusão de bibliotecas no código-fonte; 
           
           Data: Responsável por conter as estáticas geradas pelo uso de softwares;
       
           Heap: Responsável por armazenar os dados para alocação dinâmica: calloc, malloc, free;
           
            Stack: Responsável por mater a pilha de execução do processo;

>#### Capítulo 15 - Hardware de memória

    Página 21 - questão 1. 

            Endereços físicos (ou reais) são os endereços dos bytes de memória física do computador. Estes endereços são 
          definidos pela quantidade de memória disponível na máquina.
          
          Endereços lógicos (ou virtuais) são os endereços de memória usados pelos processos e pelo sistema operacional 
          e, portanto, usados pelo processador durante a execução. Estes endereços são definidos de acordo com o espaço 
          de endereçamento do processador.São utilizados, pois permitem implementar a proteção de memória do núcleo e 
          dos processos entre si, fundamentais para a segurança e estabilidade do sistema.

    página 7:
        0:45 =  89
        1:100 = 300
        2:90 = 90
        3:1.900 = Estoura o limite
        4:200 = 1.400

    página 8:
        414 = 1914
        741 = 741
        1.995 = 475(NULL)
        4.000 = 0
        6.633 = 3633

>#### Capítulo 16 - Alocação de memória

    Página 9 - questão 5. 

        (b) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.

      
>#### Capítulo 17 - Paginação em disco

    Página 19 - questão 1
        Falta de página é uma interrupção (ou exceção) disparada pelo hardware quando um programa acessa uma página mapeada no espaço de memória virtual, mas que não foi carregada na memória física do computador; O que pode causar isso é:

        - A página correspondente ao endereço requisitado não está carregada na memória;

        - A página correspondente ao endereço de memória acessado está carregada, mas o seu estado corrente não foi atualizado no hardware;

        - A página não é parte do programa, e portanto não é mapeada na memória do programa;

        - O programa não tem privilégios suficientes para ler ou escrever a página;

        - O acesso à página é legal, mas está mapeada como página sob demanda.
            
        - Geralmente, o programa que recebe a exceção deve trata-lá, caso contrário, o sistema operacional realiza um padrão já implementado para tratar, deste modo, executa o término do processo que causou e mostra ao usuário que o programa apresenta um mal funcionamento, dependendo do S.O essa mensagem pode ser mostrando de diferentes maneiras, entretanto, todas com a mesma finalidade.

>### Capítulo 20 - Software de entrada e saída

    Por que os sistemas operacionais exigem de todos os drivers de disposito (device-drivers) a mesma interface padrão? Não seria mais apropriado deixar cada driver de dispositivo definir rotinas de interface que fazem sentido para aquele tipo específico de dispositivo?

    Resposta: Não, pois é justamente essa exigência que torna a comunicação do sistema operacional com os 
    dispositivos mais facil. Pois sem isso os sistemas operacionais teriam que 
    se adaptar a qualquer dispositivo do mundo.


>### Capítulo 21 - Discos rígidos
    Página 12 - questão 3
    A)
    Para esta finalidade, eu escolheria o RAID 0, pois aqui os discos são
     divididos em fatias (stripes), e essas fatias são concatenadas para melhor 
    aproveitamento do espaço útil de disco. 
    
    B)Para esta finalidade, eu escolhereia o RAID 1, pois aqui o conteúdo 
    é replicado em mais de um disco.
    
    C)Para esta finalidade, eu escolhereia o RAID 0, pois aqui os discos são dividos
    em fatias, e essas fatias são concatenadas. Tudo isso contribui para haja um
    maior espalhamento dos blocos sobre os discos físicos, e consequentemente esse 
    arranjo obtem um melhor desempenho em leitura/escrita.
    
    D)Para esta finalidade, eu escolhereia o RAID 0, pois aqui os discos são dividos
    em fatias, e essas fatias são concatenadas. Tudo isso contribui para haja um
    maior espalhamento dos blocos sobre os discos físicos, e consequentemente esse 
    arranjo obtem um melhor desempenho em leitura/escrita.
    
    
    E)Para esta finalidade, eu escolhereia o RAID 5, por que assim como no RAID 4,
    ele também aramazena informações de paridade para tolerar falhas, mas a diferença
     aqui essas informações não ficam concentradas em um único disco físico, são 
    distribuídas uniformemente entre os discos. E isso colabora no desempenho no
    acesso aos dados. E esta é uma abordagem de RAID popular, por oferecer um bom
    desempenho e redundância de dados, desperdiçando menos espaço que o
    espelhamento


>### Capítulo 22 - O conceito de arquivo
    Página 10 - questão 3
    Números Mágicos
    Aqui se usa alguns bytes no começo do conteúdo do arquivos para 
    se definir o formato dele. Essa forma tem uma segurança maior na manutenção 
    do formato do arquivo, mas, é sempre será necessário ler o início do arquivo 
    para reconhecer o formato.
    
    Extensão por nome
    Aqui se usa o próprio nome do arquivo para definir o formato. É uma forma 
    bem prática e simples, porém pode ser facilmente alterada.


    Página 10 - questão 4
    a) Incorreto - byte, não necessariamente numéricos

    b) Correto
    
    C) Incorreto
    
    d) Correto
    
    e) Incorreto - São formatos de arquivo de código.
    
    f) Incorreto - É usado nos sistemas operacionais MacOS X e BeOS.


>### Capítulo 23 - Uso de arquivos

    Página 13 - questão 3
    Acesso sequencial: Neste tipo de acesso, os dados são lidos ou escritos de maneira sequencial, do início até o final do arquivo. É o mais popular e utilizado em quase todos os S.O's do mercado e a forma mais usual de acesso aos arquivos.
    Acesso direto a posições específicas do arquivo, indica-se a posição do arquivo onde fazer o acesso, read (file, position, size, buffer). Importante em SGBDs e aplicações similares, raramente implementada “pura” nos SOs.
    Acesso aleatório: aqui se pode pode indiar a posição do aquivo onde cada leitura ou escrita deve acontecer. Essa forma é útil para gerenciadores de bancos de dados e aplicações congêneres que precisam frequentemente acessar as posições de arquivos.
    Acesso mapeado em memória: Neste tipo de acesso, o arquivo é associado a um vetor de bytes de mesmo tamanho na memória principal, de forma que cada posição do vetor corresponda à sua posição equivalente no arquivo. É usado pelo núcleo para carregar código executável software e library na memória.
    Acesso indexado, implementado em alguns sistemas, como o OpenVMS, estrutura interna do arquivo é vista com tabela indexada, acesso muito rápido (indexação implementada no núcleo), pouco usado nos SOs atuais, mas disponível por bibliotecas.

    Página 13 - questão 4
    Trava obrigatória: incontornável, imposta pelo núcleo aos processos, processos são suspensos aguardando liberar a trava, default nos sistemas Windows.
    Travas recomendadas: Estas são impostas pelo próprio núcleo do S.O, entretanto, são gerenciadas pelo suporte da execução um exemplo deste suporte são as bibliotecas. São muitos os processos envolvendo o acesso dos mesmos arquivos, todavia, devem travá-los explicitamente quando forem acessá-los.
    Travas exclusivas: garantem acesso exclusivo ao arquivo, enquanto uma trava exclusiva estiver ativa, nenhum outro processo poderá ter acesso ao arquivo.
    Trava recomendada: impede travas exclusivas sobre o arquivo, permite mais travas compartilhadas.

    Página 13 - questão 5
    Semântica imutável: Aqui quando um arquivo é compartilhado entre vários processos, este arquivo não pode ser alterado, only read (apenas leitura). De tal forma que, arquivos compartilhados recebem a marcação de imutáveis, garantido total integridade do conteúdo;
    
    Semântica Unix: Modificações são imediatamente perceptíveis a todos os processos que envolvem aquele arquivo, comum em sistemas de arquivos locais UNIX.
    
    Semântica de Sessão: considera que cada processo usa um arquivo em uma sessão, que inicia com a abertura do arquivo e termina com o seu encerramento. Se um arquivo é modificado uma sessão só serão percebidas na mesma sessão e pelas que forem iniciadas após o encerramento da que realizou as alterações.
    
    Sessão de transição: Aqui trata-se de um conceito parecido com o de semântica de sessão, sua diferença acontece no momento que um conjunto de operações é realizada o arquivo é atualizado. Todas as modificações parciais do arquivo durante a execução de uma transação não são visíveis às demais transações, somente após sua conclusão.
    

>### Capítulo 24 - Sistemas de arquivos
    Página 20 - questão 1
    Dispositivos: Responsáveis pelo armazenamento dos dados. Como: discos rígidos e bancos de memória flash.
    
    Controladores: Constituídos por circuitos eletrônicos dedicados ao controle dos dispositivos físicos. Eles são acessados por portas de entrada/saída.
    
    Drivers: interagem com os controladores, SO e os dispositivos. É necessário um driver para cada controlador, pelo fato de cada controlodaor ter um interface.
    
    Gerência de blocos: gerencia o fluxo de blocos de dados entre a memória e os dispositivos de armazenamento
    
    Alocação de arquivos: realiza a alocação de arquivos sobre os blocos lógicos oferecidos pela camada de gerência de blocos.
    
    Sistema de arquivos virtual: É uma camada responsável por abstrações de pastas e atalhos, também gerencia permissões de arquivos que acontecem devido ao acesso compartilhado.
    
    Interface do sistema de arquivos: conjunto de chamadas de sistema oferecias aos processos do espaço de usuários para a criação e manupulação de arquivos.
    
   
