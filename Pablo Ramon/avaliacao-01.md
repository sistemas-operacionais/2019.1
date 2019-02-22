#Respostas das questões do capítulo 1 do livro de s.o.

## Info
## Aluno: Pablo Ramon Varela de Souza

Questão 01: Os dois principais objetivos do sistema operacional são a abstração e gerência de recursos.

Questão 02: A abstração é importante para as aplicações, pois ela permite que o desenvolvedor não precise 
adaptar o procedimento de uma operação (abrir um arquivo por exemplo) para cada dispositivo que existe. 
Abstraindo as especificidades do hardware, o software pode executar a operação de abrir um arquivo em vários 
dispositivos de armazenamento diferentes da mesma forma, apesar de que o hardware por baixo vai funcionar de forma diferente.

Questão 03: A maior vantagem, é a possibilidade de rodar diversos aplicativos ao mesmo tempo, utilizando o sistema de forma
multitarefa. Para que essa funcionalidade realmente funcione, tem de ser implementada uma forma de organizar quem vai usar o processador
de forma justa, organizando e resolvendo os conflitos que podem ocorrer durante o processo.

Questão 04: Um sistema operacional de tempo real, é aquele que possui um comportamento temporal previsível. Sendo sempre possível
saber o seu tempo de execução no melhor e pior caso. Os dois tipos diferentes de s.o. de tempo real são os *soft real-time systems* 
em que se um prazo for perdido, as consequências serão a degradação do próprio serviço prestado por esse sistema, e os *hard real-time
systems*, em que se um prazo for perdido os prejuízos podem ser muito mais graves, possibilitando o descontrole do objeto controlado 
pelo sistema, podendo causar danos humanos, financeiros e/ou ambientais.

Questão 05: Ele é quem cuida das abstrações principais utilizadas pelos programas aplicativos, além de ser responsável pela gerência dos recursos do hardware

Questão 06: Não, pois sem os níveis de privilégio qualquer programa poderia ter acesso irrestrito as instruções do processador podendo usar comandos perigosos como o HALT e o RESET comprometendo a segurança do mesmo.

Questão 07: Sim, mas só se houvesse como controlar esses outros dois níveis de acesso, para que não houvesse uma quebra de segurança.

Questão 08: Interrupções e exceções são eventos que desviam o fluxo de funcionamento do processador, sendo que as interrupções são externas e os eventos são gerados pelo processador. As traps são um tipo de interrupção causada por software.

Questão 09: Ao mascarar interrupções, elas são ignoradas pelo processador, usando um bit de máscara. Ao utilizar esse recurso por muito tempo os periféricos que tiveram suas interrupções mascaradas podem apresentar lentidão ou parar de funcionar. Para evitar isso os periféricos podem usar interrupções não-mascaráveis.

Questão 10: fopen é uma função da biblioteca de entrada e saída da linguagem C.

Questão 12: [T]
            [S]
            [E]
            [D]
            [M]
            [E]
            [K]
            [S]
            [K]
            [E]
           
Questão 13: (d) Pois poderia causar problema na bios
            (f) Pois poderia ser usada para fazer um periférico ou programa parar de funcionar.
            
Questão 14: (d) Acessos a memória são feitos usando chamadas de sistema.
            (e) Aqui também usa-se chamadas de sistema para garantir que o programa não está tentando apagar um arquivo do sistema.
            
Questão 15: [5]
            [8]
            [2]
            [3]
            [x]
            [x]
            [4]
            [1]
            [6]
            [7]
            
Questão 16: (c) III - Está errada pois não é o sistema operacional de rede, e sim o distribuído.
                IV - Está errada pois quem prioriza as tarefas que interagem com o usuário é o s.o multi-usuário, ou o desktop.
                
Questão 17: (e) I - Errada, pois uma máquina virtual de sistema suporta um S.O inteiro.
                IV - Errada, pois a manutenção não era simples, principalmente com o aumento do sistema.
                III - Errada, pois no micro-núcleo os componentes do sistema ficam no nível de usuário.
