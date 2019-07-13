### Interação entre tarefas - Capítulo 13 - Impasses
  ## Respostas

        -1) página 10, questão 4:
        
              Quando ocorrer um impasse, o sistema deve detectá-lo, determinar quais as tarefas e recursos 
            envolvidos e tomar medidas para desfazê-lo.Para a detectar o impasse o sistema pode utilizar inspeção do grafo de alocação
            de recursos. Depois de detectado quais recursos e tarefas estão envolvidas no impasse, será escolhida a estratégia para 
            tratar o impasse, que são:

            Eliminar tarefas : uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais 
            tarefas possam prosseguir. A escolha das tarefas a eliminar deve levar em conta vários fatores, como o tempo de vida de cada 
            uma, a quantidade de recursos que cada tarefa detém. Normalmente será  viável utilizar essa estratégia quando a eliminação da
            tarefa  não irá  prejudicar o usuário.

            Retroceder tarefas :uma ou mais tarefas envolvidas no impasse têm sua execução parcialmente desfeita (uma técnica chamada rollba
            ck), de forma a fazer o sistema retornar a um estado seguro anterior ao impasse. Para retroceder a execução de uma tarefa, é 
            necessário salvar periodicamente seu estado, de forma a poder recuperar um estado anterior quando necessário.Essa estratégia 
            não será  viável para tarefas que não tem como fazer o “rollback”, por exemplo, desfazer o envio de um pacote de rede, ou a 
            reprodução de um arquivo de áudio na tela do usuário, mas será muito utilizada em  sistemas de bancos de dados, pois são 
            providos mecanismos para criar checkpoints dos registros envolvidos antes da transação  para efetuar o rollback.
        
        -2) página 11, questão 8.8 : 
        
            Imagem 1: ciclo que irá gera um impasse T1 requer o recurso R2,o recurso R2  pertence à T2,T2 requer o recurso R1,
            O recurso R1  pertence à T1.
            
            Imagem 2: T1 requer o recurso R2,o recurso R2  pertence à T2,T2 requer o recurso R3,o recurso R3  pertence à T3 e 
            T4(é um instância múltipla),T3 requer o recurso R1,o recurso R1  pertence à T1.Provavelmente este ciclo irá dar 
            impasse, mas pode ser que a tarefa T4 libere  uma instância do recurso R3,caso isso aconteça não irá haver impasse.
            
            
        -(3) página 11, 9:

           Exclusão mútua: No exemplo dos carros não há nenhum semáforo  para controlar o fluxo.

           Posse e espera: um carro pode solicitar acesso sem deter os seus recursos.

           Não-preempção: Como não tem um semáforo para controlar o fluxo, o carro libera os recursos que detém quando assim 
           o decidir.

           Espera circular: O carro vermelho requer o recurso que está com o carro azul, o carro azul requer o recurso que 
           está com o verde, o carro verde requer o recurso que está com o carro amarelo. Isso irá causar uma dependência 
           circular que ocasionará um impasse.

           Resolução:
            Para resolver este problema seŕa necessário um semáforo e algumas regras ,para controlar o uso dos recursos.

          regras: 
            -toda vez que o semáforo estiver verde para o carro ele deve prosseguir(utilizar o recurso)
            todas vez que estiver vermelho o carro deve esperar, ou seja, esperar o outro carro utilizar o recurso.

            -para o semáforo ficar verde para os carros amarelos e azuis ele deve ficar vermelho para os carros vermelhos e 
            verdes.
            -para o semáforo ficar verde para os carros vermelhos  e verdes ele deve ficar vermelho para os carros amarelos e 
            azuis.





### Gestão de memória-Capítulo 14 - Conceitos básicos
  ## Respostas
      (4) questão 1:
             codificação,: o programador escolhe o endereço de cada uma das variáveis e do código do programa na memória. Esta
             abordagem normalmente só é usada na programação de sistemas embarcados simples, programados diretamente em 
             Assembly. 

             compilação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória. Para isso, todos os 
             códigos-fontes necessários ao programa devem ser conhecidos no momento da compilação.

             ligação: na fase de compilação, o compilador traduz o código fonte em código binário, mas não define os endereços das 
             variáveis e funções, gerando como saída um arquivo objeto (object file) 2 , que contém o código binário e uma tabela de 
             símbolos descrevendo as variáveis e funções usadas, seus tipos, onde estão definidas e onde são usadas. A seguir, o ligador 
             (linker) pega os arquivos objetos com suas tabelas de símbolos, define os endereços de memória dos símbolos e gera o programa
             executável [Levine, 2000]. 

            carga: um carregador (loader) é responsável por carregar o código do processo na memória e definir os endereços de memória 
            que devem ser utilizados. O carregador pode ser parte do núcleo do sistema operacional ou uma biblioteca ligada ao executável,
            ou ambos. Esse mecanismo normalmente é usado na carga de bibliotecas dinâmicas (DLL - Dynamic Linking Libraries). 

            execução: os endereços emitidos pelo processador durante a execução do processo são analisados e convertidos nos endereços 
            efetivos a serem acessados na memória real. Por exigir a análise e a conversão de cada endereço gerado pelo processador, 
            este método só é viável com o auxílio do hardware.

    
  
      (5) questão 2:
            é organizado em uma estrutura  com TEXT(código binário do programa), DATA(variáveis inicializadas), 
            BSS(variáveis não-inicializadas), HEAP(variáveis dinâmicas malloc/free), STACK(dados usados por funções 
            parâmetros, variáveis locais, endereços de retorno).

  
  
  
  
  
### Capítulo 15 - Hardware de memória
  ## Respostas  
       (6) questão 1:
              Endereços físicos (ou reais) são os endereços dos bytes de memória física do computador. Estes endereços são 
              definidos pela quantidade de memória disponível na máquina.
              
              Endereços lógicos (ou virtuais) são os endereços de memória usados pelos processos e pelo sistema operacional 
              e, portanto, usados pelo processador durante a execução. Estes endereços são definidos de acordo com o espaço 
              de endereçamento do processador.São utilizados, pois permitem implementar a proteção de memória do núcleo e 
              dos processos entre si, fundamentais para a segurança e estabilidade do sistema.

      (7) página 7:
            0:45 =  Endereço lógico-89
            1:100 = Endereço lógico-300
            2:90 = Endereço lógico-90
             3:1.900 = Estoura o limite
            4:200 = Endereço lógico-1.400

      (8) página 8:
            414 - pagina 14
            741 - pagina 5
            1.995  - pagina 6
            4.000 - pagina 0
            6.633 - pagin a 6
            
            
            
            
            

### Capítulo 16 - Alocação de memória
  ## Respostas
        (9) página 9, questão 5:
               (b) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.
               
               
### Capítulo 17 - Paginação em disco
  ## Respostas
        (10) página 19, questão 1:
                é uma interrupção (ou exceção) disparada pelo hardware quando um programa acessa uma página mapeada no espaço
                de memória virtual, mas que não foi carregada na memória física do computador.possíveis causas:
                
                    -a página correspondente ao endereço requisitado não está carregada na memória;
                    -a página correspondente ao endereço de memória acessado está carregada, 
                      mas o seu estado corrente não foi atualizado no hardware.
                    -a página não é parte do programa, e portanto não é mapeada na memória do programa;
                    -o programa não tem privilégios suficientes para ler ou escrever a página;
                     -o acesso à página é legal, mas está mapeada como página sob demanda.

      
      
