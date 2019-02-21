
>### Cap. 1
#### Conceitos Básicos - Respostas

1. Abstração de recursos e Gerência de recursos.
2. A abstração de recursos é importante, pois, permite que o desenvolvedor evolua de uma maneira
autônoma, consequentemente, ele não irá precisar se preocupar diretamente em como o hardware se comportará,
tendo em vista que a **abstração de recursos** já se preocupou por ele.
3. As principais vantagens são: Os usuários podem fazer várias atividades ao mesmo tempo; O uso dos processadores são distribuídos entre 
os aplicativos em execução no sistema, fazendo com que cada um possa executar de maneira a atender sua demanda, sem prejudicar aos demais; A memória _RAM_ também é distribuída de forma justa entre as aplicações. Ademais, existem desafios para implementação da **Gerência de recursos** quando dois ou mais aplicativos precisam dos mesmos recursos para poder executar, isso gera um problema que pode ser evitado a partir de políticas para gerênciá-los, deste modo, o S.O (sistema operacional) visa abstrair o acesso e gerenciar os recursos provendo uma minimização dos conflitos.
4. Um sistema operacional de tempo real é caracterizo pelo seu comportamento temporal previsível. _Soft real-time e Hard real-time systems_ são suas duas classificações. As diferenças entre elas se dá que no _Soft real-time_  a perda de prazos implica na degradação do serviço prestado, já no _Hard real-time_  a perda de prazos pelo sistema pode perturbar o objeto controlado, com graves consequências humanas, econômicas ou ambientais.
5. O núcleo é o coração de todo S.O, responsável pela gerência dos recursos do hardware usados pelas aplicações. Ele implementa as principais **abstrações** pelo usuário que utiliza a camada de interface.
6. Não, uma vez que os níveis de previlégio já são implementados para impedir que as aplicações acessem diretamente o hardware, deste modo evitando uma série de problemas de segurança e acima de tudo uma extrema lentidão.
7. Sim, uma vez que entre os níveis existissem uma divisão de processamento.
8.  Interrupções: Eventos causados por dispositivos externos ao processador  
    Exceções: São eventos gerados pelo própio processador  
    Traps: São eventos causados por software aplicativos  
9. 
10. 
