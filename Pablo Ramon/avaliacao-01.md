### Respostas das questões do capítulo 1 do livro de s.o.

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

Questão 11: 
            
            Sistemas monolíticos:
            Vantagem: A maior vantagem é o desempenho gerado por todos os componentes trabalharem em modo núcleo.
            Deficiência: A manuntenção desses sistemas se tornam complexas, e se um componente perca o controle, o dano causado ao sistema pode ser muito grande, pois o problema desse componente pode se alastrar pelo resto do núcleo, pois esse componente defeituoso tem privilégios de núcleo.
            
            Sistemas em camadas:
            Vantagem: O núcleo dividido em camadas permite que os níveis de abstração tornem-se mais refinados de acordo com as camadas. A camada mais baixa realiza a interface direta com o hardware, ao subir nas camadas os níveis de abstração se tornam mais sofisticados, até chegar na última camada, onde é implementada a interface para as aplicações do usuário.
            Deficiência: O empilhamento de camadas de software faz com que cada pedido da aplicação demore mais tempo para chegar ao hardware, prejudicando o desempenho di sistema.
            
            Sistemas micronúcleo:
            Vantagem: A principal vantagem é a robustez e flexibilidade desse tipo de sistema, por exemplo, se um subsistema começar a apresentar problemas, os mecanismos de proteção dde memória e níveis de privilégio vão isolá-lo, impedindo que a instabilidade alastre-se. 
            Deficiências: O tempo de troca de mensagens entre os componentes pode ser muito elevado, prejudicando o desempenho do sistema.
            
            Máquinas virtuais:
            Vantagem: A independência do hardware para a utilização de diferentes sistemas operacionais, auxiliando no debug de sistemas experimentais, e testes.
            Desvantagem: Custo adicional de execução dos processos na máquina virtual, chegando a 50% nas plataformas que não suportam virtualização.
            
            
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
                
Questão 18: Ele precisa efetuar chamadas de sistema pois este utilitário usa o relógio do sistema (relógio de hardware) para efetuar os cálculos de data, e não é possível acessá-lo no modo usuário.

Questão 19: Existe alguma relação sim, algumas chamadas de função até mesmo possuem o nome parecido com as chamadas de sistema, por exemplo: fwrite - write   fclose - close. E quase sempre essas chamadas de função que são pegas pelo ltrace estão atreladas a uma chamada de sistema. Principalmente no caso do utilitário date que precisa acessar um dado do relógio de hardware, que só está disponível a nível de núcleo.
