
# Capítulo 1 Conceitos básicos  
## Aluno: Arthur Meireles da Silva – Matricula20181014040032 

### 1. Quais os dois principais objetivos dos sistemas operacionais?  
Um sistema operacional visa abstrair o acesso e gerenciar os recursos de hardware, provendo aos aplicativos um ambiente de execução abstrato, no qual o acesso aos recursos se faz através de interfaces simples, independentes das características e detalhes de baixo nível, e no qual os conﬂitos no uso do hardware são minimizados. 
 
### 2. Por que a abstração de recursos é importante para os desenvolvedores de aplicações? Ela tem utilidade para os desenvolvedores do próprio sistema operacional?  
A abstração de recursos é importante pois facilita a construção de programas aplicativos e permite que os aplicativos não fiquem restritos a um dispositivo de hardware. 
Sim, pois o desenvolvedor não tem que se preocupar com as especificações de cada hardware e não tem que mudar quase nada nos códigos quando os sistemas operacionais serão usados em diferentes hardwares. 

### 3. A gerência de atividades permite compartilhar o processador, executando mais de uma aplicação ao mesmo tempo. Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.  
Possibilita a criação de sistemas mais interativos, fornece abstrações para sincronizar atividades interdependentes e prover formas de comunicação entre ela e o desafio é distribuir a capacidade de processamento de forma justa entre as aplicações, evitando que uma aplicação monopolize esse recurso e respeitando as prioridades dos usuários. 

### 4. O que caracteriza um sistema operacional de tempo real? Quais as duas classificações de sistemas operacionais de tempo real e suas diferenças?  
A característica essencial é ter um comportamento temporal previsível (ou seja, seu tempo de resposta deve ser conhecido no melhor e pior caso de operação). 
As duas classificações são: 
Soft real-time systems, nos quais a perda de prazos implica na degradação do serviço prestado. 
Hard real-time systems tem como característica a perda de prazos pelo sistema pode perturbar o objeto controlado, com graves consequências humanas, econômicas ou ambientais. 

### 5. O que diferencia o núcleo do restante do sistema operacional?  
Núcleo é a base de todo o sistema operacional é a camada do sistema que está em contato com o hardware da máquina o usuário que utiliza a camada de interface não percebe 

### 6. Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê?  
Não, pois poderiam desestruturar o sistema inteiro e pode gerar conflitos e muita lentidão. 

### 7. O processador Pentium possui dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos sistemas operacionais para esse processador usa somente os níveis extremos (0 e 3, ou 002 e 112 ). Haveria alguma utilidade para os níveis intermediários?  
Sim, se existir uma divisão de processamento. 

### 8. Quais as diferenças entre interrupções, exceções e traps?  
Interrupções acontecem quando um controlador de periférico tem uma informação importante a fornecer ao processador, ele pode aguardar ou notificar e ao receber a requisição de interrupção, os circuitos do processador suspendem seu ﬂuxo de execução corrente e desviam para um endereço pré-deﬁnido, onde se encontra uma rotina de tratamento de interrupção. 
Exceções são eventos gerados pelo próprio processador que podem ocasionar o desvio da execução usando os mesmos mecanismos das interrupções. São gerados pelo próprio processador. 
Traps são interrupções que comuta o processador para o nível privilegiado e procede de forma parecida ao tratamento de uma interrupção. 

### 9. Quais as implicações de mascarar interrupções? O que pode ocorrer se o processador ignorar interrupções por muito tempo? O que poderia ser feito para evitar o mascaramento de interrupções?  
O processador perde tempo para verificar todos os periféricos e o hardware do sistema 

### 10. O comando em linguagem C fopen é uma chamada de sistema ou uma função de biblioteca? Por quê?  
Em C, cada arquivo aberto é representado por uma variável dinâmica do tipo FILE*, criada pela função fopen. As funções de acesso a arquivos são deﬁnidas na Biblioteca Padrão de Entrada/Saída (Standard I/O Library, deﬁnida no arquivo de cabeçalho stdio.h). 

### 11. Monte uma tabela com os benefícios e deficiências mais significativos das principais arquiteturas de sistemas operacionais.  
ARQUITERURA BENEFICIOS DEFICIÊNCIAS  
  
#### Sistemas monolíticos  
A grande vantagem dessa arquitetura é seu desempenho: qualquer componente do núcleo pode acessar os demais componentes, toda a memória ou mesmo dispositivos periféricos diretamente, pois não há 
  
 
A robustez e a facilidade de desenvolvimento. 
barreira sim pedindo esse acesso. Sistemas em camadas Domínio de redes de computadores  
Demora no pedido da aplicação 
Sistemas micronúcleo As principais vantagens dos sistemas micronúcleo são sua robustez e ﬂexibilidade: caso um subsistema tenha problemas, os mecanismos de proteção de memória e níveis de privilégio irão conﬁná-lo, impedindo que a instabilidade s e alastre ao restante do sistema. 
Os processos não podem se comunicar diretamente, devido às restrições impostas pelos mecanismos de proteção do hardware. 
Máquinas virtuais Robustez, a compactação e a flexibilidade 
O custo na troca de mensagens é alto 
 
### 12. Relacione as afirmações aos respectivos tipos de sistemas operacionais: distribuído (D), multiusuário (M), desktop (K), servidor (S), embarcado (E) ou de tempo real (T):  
[ T ] Deve ter um comportamento temporal previsível, com prazos de resposta claramente definidos. 
[ B ] Sistema operacional usado por uma empresa para executar seu banco de dados corporativo.  
[ E ] São tipicamente usados em telefones celulares e sistemas eletrônicos dedicados.  
[ R ] Neste tipo de sistema, a localização física dos recursos do sistema computacional é transparente para os usuários.  
[ M ] Todos os recursos do sistema têm proprietários e existem regras controlando o acesso aos mesmos pelos usuários.  
[ E ] A gerência de energia é muito importante neste tipo de sistema.  
[ K ] Sistema que prioriza a gerência da interface gráfica e a interação com o usuário.  
[ S ] Com,struído para gerenciar de forma eficiente grandes volumes de recursos.  
[ K ] O MacOS X é um exemplo típico deste tipo de sistema.  
[ E ] São sistemas operacionais compactos, construídos para executar aplicações específicas sobre plataformas com poucos recursos.  

### 13. A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê?  
(a) Ler uma porta de entrada/saída  
(b) Efetuar uma divisão inteira  
(c) Escrever um valor em uma posição de memória  
(d) Ajustar o valor do relógio do hardware  
(e) Ler o valor dos registradores do processador  
(f) Mascarar uma ou mais interrupções  
Instruções “perigosas” são proibidas para todo código executando neste nível. Além disso, o hardware restringe o uso da memória, permitindo o acesso somente a áreas previamente deﬁnidas. 

### 14. Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas:  
(a) Ler o relógio de tempo real do hardware.  
(b) Enviar um pacote através da rede.  
(c) Calcular uma exponenciação.  
(d) Preencher uma área de memória do processo com zeros.  
(e) Remover um arquivo do disco.  
Pois o sistema bloqueia ações diretas ao hardware 

### 15. Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um processo (observe que nem todas as ações indicadas fazem parte da sequência).  
[ 5 ] A rotina de tratamento da interrupção de software é ativada dentro do núcleo.  
[ 9 ] A função printf finaliza sua execução e devolve o controle ao código do processo.  
[ 2 ] A função de biblioteca printf recebe e processa os parâmetros de entrada (a string “Hello world”).  
[ 3 ] A função de biblioteca printf prepara os registradores para solicitar a chamada de sistema write()  
[ 7 ] O disco rígido gera uma interrupção indicando a conclusão da operação.  
[ 8 ] O escalonador escolhe o processo mais prioritário para execução.  
[ 4 ] Uma interrupção de software é acionada.  
[ 1 ] O processo chama a função printf da biblioteca C.  
[ 6 ] A operação de escrita no terminal é efetuada ou agendada pela rotina de tratamento da interrupção.  
[ 10 ] O controle volta para a função printf em modo usuário.  

### 16. Considere as afirmações a seguir, relativas aos diversos tipos de sistemas operacionais:  
I. Em um sistema operacional de tempo real, a rapidez de resposta é menos importante que a previsibilidade do tempo de resposta.  
II. Um sistema operacional multiusuário associa um proprietário a cada recurso do sistema e gerencia as permissões de acesso a esses recursos.  
III. Nos sistemas operacionais de rede a localização dos recursos é transparente para os usuários.  
IV. Um sistema operacional de tempo real deve priorizar as tarefas que interagem com o usuário.  
V. Um sistema operacional embarcado é projetado para operar em hardware com poucos recursos.  
Indique a alternativa correta:  
(a) As afirmações II e III estão corretas.  
(b) Apenas a afirmação V está correta.  
(c) As afirmações III e IV estão erradas.  
(d) As afirmações III, IV e V estão erradas.  
(e) Todas as afirmações estão erradas.  
Justifique as afirmações julgadas erradas (Assim: VII está errada porque ...):  
A terceira afirmativa está errada pois a característica de sistemas distribuídos e não de rede e a quarta afirmativa está errada pois são características do desktop. 

### 17. Considere as afirmações a seguir, relativas às diversas arquiteturas de sistemas operacionais:  
I. Uma máquina virtual de sistema é construída para suportar uma aplicação escrita em uma linguagem de programação específica, como Java.  
II. Um hipervisor convidado executa sobre um sistema operacional hospedeiro.  
III. Em um sistema operacional micronúcleo, os diversos componentes do sistema são construídos como módulos interconectados executando dentro do núcleo.  
IV. Núcleos monolíticos são muito utilizados devido à sua robustez e facilidade de manutenção.  
V. Em um sistema operacional micro-núcleo, as chamadas de sistema são implementadas através de trocas de mensagens.  
Indique a alternativa correta:  
(a) Todas as afirmações estão erradas.  
(b) As afirmações II e III estão corretas.  
(c) As afirmações II e IV estão erradas.  
(d) Apenas a afirmação V está correta.  
(e) As afirmações II e V estão corretas.  
Justifique as afirmações julgadas erradas (Assim: VII está errada porque ...):  
A primeira afirmação está equivocada pois a máquina virtual é feita para aguentar sistemas completos a terceira também está errada pois essa é umas características dos sistemas monolíticos e a quarta afirmativa está errada pois sistemas monolíticos tem manutenções complexas. 

### 18. O utilitário strace do UNIX permite observar a sequência de chamadas de sistema efetuadas por uma aplicação. Em um terminal UNIX, execute strace date para descobrir quais o arquivo aberto pela execução do utilitário date (que indica a data e hora correntes). Por que o utilitário date precisa fazer chamadas de sistema?  
Para o carregamento de bibliotecas compartilhadas e mapeamento da memória e emissão das informações sobre a data para a saída padrão 

### 19. O utilitário ltrace do UNIX permite observar a sequência de chamadas de biblioteca efetuadas por uma aplicação. Em um terminal UNIX, execute ltrace date para descobrir as funções de biblioteca chamadas pela execução do utilitário date (que indica a data e hora correntes). Pode ser observada alguma relação entre as chamadas de biblioteca e as chamadas de sistema observadas no item anterior? 
O date chama uma biblioteca para falar com o núcleo, a biblioteca manipula detalhes de baixo nível que tem relação coma passagem de informações para o núcleo e com a chamada da rotina privilegiada nome a conversão de convenções de chamadas. O system library prepara os parâmetros prepara o parâmetros me retorna resultados obtidos quando as chamadas de sistema são oferecidas pelas aplicações em modo usuário. 
