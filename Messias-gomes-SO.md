<h1>Respostas do capitulo 1</h1>
<h3> </h3>
<h3><b>1. Quais os dois principais objetivos dos sistemas operacionais?</b><br></h3>
Os objetivos básicos de um sistema operacional podem ser sintetizados em duas
palavras-chave: “abstração” e “gerência”.<br>

<h3><b>2. Por que a abstração de recursos é importante para os desenvolvedores de aplicações?</b><br></h3>
<b>Ela tem utilidade para os desenvolvedores do próprio sistema operacional?</b><br></h3>
<p> Tornar os aplicativos independentes do hardware. Ao definir uma interface abstrata deacesso a um dispositivo de hardware, o sistema operacional desacopla o hardwaredos aplicativos e permite que ambos evoluam de forma mais autônoma  </p>

<h3><b>3. A gerência de atividades permite compartilhar o processador, executando mais de
uma aplicação ao mesmo tempo. Identifique as principais vantagens trazidas por essa funcionalidade e os desafios a resolver para implementá-la.</b></h3><br>

<p> Cada computador normalmente possui menos processadores que o número detarefas em execução.  Por isso, o uso desses processadores deve ser distribuídoentre os aplicativos presentes no sistema,  de forma que cada um deles possaexecutar na velocidade adequada para cumprir suas funções sem prejudicar osdemais. O mesmo ocorre com a memória RAM, que deve ser distribuída de formajusta entre as aplicações. </p>



<h3><b>4. O que caracteriza um sistema operacional de tempo real? Quais as duas classificações
de sistemas operacionais de tempo real e suas diferenças?</b></h3><br>

<p>Um sistema operacional de tempo real não precisa ser necessariamente ultrarrápido; sua característica essencial é ter um comportamento temporal previsível (ou seja, seu tempo de resposta deve serconhecido no melhor e pior caso de operação).<br> A estrutura interna de um sistemaoperacional de tempo real deve ser construída de forma a minimizar esperas elatências imprevisíveis, como tempos de acesso a disco e sincronizações excessivas.<br>   Existem duas classificações de sistemas de tempo real:soft real-time systems, nosquais a perda de prazos implica na degradação do serviço prestado. Um exemplo seria o suporte à gravação de CDs ou à reprodução de músicas. Caso o sistema seatrase, pode ocorrer a perda da mídia em gravação ou falhas na música que estásendo tocada.  Por outro lado, noshard real-time systemsa perda de prazos pelosistema pode perturbar o objeto controlado, com graves consequências humanas,econômicas ou ambientais. Exemplos desse tipo de sistema seriam o controle defuncionamento de uma turbina de avião a jato ou de uma caldeira industrial. <br>Exemplos de sistemas de tempo real incluem o QNX, RT-Linux e VxWorks. Muitos sistemas embarcados têm características de tempo real, e vice-versa.                                                                                          </P>

<h3><b>5. O que diferencia o núcleo do restante do sistema operacional?</b></h3><br>
  
  <p>    É o coração do sistema operacional, responsável pela gerência dos recursos do hardware usados pelas aplicações. <br>
  Ele também implementa as principais abstrações utilizadas pelos programas aplicativos.</p>
  
  
  
<h3><b>6. Seria possível construir um sistema operacional seguro usando um processador
que não tenha níveis de privilégio? Por quê?</b></h3><br>

<p>Não. Núcleo,  drivers,  utilitários e aplicações são constituídos basicamente de código de máquina. Todavia, devem ser diferenciados em sua capacidade de interagir com o hardware: enquanto o núcleo e os drivers devem ter pleno acesso ao hardware, para poder configurá-lo e gerenciá-lo, os utilitários e os aplicativos devem ter acesso mais restrito a ele, para não interferir nas configurações e na gerência, o que acabaria desestabilizando o sistema inteiro. Além disso, aplicações com acesso pleno ao hardware tornariam inúteis os mecanismos de segurança e controle de acesso aos recursos (tais como arquivos, diretórios e áreas de memória).</p>

  
<h3><b>7. O processador Pentium possui dois bits para definir o nível de privilégio, resultando
em 4 níveis distintos. A maioria dos sistemas operacionais para esse processador usa somente os níveis extremos (0 e 3, ou 002 e 112).
  Haveria alguma utilidade para os níveis intermediários?</b></h3><br>
  
  




<h3><b>8. Quais as diferenças entre interrupções, exceções e traps?</b><br>
  
  
  
  
  
<h3><b>9. Quais as implicações de mascarar interrupções? O que pode ocorrer se o processador
ignorar interrupções por muito tempo? O que poderia ser feito para evitar o
mascaramento de interrupções?</b></h3><br>





  
<h3><b>10. O comando em linguagem C fopen é uma chamada de sistema ou uma função de
biblioteca? Por quê?</b></h3><br>





<h3><b>11. Monte uma tabela com os benefícios e deficiências mais significativos das principais
arquiteturas de sistemas operacionais.</b></h3><br>





<h3><b>12. Relacione as afirmações aos respectivos tipos de sistemas operacionais: distribuído
(D), multi-usuário (M), desktop (K), servidor (S), embarcado (E) ou de tempo-real
(T):
