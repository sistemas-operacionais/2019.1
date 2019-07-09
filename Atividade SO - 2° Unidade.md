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

     página 19 - questão 1
        Falta de página é uma interrupção (ou exceção) disparada pelo hardware quando um programa acessa uma página mapeada no espaço de memória virtual, mas que não foi carregada na memória física do computador; O que pode causar isso é:

        - A página correspondente ao endereço requisitado não está carregada na memória;

        - A página correspondente ao endereço de memória acessado está carregada, mas o seu estado corrente não foi atualizado no hardware;

        - A página não é parte do programa, e portanto não é mapeada na memória do programa;

        - O programa não tem privilégios suficientes para ler ou escrever a página;

        - O acesso à página é legal, mas está mapeada como página sob demanda.
            
        - Geralmente, o programa que recebe a exceção deve trata-lá, caso contrário, o sistema operacional realiza um padrão já implementado para tratar, deste modo, executa o término do processo que causou e mostra ao usuário que o programa apresenta um mal funcionamento, dependendo do S.O essa mensagem pode ser mostrando de diferentes maneiras, entretanto, todas com a mesma finalidade.






