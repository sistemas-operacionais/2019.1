### Sistemas Operacionais - 2º Bimestre - 2019.

>#### Interação entre tarefas - Capítulo 13 - Impasses


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-13.pdf)
- Questões da avaliação
    - (1) página 10, questão 4. Uma vez detectado um impasse, quais as abordagens possíveis para
resolvê-lo? Explique-as e comente sua viabilidade.

        - Resposta:

            Partindo do princípio que nenhuma medida preventiva foi adotada para prevenir ou evitar impasses e as tarefas executam normalmente suas atividades, alocando e liberando recursos conforme suas necessidades temos duas soluções para resolver um impasse. Eliminar tarefas: Uma ou mais tarefas envolvidas no impasse são eliminadas, liberando seus recursos para que as demais tarefas possam prosseguir. Retroceder tarefas: Uma ou mais tarefas envolvidas no impasse têm sua execução parcialmente desfeita (uma técnica chamada rollback), de forma a fazer o sistema retornar a um estado seguro anterior ao impasse. A última opção para solução de impasses é menos viável, pois é necessário salvar periodicamente o estado da tarefa para que seja possível voltar ao estado anterior quando necessário. Além disso, operações envolvendo a rede ou interações com o usuário podem ser muito difíceis ou mesmo impossíveis de retroceder.

    - (2) página 11, questão 8. 8. Nos grafos de alocação de recursos da figura a seguir, indique o(s)
ciclo(s) onde existe um impasse:

        - Resposta: 
        
            Na imagem da esquerda, o impasse acontece no seguinte ciclo: t1 _requer_ r2 _pertence_ t2 _requer_ r1 _pertence_ t1. Nesse contexto, o impasse irá acontecer pelo simples motivo de que nenhuma tarefa vai liberar o recurso que possui sem antes receber o outro recurso.

            Na imagem da direito eu acredito que não existe um impasse pelo simples motivo:
            r2 e uma instância de r3 _pertence_ a t4, que por sua vez não _requer_ nenhum outro recurso, ou seja, se r2 ou r3 for solicitado por outra tarefa (tx) os recursos (r2 ou r3) serão liberados por t4. Entretanto, r2 esta _pertencendo_ a t2 e t4, acredito que isso não seja possível.

    - (3) página 11, 9. A figura a seguir representa uma situação de impasse em um cruzamento de
trânsito. Todas as ruas têm largura para um carro e sentido único. Mostre que as quatro condições
necessárias para a ocorrência de impasses estão presentes nessa situação. Em seguida, defina
uma regra simples a ser seguida por cada carro para evitar essa situação; regras envolvendo algum
tipo de informação centralizada não devem ser usadas.
        
        - Resposta:

            Exclusão mútua: Os carros em sentidos diferentes (vertical e horizontal) não devem acessar o mesmo cruzamento ao mesmo tempo.
            
            Posse e espera: Os carros que estão em um cruzamento solicita acesso ao outro cruzamento sem liberar o cruzamento que ele está ocupando.

            Não-preempção: Os carros que ocupam um cruzamento só libera quando assim decidir.

            Espera circular: Os carros vermelhos dependente da liberação do cruzamento dos carros azuis, que depende dos verdes, que depende dos amarelos e os amarelos dependem dos vermelhos, entrando em um ciclo de esperas.

            A regra para evitar o impasse: Podemos dizer que todo cruzamento é um recurso compartilhado, e com isso, só é possível acessar um de cada vez, dessa forma, cada recurso (cruzamento) deve ter um semáforo para informar se está liberado ou não. Portanto, cada carro deve solicitar o semáforo do recurso para prosseguir ou aguardar.


`Data de entrega: 05/07/2019`



#### Gestão de memória

>#### Capítulo 14 - Conceitos básicos


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-14.pdf)
- Questões da avaliação 
- Página 10 
    - (4) questão 1. Explique em que consiste a resolução de endereços nos seguintes
momentos: codificação, compilação, ligação, carga e execução.

        - Resposta:

            Codificação: O software escolhe a posição de cada variavél e do código-fonte do software;

            Compilação: Compilador escolhe a posição das variavéis na memória, código-fonte é conhecido no momento que o processo de compilação ocorre, evitando possíveis conflitos de endereços na memória;

            Ligação: Pega os arquivos objetos (gerado pelo compilador) com suas tabelas de símbolos, define os endereços de memória dos símbolos e gera o programa executável.
            
            Carga: Responsável por definir os objetos de variáveis e funções de carga do código-fonte em memória para iniciar um novo processo;

            Execução: Após todo o processo, estes, são analisados e consequeentemente convertidos pelo processador para a memória final;

    - (5) questão 2. Como é organizado o espaço de memória de um processo?
        - Resposta:

            O processo é organizado em: Text, Data, Heap e Stack.

            Text: Responsável por conter o código-fonte a ser executado durante o processo, gerado durante a compilação e a inclusão de bibliotecas no código-fonte;

            Data: Responsável por conter as estáticas geradas pelo uso de softwares;

            Heap: Responsável por armazenar os dados para alocação dinâmica: calloc, malloc, free;

            Stack: Responsável por mater a pilha de execução do processo;


`Data de entrega: 05/07/2019`



>#### Capítulo 15 - Hardware de memória


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-15.pdf)
- Questões da avaliação
- página 21
    - (6) questão 1. Explique a diferença entre endereços lógicos e endereços físicos e as razões
que justificam o uso de endereços lógicos.

        - Resposta: 

            Endereços físicos (ou reais) são os endereços dos bytes de memória física do computador. Estes endereços são definidos pela quantidade de memória disponível na máquina. Já os endereços lógicos (ou virtuais) são os endereços de memória usados pelos processos e pelo sistema operacional e, portanto, usados pelo processador durante a execução. Estes endereços são definidos de acordo com o espaço de endereçamento do processador. Uma das razões para utilizar endereços lógicos é ocultar a organização complexa da memória física e simplificar os procedimentos de alocação da memória aos processos.

    - (7) página 7. Considerando a tabela de segmentos a seguir (com valores em decimal),
calcule os endereços físicos correspondentes aos endereços lógicos 0:45, 1:100, 2:90,
3:1.900 e 4:200.

        | Segmento |   0  |   1  |   2  |   3  |   4  |
        |----------|------|------|------|------|------|
        | Base     | 44   | 200  | 0    | 2.000| 1.200|
        | Limite   | 810  | 200  | 1.000| 1.000| 410  |

        - Resposta:

            | Segmento Lógico         |   0  |   1   |   2  |    3    |   4   |
            |------------------|------|-------|------|---------|-------| 
            | Offset Lógico          | 45   | 100   | 90   | 1.900   | 200   |
            | Endereço Físico  | 89   | 300   | 90   | Violação de segmentação | 1.400 |

    - (8) página 8. Considerando a tabela de páginas a seguir, com páginas de 500 bytes5,
informe os endereços físicos correspondentes aos endereços lógicos 414, 741, 1.995,
4.000 e 6.633, indicados em decimal.
        
        | Página | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
        |--------|---|---|---|---|---|---|---|---|---|---|----|----|----|----|----|----|
        | Quadro | 3 | 12| 6 | – | 9 | – | 2 | – | 0 | 5 | –  | –  | –  | 7  | –  | 1  |

        - Resposta:

            | Página | 0         | 1 | 2 | 3 | 4 | 5   | 6                 | 7  | 8  | 9  | 10 | 11    | 12 | 13 | 14  | 15 |
            |--------|-----------|---|---|---|---|-----|-------------------|----|----|----|----|-------|----|----|-----|----|
            | Quadro | 3 - 4.000 | 12| 6 | – | 9 | 741 | 2 - 1.995 - 6.633 | –  | 0  | 5  | –  | 1.995 | –  | 7  | 414 | 1  |


`Data de entrega: 05/07/2019`



>#### Capítulo 16 - Alocação de memória


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-16.pdf)
- Questões da avaliação
    - (9) página 9, questão 5. Considere um banco de memória com os seguintes “buracos” não-
contíguos:

        | B1 | B2 | B3 | B4 | B5 | B6 |
        |----|----|----|----|----|----|
        |10MB|4MB | 7MB| 30MB| 12MB | 20MB |

        Nesse banco de memória devem ser alocadas áreas de 5MB, 10MB e 2MB, nesta
        ordem, usando os algoritmos de alocação First-fit, Best-fit ou Worst-fit. Indique a
        alternativa correta:

        (A) Se usarmos Best-fit, o tamanho final do buraco B4 será de 6 Mbytes.

        (B) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes.

        (C) Se usarmos First-fit, o tamanho final do buraco B4 será de 24 Mbytes.

        (D) Se usarmos Best-fit, o tamanho final do buraco B5 será de 7 Mbytes.

        (E) Se usarmos Worst-fit, o tamanho final do buraco B4 será de 9 Mbytes.


        - Resposta: B


`Data de entrega: 05/07/2019`



>#### Capítulo 17 - Paginação em disco


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-17.pdf)
- Questões da avaliação
    - (10) página 19, questão 1. O que é uma falta de página? Quais são suas causa possíveis e como o
sistema operacional deve tratá-las?
        
        - Resposta: 
        
            Falta de página é quando um processo acessa uma página virtual e o MMU verifica se a mesma está localizada na memória RAM. Se estiver, faz o acesso ao endereço físico correspondente. Caso contrário, a MMU gera uma interrupção de falta de página que desvia a execução para o sistema operacional. O sistema operacional verifica se a página é válida, usando os flags de controle da tabela de páginas. Caso a página seja inválida, o processo tentou acessar um endereço inválido e deve ser abortado. Por outro lado, caso a página solicitada seja válida, o processo deve ser suspenso enquanto o sistema transfere a página de volta para a memória RAM e faz os ajustes necessários na tabela de páginas

            Possiveis causas:
            
            A página correspondente ao endereço requisitado não está carregada na memória;

            A página correspondente ao endereço de memória acessado está carregada, mas o seu estado corrente não foi atualizado no hardware;

            A página não é parte do programa, e portanto não é mapeada na memória do programa;

            O programa não tem privilégios suficientes para ler ou escrever a página;

            O acesso à página é legal, mas está mapeada como página sob demanda.
            
            Geralmente, o programa que recebe a exceção deve trata-lá, caso contrário, o sistema operacional realiza um padrão já implementado para tratar, deste modo, executa o término do processo que causou e mostra ao usuário que o programa apresenta um mal funcionamento, dependendo do S.O essa mensagem pode ser mostrando de diferentes maneiras, entretanto, todas com a mesma finalidade.


`Data de entrega: 05/07/2019`



#### Gestão de entradas e saídas

>#### Capítulo 19 - Hardware de entrada/saída


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-19.pdf)


>#### Capítulo 20 - Software de entrada e saída


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-20.pdf)
- Questões da avaliação
    - (1) Livro Sistemas operacionais, série livros didáticos, editora bookman. Por que os sistemas
operacionais exigem de todos os drivers de disposito (device-drivers) a mesma interface padrão?
Não seria mais apropriado deixar cada driver de dispositivo definir rotinas de interface que fazem
sentido para aquele tipo específico de dispositivo?
        - Resposta:


`Data de entrega: 12/07/2019`



>#### Capítulo 21 - Discos rígidos


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-21.pdf)
- Questões da avaliação
    - (2) página 12, questão 3. Você tem 4 discos rígidos de 8 TB cada, que pode organizar de diversas
formas. Indique os arranjos RAID que escolheria para obter:
        - Resposta: 


`Data de entrega: 12/07/2019`



#### Gestão de arquivos

>#### Capítulo 22 - O conceito de arquivo


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-22.pdf)
- Questões da avaliação
    - página 10
        - (3) questão 3. Apresente e comente as principais formas de atribuição de tipos aos arquivos.
Quais são as vantagens e desvantagens de cada uma?
            - Resposta:

        - (4) questão 4. Sobre as afirmações a seguir, relativas a formatos de arquivos, indique quais
são incorretas, justificando sua resposta:
            - Resposta:


`Data de entrega: 12/07/2019`



>#### Capítulo 23 - Uso de arquivos


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-23.pdf)
- Questões da avaliação
    - página 13
        - (5) questão 3. Comente as principais formas de acesso a arquivos. Qual o uso mais
apropriado para cada uma delas?
            - Resposta:

        - (6) questão 4. Apresente e explique os quatro principais tipos de travas sobre arquivos
compartilhados disponíveis no sistema operacional.
            - Resposta: 

        - (7) questão 5. Apresente e explique as quatro principais semânticas de acesso a arquivos
compartilhados em um sistema operacional.
             - Resposta: 


`Data de entrega: 12/07/2019`



>#### Capítulo 24 - Sistemas de arquivos


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-24.pdf)
- Questões da avaliação
    - (8) página 20, questão 1. Apresente a arquitetura de gerência de arquivos presente em um sistema
operacional típico, explicando seus principais elementos constituintes.
        - Resposta:

    - (9) página 23, questão 18. Explique como é efetuada a gerência de espaço livre através de
bitmaps.
        - Resposta:


`Data de entrega: 12/07/2019`


### Capítulo 25 - Diretórios e atalhos


- [Texto e lista de exercício](http://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-texto-25.pdf)
- Questões da avaliação
    - (10) página 10, questão 2. Do ponto de vista lógico, quais as principais diferenças entre a estrutura
de diretórios Unix e Windows?
        - Resposta:


`Data de entrega: 12/07/2019`