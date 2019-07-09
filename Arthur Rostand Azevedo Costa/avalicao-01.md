##Questões do primeiro capítulo do livro

1. Abstração e gerência dos recursos de um sistema.

2. A abstração de recursos é importante para ambos os desenvolvedores de aplicativos e do próprio sistema operacional porque remove a necessidade de se pensar em tipos específicos de hardware, abstraindo conceitos variados em um só. Isso não só simplifica o desenvolvimento de novos recursos, como também aumenta a variedade de usos de recursos e hardwares envolvidos.

3. A principal vantagem seria, logicamente, a possibilidade de realizar múltiplas tarefas no mesmo computador, todas numa velocidade adequada e com possível interação entre si. E o maior desafio na sua implementação seria quebrar a barreira de abstração dos dados de cada aplicativo, dando assim a chance de todos serem processados simultaneamente, como se houvesse um processador único para cada.

4. São sistemas nos quais o tempo é essencial e que possuem um comportamento temporal previsível. É necessário que tenha um tempo de resposta prevísivel em qualquer caso de operação. Eles se dividem em críticos e não críticos, sendo os primeiros usados em casos em cuja falha resultaria em graves consequencias humanas, economicas ou ambientais; enquanto os últimos não possuem consequencias tão graves.

5. Como o próprio nome diz, o núcleo é o centro do sistema operacional pertencente a camada mais baixa de um sistema e gerencia os recursos dos hardwares usados pelas aplicações. As demais partes do sistema são responsáveis por auxiliar o núcleo de maneiras variadas (como ajudando na comunicação do núcleo com hardwares específicos, ou adicionando uma interface gráfica ou ainda auxiliando na inicialização do mesmo...).

 6. Não seria possível criar um SO seguro sem ter níveis de privilégio no processador, pois sem eles qualquer aplicação teria acesso total a todos os recursos do processador, inviabilizando qualquer nível de segurança.
 
 7. Suponho que os níveis intermediários sirvam para isolar processos específicos, ou para assinalar uma parte predeterminada do processador para tais processos, ou como medida de segurança para evitar conflitos entre processos.
 
 8. Interrupções são necessárias para a adição de informação vinda de periféricos ou aplicativos ao processador, sem precisar que o mesmo fique o tempo todo checando por informação vinda de tais fontes. Geralmente interrupções eram mais comuns vindas de periféricos (como o teclado), mas quando são feitas por softwares que precisam se comunicar com aréas de hardware separadas pelo sistema, essas interrupções são conhecidas por traps. Já uma exceção é causada por um erro de sistema que precisa ser tratado, quando o processo toma uma rota diferente da normal (uma exceção).
 
 9. Mascarar uma interrupção é diminuir sua prioridade de tratamento em relação ao processador, para dar prioridade a outras interrupções "mais importantes". Apesar de extremamente útil, o seu uso pode atrasar o sistema, prejudicando o desempenho.
 
 10. O comando fopen da linguagem C é uma chamada de biblioteca, pois não possui acesso direto ao sistema e é pertencente a libC.
 
 11. Sistema Monolítico: Vantagens: Desempenho (todas as partes se comunicam diretamente) e Compactação do sistema. Desvantagens: Na falha de algum componente, o sistema todo falha e a complexidade de manutenção/evolução.
 Sistema de Camadas: Vantagens: Boa abstração (facilidade de manutenção e evolução) Desvantagens: Perda de desempenho pela demora em comunicação das partes.
 Sistema Micronúcleo: Vantagens: robustez e segurança (caso um problema ocorra numa parte do sistema, é fácil isolá-lo e evitar que o erro se alastre) e boa customização do sistema operacional. Desvantagens: Perda de desempenho pela demora em comunicação das partes.
 
 12. T ; S ; E ; D ; M ; E ; K ; S ; K ; E .
 
 13. D) o relógio do hardware é importante para muitos processos (especialmente de tempo real) e não deve ser modificado pelo usuário ; E) a leitura do valor do registrador do processador deveria ser feita por meio de abstração, para simplificar o processo de processamento de informação ; F) a mascaragem de uma operação deve ser de total controle do processador, sem o controle do usuário que o fará de forma indireta, controlada pelo próprio núcleo.
 
 14. C) o cálculo de uma exponenciação necessita de mais recursos que os demais cálculos aritméticos ; D) memória do processador só pode ser acessada através de um syscall.
 
 15. O processo chama a funçãoprintfda biblioteca C. -> A função de bibliotecaprintfrecebe e processa os parâmetros de entrada (astring “Hello world”) -> Uma interrupção de software é acionada. -> A rotina de tratamento da interrupção de software é ativada dentro do núcleo. -> O escalonador escolhe o processo mais prioritário para execução. -> A operação de escrita no terminal é efetuada ou agendada pela rotina detratamento da interrupção -> A funçãoprintffinaliza sua execução e devolve o controle ao código do processo
 
 16. C) Não é necessário que a localização dos recursos seja transparente para os usuários, apenas que os recursos estejam disponíveis, não importando a distância. A interação com o usuário não é tão necessária quanto a necessidade de minimizar esperas e latências previsíveis.
 
 17. 
