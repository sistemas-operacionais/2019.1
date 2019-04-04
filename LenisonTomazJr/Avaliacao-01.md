### Exercícios do capítulo 1 - Conceitos básicos


1- Quais os dois principais objetivos dos sistemas operacionais? 

    -Abstração de recursos de hardware e gerência de recurso.
 
2- Por que a abstração de recursos é importante para os desenvolvedores de aplicações? Ela tem utilidade para os desenvolvedores
do próprio sistema operacional?


    -Acessar diretamente os recursos do hardware de um sistema pode ser uma tarefa muito complexa, devido às características 
    específicas de cada dispositivo físico e a complexidade de suas interfaces, e isso atrapalha o desenvolvimento de 	  aplicações,por isso a abstração de recurso de hardware e importante para os desenvolvedores de aplicações, pois assim o desenvolvedor não precisa “baixar o nível “quando precisar de recursos de hardware, o próprio sistemas irá dar ferramentas  para ter acesso aos recursos mais  facilmente e mais rápido. 
  
    -Sim.
  
  
3-A gerência de atividades permite compartilhar o processador, executando mais de uma aplicação ao mesmo tempo.
Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.

      -Vantagens: -Evita a monopolização de recursos.  

       - Permite a construção de sistemas mais interativos. 

      - Fornece abstrações para sincronizar atividades interdependentes e prover formas de comunicação entre elas.
                  
      -Dificuldades de implementação: as funcionalidades de um sistema operacional são interdependentes, ou seja, 
      uma funcionalidade influencia em outra, por exemplo, a gerência do processador depende de aspectos da gerência de   	memória assim como a gerência de memória depende da gerência de dispositivos e da gerência de proteção. 
      
      
4-O que caracteriza um sistema operacional de tempo real? Quais as duas classificações de sistemas operacionais de tempo real 
e suas diferenças?    

      -Um sistema operacional de tempo real tem como características a execução de múltiplas tarefas, tempo de resposta ao um 
      evento pré-definido e previsibilidade. O sistema operacional de tempo real é dividido em 2 categorias: soft real-time 
      systems e hard real-time systems, a diferença desses sistemas está na implicação que ele pode gerar caso perca o tempo 
      de tarefa, por exemplo , o hard real-time tem que possuir um tempo de tarefa bem definido e não pode perde o tempo de 
      tarefa , pois a perca desse tempo de tarefa  pode perturbar o objeto controlado , causando grandes consequências 
      humanas, econômicas ou ambientais, por exemplo, sistema que controla o ABS de um carro ou um sistema que controla a 
      turbina de um avião. soft real-time systems a perca do tempo de tarefa irá gera uma perca de serviço prestado, mas não 
      causara grandes danos, ou seja, uma falha é aceitável, por exemplo, o sistema que controla o leitor de DVD. 
      
5-O que diferencia o núcleo do restante do sistema operacional? 
     -O núcleo é responsável pela gerencia de recursos do hardware e também é responsável da criação da abstração utilizada 
     pelos programas.
  
	
6-Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê?

    -Não, pois se o processador não possuir níveis de privilegio os usuários e aplicativos teriam total acesso ao hardware 
    podendo interferir nas configurações e na gerência e isso acabaria desestabilizando o sistema inteiro. 


7-O processador Pentium possui dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos 
sistemas operacionais para esse processador usa somente os níveis extremos (0 e 3, ou 002 e 112). Haveria alguma utilidade 
para os níveis intermediários? 

      -Sim, mas só se houvesse necessidade de processamento entre os níveis.
      
      
8-Quais as diferenças entre interrupções, exceções e traps?
    -Interrupções são geradas por eventos externos, exceções são Eventos como instruções ilegais 
    (inexistentes ou com operandos inválidos) e trap são geradas por software. 
 
 
10-. O comando em linguagem C fopen é uma chamada de sistema ou uma função de biblioteca? Por quê? 

      -Fopen é uma função da biblioteca padrão da linguagem C definida no cabeçalho do Stdio.h
			
			
    
 11-Monte uma tabela com os benefícios e deficiências mais significativos das principais arquiteturas de sistemas operacionais.
 	
	
   | Arquiteturas  de sistemas operacionais      |    Benefícios          	   |      Deficiências| 
                         	   
												                       	   
|Sistema monolítico|      |-Desempenho |a robustez e a facilidade de desenvolvimento. |
                                                    
|Sistema em camada|       |-Domínio das redes |Demora no pedido da aplicação.| 
                                                   
|Sistema micronúcleo|     |-robustez e flexibilidade|o custo associado às trocas de mensagens entre componentes pode ser bastante elevado |
                                                       
|Máquinas virtuais|    |-Executar diferentes sistemas|custo adicional de execução dos processos na máquina virtual operacionais sobre o mesmo  hardware, simultaneamente|	 	 
												                           
		
		
		
													
12- Relacione as afirmações aos respectivos tipos de sistemas operacionais: distribuído (D), multiusuário (M), desktop (K), 
servidor (S), embarcado (E) ou de tempo real (T): 		

[ T] Deve ter um comportamento temporal previsível, com prazos de resposta claramente definidos.

[ s] Sistema operacional usado por uma empresa para executar seu banco de dados corporativo. 

[ E] São tipicamente usados em telefones celulares e sistemas eletrônicos dedicados.  

[S ] Neste tipo de sistema, a localização física dos recursos do sistema computacional é transparente para os usuários.  

[ M] Todos os recursos do sistema têm proprietários e existem regras controlando o acesso aos mesmos pelos usuários.  

[ E] A gerência de energia é muito importante neste tipo de sistema. 

[K ] Sistema que prioriza a gerência da interface gráfica e a interação com o usuário.  

[S ] Construído para gerenciar de forma eficiente grandes volumes de recursos.  

[K ] O MacOS X é um exemplo típico deste tipo de sistema. 

[E ] São sistemas operacionais compactos, construídos para executar aplicações específicas sobre plataformas com poucos 
recursos. 
						
						
13- A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. 
Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê? 

(a) Ler uma porta de entrada/saída  

(b) Efetuar uma divisão inteira  

(c) Escrever um valor em uma posição de memória  - e responsabilidade do hardware 

(d) Ajustar o valor do relógio do hardware  

(e) Ler o valor dos registradores do processador  -e responsabilidade do hardware 

(f) Mascarar uma ou mais interrupções - e responsabilidade do hardware 


 14- Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique 
 quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas:  

(a) Ler o relógio de tempo real do hardware.  

(b) Enviar um pacote através da rede.  

(c) Calcular uma exponenciação.  

(d) Preencher uma área de memória do processo com zeros. -e responsabilidade do hardware   

(e) Remover um arquivo do disco. 

    
 
 15- Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um 
 processo (observe que nem todas as ações indicadas fazem parte da seqüência). 

 [05 ] A rotina de tratamento da interrupção de software é ativada dentro do núcleo.  

[08] A função printf finaliza sua execução e devolve o controle ao código do processo.  

[03] A função de biblioteca printf recebe e processa os parâmetros de entrada (a string “Hello world”). 

 [02] A função de biblioteca printf prepara os registradores para solicitar a chamada de sistema write() 

 [06] O disco rígido gera uma interrupção indicando a conclusão da operação.  

[ 04] O escalonador escolhe o processo mais prioritário para execução.  

[07 ] Uma interrupção de software é acionada.  

[01] O processo chama a função printf da biblioteca C. 

 [ 10] A operação de escrita no terminal é efetuada ou agendada pela rotina de tratamento da interrupção.  

[ 09] O controle volta para a função printf em modo usuário. 




16-. Considere as afirmações a seguir, relativas aos diversos tipos de sistemas operacionais:  

I. Em um sistema operacional de tempo real, a rapidez de resposta é menos importante que a previsibilidade do tempo de resposta.  

II. Um sistema operacional multi-usuários associa um proprietário a cada recurso do sistema e gerencia as permissões de acesso a esses recursos. 

 III. Nos sistemas operacionais de rede a localização dos recursos é transparente para os usuários.  

IV. Um sistema operacional de tempo real deve priorizar as tarefas que interagem com o usuário.  

V. Um sistema operacional embarcado é projetado para operar em hardware com poucos recursos. 

 Indique a alternativa correta: 

 (a) As afirmações II e III estão corretas.  

(b) Apenas a afirmação V está correta. 

 (c) As afirmações III e IV estão erradas. - Alternativa correta 

 (d) As afirmações III, IV e V estão erradas.  

(e) Todas as afirmações estão erradas. 

 
III está errado pois é uma característica de sistemas distribuídos e não de rede;  

IV está errado pois é uma característica de sistemas desktop e não de tempo real. 





17- Considere as afirmações a seguir, relativas às diversas arquiteturas de sistemas operacionais:  

I. Uma máquina virtual de sistema é construída para suportar uma aplicação escrita em uma linguagem de programação específica, como Java.  

II. Um hipervisor convidado executa sobre um sistema operacional hospedeiro.  

III. Em um sistema operacional micro-núcleo, os diversos componentes do sistema são construídos como módulos interconectados executando dentro do núcleo.  

IV. Núcleos monolíticos são muito utilizados devido à sua robustez e facilidade de manutenção. 

 V. Em um sistema operacional micro-núcleo, as chamadas de sistema são implementadas através de trocas de mensagens. Indique a alternativa correta:  

(a) Todas as afirmações estão erradas.  

(b) As afirmações II e III estão corretas.  

(c) As afirmações II e IV estão erradas. 

 (d) Apenas a afirmação V está correta.  

(e) As afirmações II e V estão corretas. - Alternativa correta. 

 

I está errada pois uma máquina virtual de sistema é construída para sistemas operacionais convidados ou nativos;  

III está errada, pois isso é uma característica de uns sistemas monolíticos e não micro-núcleos;  

IV está errada pois sistemas monolíticos não tem uma manutenção fácil . 
