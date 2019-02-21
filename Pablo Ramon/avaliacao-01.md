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
