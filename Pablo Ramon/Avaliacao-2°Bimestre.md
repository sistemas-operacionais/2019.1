**Avaliação**  
**Discente: Pablo Ramon Varela de Souza**  
**Matricula: 20181014040009**  
  
1) Uma vez detectado um impasse e identificadas as tarefas e recursos envolvidos,
o sistema deve proceder à resolução do impasse, que pode ser feita de duas formas:
Eliminando as tarefas ou Retrocedendo-as.  
Na eliminação de tarefas o sistema deve escolher
uma ou mais tarefas para eliminar liberando os recursos que estavam sendo presos para permitir
que as outras tarefas que esperavam por esses recursos possam continuar as suas execuções.    
Na tática de retroceder as tarefas elas são parcialmente desfeitas, retornando o sistema a um
estado seguro continuando a execução dali. Para isso é necessário manter o estado parcial das tarefas
para que possa ser efetuado o *rollback*.  
  
2)  
O ciclo na primeira imagem que gera um impasse é: t1 -> r2 -> t2 -> r1 -> t1  
Na segunda imagem não há um ciclo com impasse pois o ciclo t1 -> r2 -> t2 -> r3 -> t3 -> r1 -> t1
pode ser resolvido se o t4 liberar uma instância de r3.  
  
3)  
Exclusão mútua: Cada carro só pode seguir em uma direção por vez e na sua própria 'mão' do trânsito.  
Posse e Espera: Cada carro pode avançar na sua rua sem liberar os 'recursos' que é o caminho percorrido 
mas ainda sendo possível pedir por recursos compartilhados (espaços dos outros carros que estão passando)  
Não-Preempção: O sistema não pode retirar o espaço dos carros depois que eles já começaram a passar.
Espera Circular: Na forma como eles estão cada carro sempre vai estar esperando os recursos do carro a sua
frente, e os da ponta estarão esperando os recursos dos carros das pontas das outras fileiras, formando o círculo.  
Para impedir isso poderia somente permitir que um semáforo fosse ligado por vez, e com limite de tempo.  
Exemplo: Semáforo da fileira amarela fica ligado por um minuto, depois o semáforo da azul fica ligado por um minuto e assim por diante.  
  
4)  
Na edição: o programador escolhe o endereço de cada uma das variáveis e do código
do programa na memória.  
Na compilação: ao traduzir o código-fonte, o compilador escolhe as posições das variáveis na memória. Para isso, todos os códigos-fontes necessários ao programa
devem ser conhecidos no momento da compilação, para evitar conflitos de
endereços entre variáveis em diferentes arquivos ou bibliotecas.  
Na ligação: na fase de compilação, o compilador traduz o código fonte em código
binário, mas não define os endereços das variáveis e funções, gerando como
saída um arquivo objeto (object file) que contém o código binário e uma tabela
de símbolos descrevendo as variáveis e funções usadas, seus tipos, onde estão
definidas e onde são usadas. A seguir, o ligador (linker) pega os arquivos objetos
com suas tabelas de símbolos, define os endereços de memória dos símbolos e
gera o programa executável.  
Na carga: também é possível definir os endereços de variáveis e de funções durante a
carga do código em memória para o lançamento de um novo processo. Nesse
caso, um carregador (loader) é responsável por carregar o código do processo
na memória e definir os endereços de memória que devem ser utilizados.  
Na execução: os endereços emitidos pelo processador durante a execução do processo
são analisados e convertidos nos endereços efetivos a serem acessados na
memória real.  
5)  
O espaço de memória de um processo é dividido em 6 partes:  
TEXT  -> Onde fica o código do programa  
DATA  -> Onde ficam as variáveis inicializadas  
BSS   -> Onde ficam as variáveis não inicializadas  
HEAP  -> Onde fica a memória que pode ser alocada dinamicamente a pedido de funções específicas  
STACK -> Onde fica a memória usada por funções e afins.  
  
6)  
Endereço físico é o endereço real na memória ram, geralmente expressado por um número inteiro em base hexadecimal,
já o endereço lógico é o que o processo utiliza para referenciar um endereço físico, permitindo um melhor uso da memória
separando-a em seções ou partições.  
  
9)  
a b) é a correta (Se usarmos Worst-fit, o tamanho final do buraco B4 será de 15 Mbytes) pois os duas primeiras
alocações irão para o buraco B4 e a última irá para B6 fazendo o B4 ficar com 15MB e o B6 com 18MB  
  
10)  
É quando um processo busca uma página na memória RAM e ela já foi movida para o disco rígido, ocorre um erro
e para tratar esse erro o sistema deve recuperar a página e carregá-la na memória novamente, e depois avisar
que a página já está disponível.  

