# Exercicios - SO: 

## 1ª: 
Abstração e gerência. 

## 2ª:
Por facilitar a maneira que é acessado as informações do hardware, onde 
por meio da abstração, são criados métodos "homogêneos" (iguais) para reduzir a diversidade
tecnologica que dificulta esse acesso aos diversos dispositivos. Tem, pois facilita 
e reduz esse meio que existe entre o hardware e o software do sistema. 

## 3ª: 

* Evitar conflitos e aumentar a velocidade na execução de diversas funções no processador.
* Distribuir igualmente a memória para que as aplicações tenham um rendimento melhor.
* Evitar mistura de conteúdos nos documentos em uma impressora. 
* Impedir DoS (Denial of Service), ou seja, a monopolização de apenas um usuário
no uso dos recursos do sistema. 

Desafios - Definir politicias do uso dos recursos de hardware pelos aplicativos para resolver disputas e conflitos. 

## 4ª: 

Ter um comportamento temporal previsível.  As duas classificações são: soft real-time systems e
hard real-time systems, e o que diferecia os dois é a consequência que ocorre quando há um atraso 
nessa resposta por parte do sistema, enquanto em um, apenas arquivos ou serviços são perdidos (degradados),
no outro existe consequências mais graves, afetando o objeto que está sendo controlado, no caso o Ambiente ou Usuário.

## 5ª: 
O núcleo é o responsável por fazer a gerência/abstração de toda a parte de hardware,
enquanto os demais componentes são mais voltados para a parte de "software" (funcionalidades)
do sistema.

## 6ª: 

Não. Pois essa "separação" é necessário para manter a integridade dos dados e 
para que não ocorra interferência na execução de funções designadas a cada parte do SO, como por exemplo, 
a gerência do sistema, e o acesso direto ao hardware. 

## 7ª: 

Sim. Controle.

## 8ª: 

Interrupções são notificações enviadas ao processador pelo controlador de periférico 
quando o mesmo quer estabelecer uma comunicação.  Já a exceção são erros gerados pelo própio 
processador que quando ocorridos, também desviam o fluxo da execução disparando métodos para tratamento 
desses problemas no processador. E por fim, trap são interrupções intencionais realizadas pelo processador independentes
de eventos internos ou externos. 

## 9ª: 
- Distinguir interrupções gerados por dispositivos distintos, e definir o tipo de tratamento para cada uma delas.
 - Torna eficiente a interação do processador com os dispositivos periféricos.
- Prejudicar o desempenho do Sistema.

## 10ª: 
Função de biblioteca. Pois é uma função de acesso a arquivos definida em uma Biblioteca.

## 11ª: 

Arquitetura | Benefícios | Deficiências

Monolitico | Desempenho|Qualquer problema pode se alastrar para outros componentes, caso algum erro ocorra.
			Manutenção e evolução do núcleo é mais complexa.
Camadas | Essa divisão em camadas provê uma abstração e gerência melhor em cada camada.|Ruim desempenho, pois demora mais para um pedido de alguma aplicação ser levado para uma outra camada, e também o seu acesso.

Micronucleos | Robustez e flexibilidade | Prejudicar o desempenho por conta do custo alto na troca de mensagens entre os componentes.
Maquinas virtuais. | Suporte a diversas aplicações escritas em linguagens diferentes. | Custo adicional de execução dos processos na máquina virtual em comparação com a máquina real.

## 12ª: 

- 1 - T
- 2 - S.
- 3 - E
- 4 - D
- 5 - M
- 6 - E
- 7 - k.
- 8 - S
- 9 - K
- 10 - E

## 13ª: 

- a - Não poderia.
- b - Poderia.
- c - Não poderia.
- d - Poderia.
- e - Não poderia. 
- f - Não poderia.

Por que são instruções que são realizadas diretamente pelo processador e com um acesso mais "privilegiado"
ao hardware, que só é permitido ao núcleo do SO. Caso fosse possível, poderia ocorrer "conflitos" nesse acesso/permissão
de baixo nível acabando com o desempenho do SO. 

## 14ª: 

- a - Não.
- b - Sim.
- c - Não.
- d - Sim
- e - Sim.

Para ter acesso aos componentes mais baixos, é necessário que o sistema operacional para realizar as operações.

## 15ª: 

- 1 - 5
- 2 - 7
- 3 - 2
- 4 - 3
- 5 - 
- 6 - 4
- 7 - 
- 8 - 1 
- 9 - 6
- 10 - 8

## 16ª: 

- I - V 
- II - V
- III - F, isso é caracteristica do so distribuido.
- IV - F, isso é caracteristica do so desktop.
- V - V

(c)

## 17ª: 

- I - F, ocorre o oposto. 
- II - V
- III - F, isso é caracteristica do monolitico.
- IV - F, pois como os componentes estão interligados e tem acesso aos demais, 
caso algum desses componentes tenha um erro, esse problema pode gerar um colapso 
no sistema, e a manutenção é mais complexa, pois dependencias e pontos de interação 
podem não ser evidentes, e caso uma estrutura seja alterada, pode causar um impacto
nos demais componentes que também tenham acesso a aquela estrutura. 
- V - V 

e. 

## 18ª: 
Para o carregamento de bibliotecas compartilhadas, mapeamento da memória e – no final do rastreio – a emissão das informações sobre a data para a saída padrão.

## 19ª: 
O utilitário date chama uma biblioteca com o fim de comunicar com o núcleo. Esta biblioteca manipula os detalhes de baixo nível
relacionados com a passagem de informação para o núcleo e com a chamada da rotina privilegiada propriamente dita, nomeadamente a
conversão de convenções de chamadas. As chamadas de sistema são oferecidas para as aplicações em modo usuário através da system library que prepara os parâmetros, invoca a interrupção de software e retorna à aplicação os resultados obtidos.
