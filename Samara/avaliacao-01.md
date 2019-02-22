Respostas do Capítulo 1

1 -  Abstração e gerência

2 – Porque ele provê interfaces de acesso aos dispositivos simplificando a construção de programas, torna os aplicativos independentes do hardware e define interface de acesso homogêneas para dispositivos com tecnologias distintas.

3 – Cada computador normalmente possui menos processadores que o número de tarefas em execução por isso o sistema operacional distribui o uso deles entre os aplicativos presentes no sistema executando em velocidade adequada. Os desafios são fazer essa gerência de forma que nenhuma aplicação seja prejudicada.

4 – O que o caracteriza é o comportamento temporal previsível, ou seja, seu tempo de resposta deve ser conhecido no melhor e no pior caso de forma a minimizar esperas e latências imprevisíveis. As duas classificações existentes são: o soft-real-time systems nos quais a perda de prazos implica na degradação do serviço prestado e o hard-real-time systems onde a perda de prazos pelo sistema pode perturbar o objeto controlado, com graves consequências humanas, econômicas e ambientais.

5 – O núcleo gerencia os recursos do hardware usados pelas aplicações, implementando também as principais abstrações utilizadas pelos programas aplicativos.

6 – Não. Porque os utilitários e aplicativos devem ter acesso restrito ao hardware para não interferir nas configurações e na gerência pois isso acabaria desestabilizando o sistema inteiro.

8 – Uma exceção é gerada quando uma aplicação tente executar uma instrução proibida ou acessar uma área de memória inacessível. A interrupção é quando um controlador periférico tem uma informação importante para fornecer ao processador. Nela os circuitos do processador suspendem seu fluxo de execução e chamam a rotina interrupt handler que é responsável por executar as ações necessárias para atender o dispositivo que a gerou. 
