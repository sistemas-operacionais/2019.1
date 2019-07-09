# Exercicios Capitulo 1 
## Aluno: Emerson Breno Martins Carvalho

1. Quais os dois principais objetivos dos sistemas operacionais?

R: Abstração e Gerência de acesso e recursos.

2. Por que a abstração de recursos é importante para os desenvolvedores de aplicações? Ela tem utilidade para os desenvolvedores do próprio sistema operacional?

R: A abstraçaõ de recursos é bastante importante para os desenvolvedores porque ela tem a função de facilitar o trabalho dos desenvolvedores de algumas maneiras, dentre as quais podemos citar o provimento de interfaces de acesso aos dispositivos a serem utilizados, evitando assim que o programador tenha que trabalhar em um 'baixo nível' para efetuar operações simples, como por exemplo a abertura de arquivos. Além disso, a abstração de recursos também é responsavel por tornar os aplicativos indepentens do hardware utilizado e definir interfaces de acesso homogeneas que funcionam para dispositivos com diferentes tecnologias.

3. A gerência de atividades permite compartilhar o processador, executando mais de uma aplicação ao mesmo tempo. Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.

R: Uma das vantangens é a possibilidade de várias tarefas serem realizadas simultamente sem que seja necessário que uma delas seja encerrada para que outra possa ser concluida. Entretanto, ao paralelizar essas atividades a complexidade do gerênciamento aumenta, podendo gerar conflitos entre processos que querem utilizar o mesmo hardware simultaneamente, o que em alguns casos é impossível. 

4. O que caracteriza um sistema operacional de tempo real? Quais as duas classificações de sistemas operacionais de tempo real e suas diferenças?

R: São sistemas que necessitam de um comportamento temporal previsivel, assim p tempo de melhor e pior caso de resposta do sistema tem que ser conhecido previamente. Nós temos o 'soft real-time system' que resulta em degradação do serviço associado ao sistema em caso de 'lag' no processo de execução, e o 'hard real-time system' que pode ocasionar sérias consequências humanas, economicas ou ambientais em caso de 'lag' no processo de execução.

5. O que diferencia o núcleo do restante do sistema operacional?

R: O núcleo é o coração do sistema operacional, é o ele o quem tem a responsabilidade de gerenciar os recursos do hardware utilizados nas aplicações em execução no sistema.

6. Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê?

R: Não, pois assim seria impossível controlar o acesso a recursos que só deveriam estar disponiveis para elementos especificos do sistema, ou seja, não teriamos como garantir que um "recurso de gerência" estaria disponivel apenas para o "gerente". 

7. O processador Pentium possui dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos sistemas operacionais para esse processador usa somente os níveis extremos (0 e 3, ou 002 e 112). Haveria alguma utilidade para os níveis intermediários?

R: A maioria dos SO's utilizam apenas 2 níveis para diferenciar os privilegios, então depende do sistema.

8. Quais as diferenças entre interrupções, exceções e traps?

R: A interrupção é causada através de hardwares periféricos para que o processador suspenda e desvie seu fluxo de execução atual para um endereço pré-definido, onde existe uma rotina que irá tratar a interrupção. Já a exceção ocorre quando o próprio processador gera um evento que ocasiona em uma interrupção. Enquanto a trap é um evento gerado por software.

9. Quais as implicações de mascarar interrupções? O que pode ocorrer se o processador ignorar interrupções por muito tempo? O que poderia ser feito para evitar o mascaramento de interrupções?

R: Ao ignorar por muito tempo as interrupções o processador pode se deparar com uma espécie de 'gargalo' ao acumular operações ignoradas.

10. O comando em linguagem C fopen é uma chamada de sistema ou uma função de biblioteca? Por quê?

R: O comando fopen é uma chamada de sistema que é efetuada atráves de uma biblioteca da linguagem C.

11. Monte uma tabela com os benefícios e deficiências mais significativos das principais arquiteturas de sistemas operacionais.

R:  Sistema  Monolíticos
        Vantagem: Desempenho
        Desvantagem: Problemas na Robustez e Facilidade de Desenvolvimento


12. Relacione as afirmações aos respectivos tipos de sistemas operacionais: distribuído (D), multi-usuário (M), desktop (K), servidor (S), embarcado (E) ou de tempo-real (T):

    [**T**] Deve ter um comportamento temporal previsível, com prazos de resposta claramente definidos.
    
    [**S**] Sistema operacional usado por uma empresa para executar seu banco de dados corporativo.
    
    [**E**] São tipicamente usados em telefones celulares e sistemas eletrônicos dedicados.
    
    [**D**] Neste tipo de sistema, a localização física dos recursos do sistema computacional é transparente para os usuários.
    
    [**M**] Todos os recursos do sistema têm proprietários e existem regras controlando o acesso aos mesmos pelos usuários.
    
    [**E**] A gerência de energia é muito importante neste tipo de sistema.
    
    [**K**] Sistema que prioriza a gerência da interface gráfica e a interação com o usuário.
    
    [**S**] Construído para gerenciar de forma eficiente grandes volumes de recursos.
    
    [**K**] O MacOS X é um exemplo típico deste tipo de sistema.
    
    [**E**] São sistemas operacionais compactos, construídos para executar aplicações específicas sobre plataformas com poucos recursos.

13. A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê?
    
    (a) Ler uma porta de entrada/saída
    
    (b) Efetuar uma divisão inteira
    
    **(c) Escrever um valor em uma posição de memória**
    
    (d) Ajustar o valor do relógio do hardware
    
    (e) Ler o valor dos registradores do processador
    
    **(f) Mascarar uma ou mais interrupções**

14. Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas:
    
    (a) Ler o relógio de tempo real do hardware.
    
    (b) Enviar um pacote através da rede.
    
    (c) Calcular uma exponenciação.
    
    **(d) Preencher uma área de memória do processo com zeros.**
    
    (e) Remover um arquivo do disco.

15. Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um processo (observe que nem todas as ações indicadas fazem parte da seqüência).
    
    [ ] A rotina de tratamento da interrupção de software é ativada dentro do núcleo.
    
    [5] A função printf finaliza sua execução e devolve o controle ao código do
    processo.
    
    [2] A função de biblioteca printf recebe e processa os parâmetros de entrada (a
    string “Hello world”).
    
    [3] A função de biblioteca printf prepara os registradores para solicitar a
    chamada de sistema write()
    
    [ ] O disco rígido gera uma interrupção indicando a conclusão da operação.
    
    [ ] O escalonador escolhe o processo mais prioritário para execução.
    
    [ ] Uma interrupção de software é acionada.
    
    [1] O processo chama a função printf da biblioteca C.
    
    [4] A operação de escrita no terminal é efetuada ou agendada pela rotina de
    tratamento da interrupção.
    
    [ ] O controle volta para a função printf em modo usuário.

16. Considere as afirmações a seguir, relativas aos diversos tipos de sistemas operacionais:
    I. Em um sistema operacional de tempo real, a rapidez de resposta é menos importante que a previsibilidade do tempo de resposta.
    II. Um sistema operacional multi-usuários associa um proprietário a cada recurso do sistema e gerencia as permissões de acesso a esses recursos.
    III. Nos sistemas operacionais de rede a localização dos recursos é transparente para os usuários.
    IV. Um sistema operacional de tempo real deve priorizar as tarefas que interagem com o usuário.
    V. Um sistema operacional embarcado é projetado para operar em hardware com poucos recursos.

    Indique a alternativa correta:
    
    
    (a) As afirmações II e III estão corretas.
    
    (b) Apenas a afirmação V está correta.
    
    **(c) As afirmações III e IV estão erradas.**
    
    (d) As afirmações III, IV e V estão erradas.
    
    (e) Todas as afirmações estão erradas.
    
17. Considere as afirmações a seguir, relativas às diversas arquiteturas de sistemas operacionais:
    I. Uma máquina virtual de sistema é contruída para suportar uma aplicação escrita em uma linguagem de programação específica, como Java.
    II. Um hipervisor convidado executa sobre um sistema operacional hospedeiro.
    III. Em um sistema operacional micro-núcleo, os diversos componentes do sistema são construídos como módulos interconectados executando dentro do núcleo.
    IV. Núcleos monolíticos são muito utilizados devido à sua robustez e facilidade de manutenção.
    V. Em um sistema operacional micro-núcleo, as chamadas de sistema são implementadas através de trocas de mensagens.
    
    Indique a alternativa correta:
    
    
    (a) Todas as afirmações estão erradas.
    
    (b) As afirmações II e III estão corretas.
    
    (c) As afirmações II e IV estão erradas.
    
    (d) Apenas a afirmação V está correta.
    
    **(e) As afirmações II e V estão corretas.**    

18. O utilitário strace do UNIX permite observar a sequência de chamadas de sistem efetuadas por uma aplicação. Em um terminal UNIX, execute strace date para descobrir quais os arquivos abertos pela execução do utilitário date (que indica a data e hora correntes). Por que o utilitário date precisa fazer chamadas de sistema?

R: As chamadas são efetuadas para que a memória seja mapeada e as bibliotecas necessárias sejam carregadas, de modo que as informações sobre a data possam ser carregadas.

19. O utilitário ltrace do UNIX permite observar a sequência de chamadas de biblioteca efetuadas por uma aplicação. Em um terminal UNIX, execute ltrace date para descobrir as funções de biblioteca chamadas pela execução do utilitário date (que indica a data e hora correntes). Pode ser observada alguma relação entre as chamadas de biblioteca e as chamadas de sistema observadas no ítem anterior?

R:As bibliotecas são utilizadas para que a comunicação de baixo nível ocorra.
