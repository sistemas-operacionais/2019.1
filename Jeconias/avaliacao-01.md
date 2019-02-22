# Sistemas Operacionais: Conceitos e Mecanismos
### Capítulo 1 - Exercícios

**1. Quais os dois principais objetivos dos sistemas operacionais?**
`R:`
**2. Por que a abstração de recursos é importante para os desenvolvedores de aplicações? Ela tem utilidade para os desenvolvedores do próprio sistema operacional?**
`R:`
**3. A gerência de atividades permite compartilhar o processador, executando mais de uma aplicação ao mesmo tempo. Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.**
`R:`
**4. O que caracteriza um sistema operacional de tempo real? Quais as duas classificações de sistemas operacionais de tempo real e suas diferenças?**
`R:`
**5. O que diferencia o núcleo do restante do sistema operacional?**
`R:`
**6. Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê?**
`R:`
**7. O processador Pentium possui dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos sistemas operacionais para esse processador usa somente os níveis extremos (0 e 3, ou 00<sub>2</sub> e 11<sub>2</sub>). Haveria alguma utilidade para os níveis intermediários?**
`R:`
**8. Quais as diferenças entre interrupções, exceções e traps?**
`R:`
**9. Quais as implicações de mascarar interrupções? O que pode ocorrer se o processador ignorar interrupções por muito tempo? O que poderia ser feito para evitar o mascaramento de interrupções?**
`R:`
**10. O comando em linguagem C fopen é uma chamada de sistema ou uma função de biblioteca? Por quê?**
`É uma função da biblioteca pelo simples motivo dela também ser responsável pela entrada de dados. `
**11. Monte uma tabela com os benefícios e deficiências mais significativos das principais arquiteturas de sistemas operacionais.**
`R:`
**12. Relacione as afirmações aos respectivos tipos de sistemas operacionais: distribuído (D), multi-usuário (M), desktop (K), servidor (S), embarcado (E) ou de tempo-real (T):**
(T) Deve ter um comportamento temporal previsível, com prazos de resposta claramente definidos.
(S) Sistema operacional usado por uma empresa para executar seu banco de dados corporativo.
(E) São tipicamente usados em telefones celulares e sistemas eletrônicos dedicados.
(K) Neste tipo de sistema, a localização física dos recursos do sistema computacional é transparente para os usuários.
(M) Todos os recursos do sistema têm proprietários e existem regras controlando o acesso aos mesmos pelos usuários.
(E) A gerência de energia é muito importante neste tipo de sistema.
(K) Sistema que prioriza a gerência da interface gráfica e a interação com o usuário.
(S) Construído para gerenciar de forma eficiente grandes volumes de recursos.
(D) O MacOS X é um exemplo típico deste tipo de sistema.
(E) São sistemas operacionais compactos, construídos para executar aplicações específicas sobre plataformas com poucos recursos.

**13. A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê?**
[ ] Ler uma porta de entrada/saída
[ ] Efetuar uma divisão inteira
[x] Escrever um valor em uma posição de memória
[ ] Ajustar o valor do relógio do hardware
[x] Ler o valor dos registradores do processador
[x] Mascarar uma ou mais interrupções

**14. Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas:**
[ ] Ler o relógio de tempo real do hardware.
[ ] Enviar um pacote através da rede.
[ ] Calcular uma exponenciação.
[x] Preencher uma área de memória do processo com zeros.
[x] Remover um arquivo do disco.
`Pelo motivo que essas ações devem ser efetuadas diretamente no hardware.`

**15. Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um processo (observe que nem todas as ações indicadas fazem parte da seqüência).**
( ) A rotina de tratamento da interrupção de software é ativada dentro do núcleo.
( ) A função printf finaliza sua execução e devolve o controle ao código do
processo.
( ) A função de biblioteca printf recebe e processa os parâmetros de entrada (a
string “Hello world”).
( ) A função de biblioteca printf prepara os registradores para solicitar a
chamada de sistema write()
( ) O disco rígido gera uma interrupção indicando a conclusão da operação.
( ) O escalonador escolhe o processo mais prioritário para execução.
( ) Uma interrupção de software é acionada.
( ) O processo chama a função printf da biblioteca C.
( ) A operação de escrita no terminal é efetuada ou agendada pela rotina de
tratamento da interrupção.
( ) O controle volta para a função printf em modo usuário.

**16. Considere as afirmações a seguir, relativas aos diversos tipos de sistemas operacionais:**
I. Em um sistema operacional de tempo real, a rapidez de resposta é menos importante que a previsibilidade do tempo de resposta.
II. Um sistema operacional multi-usuários associa um proprietário a cada
recurso do sistema e gerencia as permissões de acesso a esses recursos.
III. Nos sistemas operacionais de rede a localização dos recursos é transparente para os usuários.
IV. Um sistema operacional de tempo real deve priorizar as tarefas que interagem
com o usuário.
V. Um sistema operacional embarcado é projetado para operar em hardware com poucos recursos.
Indique a alternativa correta:
[ ] As afirmações II e III estão corretas.
[ ] Apenas a afirmação V está correta.
[ ] As afirmações III e IV estão erradas.
[ ] As afirmações III, IV e V estão erradas.
[ ] Todas as afirmações estão erradas.

Justifique as afirmações julgadas erradas (Assim: VII está errada porque ...):
`III e IV estão erradas, pois descrevem o sistema operacional distribuído.`

**17. Considere as afirmações a seguir, relativas às diversas arquiteturas de sistemas
operacionais:**
I. Uma máquina virtual de sistema é contruída para suportar uma aplicação
escrita em uma linguagem de programação específica, como Java.
II. Um hipervisor convidado executa sobre um sistema operacional hospedeiro.
III. Em um sistema operacional micro-núcleo, os diversos componentes do
sistema são construídos como módulos interconectados executando dentro
do núcleo.
IV. Núcleos monolíticos são muito utilizados devido à sua robustez e facilidade
de manutenção.
V. Em um sistema operacional micro-núcleo, as chamadas de sistema são
implementadas através de trocas de mensagens.
Indique a alternativa correta:
( ) Todas as afirmações estão erradas.
( ) As afirmações II e III estão corretas.
( ) As afirmações II e IV estão erradas.
( ) Apenas a afirmação V está correta.
( ) As afirmações II e V estão corretas.
Justifique as afirmações julgadas erradas (Assim: VII está errada porque ...):

**18. O utilitário strace do UNIX permite observar a sequência de chamadas de sistema efetuadas por uma aplicação. Em um terminal UNIX, execute strace date para descobrir quais os arquivos abertos pela execução do utilitário date (que indica a data e hora correntes). Por que o utilitário date precisa fazer chamadas de sistema?**
`R:`
**19. O utilitário ltrace do UNIX permite observar a sequência de chamadas de biblioteca efetuadas por uma aplicação. Em um terminal UNIX, execute ltrace date para descobrir as funções de biblioteca chamadas pela execução do utilitário date (que indica a data e hora correntes). Pode ser observada alguma relação entre as chamadas de biblioteca e as chamadas de sistema observadas no ítem anterior?**
`R:`