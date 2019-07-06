### Sistemas Operacionais - 2º Bimestre - 2019.

>#### Interação entre tarefas - Capítulo 13 - Impasses

- Questões da avaliação
    - (1) Questão 4:

        - Resposta:

            Partindo do princípio que nenhuma medida preventiva foi adotada para prevenir ou evitar impasses e as tarefas executam normalmente suas atividades, alocando e liberando recursos conforme suas necessidades temos duas soluções para resolver um impasse. Eliminar tarefas: Uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais tarefas possam prosseguir. Retroceder tarefas: Uma ou mais tarefas envolvidas no impasse têm sua execução parcialmente desfeita (uma técnica chamada rollback), de forma a fazer o sistema retornar a um estado seguro anterior ao impasse. A última opção para solução de impasses é menos viável, pois é necessário salvar periodicamente o estado da tarefa para que seja possível voltar ao estado anterior quando necessário. Além disso, operações envolvendo a rede ou interações com o usuário podem ser muito difíceis ou mesmo impossíveis de retroceder.

    - (2) Questão 8:

        - Resposta: 
        
            Na imagem da esquerda, o impasse acontece no seguinte ciclo: t1 _requer_ r2 _pertence_ t2 _requer_ r1 _pertence_ t1. Nesse contexto, o impasse irá acontecer pelo simples motivo de que nenhuma tarefa vai liberar o recurso que possui sem antes receber o outro recurso.

            Na imagem da direito eu acredito que não existe um impasse pelo simples motivo:
            r2 e uma instância de r3 _pertence_ a t4, que por sua vez não _requer_ nenhum outro recurso, ou seja, se r2 ou r3 for solicitado por outra tarefa (tx) os recursos (r2 ou r3) serão liberados por t4. Entretanto, r2 esta _pertencendo_ a t2 e t4, acredito que isso não seja possível.

    - (3) Questão 9:        
        - Resposta:

            Exclusão mútua: Os carros em sentidos diferentes (vertical e horizontal) não devem acessar o mesmo cruzamento ao mesmo tempo.
            
            Posse e espera: Os carros que estão em um cruzamento solicita acesso ao outro cruzamento sem liberar o cruzamento que ele está ocupando.

            Não-preempção: Os carros que ocupam um cruzamento só libera quando assim decidir.

            Espera circular: Os carros vermelhos dependente da liberação do cruzamento dos carros azuis, que depende dos verdes, que depende dos amarelos e os amarelos dependem dos vermelhos, entrando em um ciclo de esperas.

            A regra para evitar o impasse: Podemos dizer que todo cruzamento é um recurso compartilhado, e com isso, só é possível acessar um de cada vez, dessa forma, cada recurso (cruzamento) deve ter um semáforo para informar se está liberado ou não. Portanto, cada carro deve solicitar o semáforo do recurso para prosseguir ou aguardar.




#### Gestão de memória

>#### Capítulo 14 - Conceitos básicos

- Página 10 
    - (4) Questão 1:

        - Resposta:

            Codificação: O software escolhe a posição de cada variavél e do código-fonte do software;

            Compilação: Compilador escolhe a posição das variavéis na memória, código-fonte é conhecido no momento que o processo de compilação ocorre, evitando possíveis conflitos de endereços na memória;

            Ligação: Pega os arquivos objetos (gerado pelo compilador) com suas tabelas de símbolos, define os endereços de memória dos símbolos e gera o programa executável.
            
            Carga: Responsável por definir os objetos de variáveis e funções de carga do código-fonte em memória para iniciar um novo processo;

            Execução: Após todo o processo, estes, são analisados e consequeentemente convertidos pelo processador para a memória final;

    -(5) Questão 2:

            O processo é organizado em: Text, Data, Heap e Stack.

            Text: Responsável por conter o código-fonte a ser executado durante o processo, gerado durante a compilação e a inclusão de bibliotecas no código-fonte;

            Data: Responsável por conter as estáticas geradas pelo uso de softwares;

            Heap: Responsável por armazenar os dados para alocação dinâmica: calloc, malloc, free;

            Stack: Responsável por mater a pilha de execução do processo;



>#### Capítulo 15 - Hardware de memória
- página 21
    - (6) Questão 1:

        - Resposta: 

            Endereços físicos (ou reais) são os endereços dos bytes de memória física do computador. Estes endereços são definidos pela quantidade de memória disponível na máquina. Já os endereços lógicos (ou virtuais) são os endereços de memória usados pelos processos e pelo sistema operacional e, portanto, usados pelo processador durante a execução. Estes endereços são definidos de acordo com o espaço de endereçamento do processador. Uma das razões para utilizar endereços lógicos é ocultar a organização complexa da memória física e simplificar os procedimentos de alocação da memória aos processos.

    -(7) Questão 7:

        - Resposta:

            | Segmento Lógico         |   0  |   1   |   2  |    3    |   4   |
            |------------------|------|-------|------|---------|-------| 
            | Offset Lógico          | 45   | 100   | 90   | 1.900   | 200   |
            | Endereço Físico  | 89   | 300   | 90   | Violação de segmentação | 1.400 |

    - (8) Questão 8:

        - Resposta:

            | Página | 0         | 1 | 2 | 3 | 4 | 5   | 6                 | 7  | 8  | 9  | 10 | 11    | 12 | 13 | 14  | 15 |
            |--------|-----------|---|---|---|---|-----|-------------------|----|----|----|----|-------|----|----|-----|----|
            | Quadro | 3 - 4.000 | 12| 6 | – | 9 | 741 | 2 - 1.995 - 6.633 | –  | 0  | 5  | –  | 1.995 | –  | 7  | 414 | 1  |




>#### Capítulo 16 - Alocação de memória

    - (9) Questão 5:

       Resposta: (B) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.




>#### Capítulo 17 - Paginação em disco

    - (10) questão 1:
        
        - Resposta: 
        
            Falta de página é quando um processo acessa uma página virtual e o MMU verifica se a mesma está localizada na memória RAM. Se estiver, faz o acesso ao endereço físico correspondente. Caso contrário, a MMU gera uma interrupção de falta de página que desvia a execução para o sistema operacional. O sistema operacional verifica se a página é válida, usando os flags de controle da tabela de páginas. Caso a página seja inválida, o processo tentou acessar um endereço inválido e deve ser abortado. Por outro lado, caso a página solicitada seja válida, o processo deve ser suspenso enquanto o sistema transfere a página de volta para a memória RAM e faz os ajustes necessários na tabela de páginas

            Possiveis causas:
            
            A página correspondente ao endereço requisitado não está carregada na memória;

            A página correspondente ao endereço de memória acessado está carregada, mas o seu estado corrente não foi atualizado no hardware;

            A página não é parte do programa, e portanto não é mapeada na memória do programa;

            O programa não tem privilégios suficientes para ler ou escrever a página;

            O acesso à página é legal, mas está mapeada como página sob demanda.
            
            Geralmente, o programa que recebe a exceção deve trata-lá, caso contrário, o sistema operacional realiza um padrão já implementado para tratar, deste modo, executa o término do processo que causou e mostra ao usuário que o programa apresenta um mal funcionamento, dependendo do S.O essa mensagem pode ser mostrando de diferentes maneiras, entretanto, todas com a mesma finalidade.



