>### Cap. 1 - Conceitos Básicos

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
9. O processador varre todos os dispositivos do sistema para fazer a verificação se há eventos a serem
tratados, deste modo, a quantidade de tempo envolvendo a solução é maior que o esperado.
10. **Fopen** pertence a biblioteca mais usual da linguagem C. Pois, em seu escopo de cabeçalho ela está definida.
11.

|    Arquitetura    |                           Benefícios                          |                              Deficiências                             |
|:-----------------:|:-------------------------------------------------------------:|:---------------------------------------------------------------------:|
|   S. Monolíticos  |                           Desempenho                          | Não é muito robusto; Velocidade e Desenvolvimento não tão favoráveis  |
| Máquinas Virtuais | Reduz gastos com novas aplicações; Se adapta às já existentes |       Custo adicional é bem menos relevante que em máquina real       |
|     S. Camadas    |               Domínio das Redes de Computadores               |                Ocorre uma demora no pedido de aplicação               |
|  S. Micronúcleos  |              Flexibilidade; Compactação; Robustos             |              O custo nas trocas de mensagens é muito alto             |
12. _[T] [S] [E] [K] [D] [E] [S] [K] [S] [K] [E]_
13. Escrever um valor em uma posição de memória; Ajustar o valor do relógio do hardware; Mascarar uma ou mais interrupções. Pois, tais operações nas mãos de um usuário mal-intecionado ou até mesmo leigo poderia conduzir problemas na estrutura/funcionamento do sistema.
14. Enviar um pacote através da rede; Preencher uma área de memória do processo com zeros _(malloc em c)_ ;Remover um arquivo do disco. Pois, como o próprio capítulo fala:

> Os sistemas operacionais definem chamadas de sistema para todas as operaçes envolvendo o acesso a recursos de baixo nível (periféricos, arquivos, alocação de memória, etc.)
15. _[5][9][2][3][7][8][4][1][6][10]_
16. **R: C**

    _Erradas/Motivo_
    III -> Essa caracteristica corresponde aos sistemas distribuídos.


    IV -> A caracteristicas citadas corresponde aos sistemas desktop.

17. **R: E**

    _Erradas/Motivos_

    I -> Máquinas virtuais são feitas para suportar sistemas operacionais completos.

    III -> Essa característica corresponde aos sistemas monolíticos.

    IV -> Sistemas monolíticos tem manutenção muito complexa.

18. Carregar bibliotecas compartilhadas; Mapear memória; Emitir informações para saída padrão.
19. Sim, uma vez que o utilitário **date** implementa uma biblioteca com finalidade de se comunicar com o núcleo, esta é responsável por toda a manipulção dos detalhes de baixo nível - linguagem de máquina - relacionados com a troca de informação entre núcleo e rotina privilegiada, criando-se então o que conhecemos por _conversão de convençes de chamadas_. Tais, são oferecidas em aplicação no modo usuário através da _System Library_ que é responsável por preparar os parâmetros, instanciar a interrupção de software, retornando à aplicação os resultados ganho.
