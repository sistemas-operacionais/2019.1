## Respostas do Capítulo 13 - Impasses

1 - Quando um impasse é detectado o sistema deve proceder a resolução do mesmo, eliminando tarefas ou retroceder tarefas. 
No eliminar tarefas uma ou mais tarefas são eliminadas levando em conta o tempo de vida de cada uma, a quantidade de recursos 
de cada uma utiliza, o prejuízo aos usuários que dependem dela, entre outras.  
No retroceder tarefas uma ou mais tarefas tem sua execução parcialmente desfeita (rollback). Para retroceder é necessário salvar 
periodicamente seu estado. Além disso operações que envolve redes ou interações podem ser difíceis ou impossíveis de retroceder 
como por exemplo o envio de um pacote de rede.  
A detecção e resolução é pouco usada fora de situações específicas porque o custo é elevado e sempre implica em perder tarefas ou 
parte de resoluções já executadas.  

2 - Na figura da direita existe um impasse onde t1 necessita do recurso r2 porém t2 retem esse recurso. Ao mesmo tempo que t2
necessita do recurso r1 mas o t1 o detem. Na figura da esquerda existe um impasse aonde t1 necessita de r2 mas t2 esta utilizando-o
t2 necessita de r3 mas ele está sendo utilizado por t3 e t4 e t3 precisa de r1 porem t1 está utilizando-o.  

3 - Existe exclusão mútua porque as ruas verticais não podem ser utilizadas ao mesmo tempo que as ruas horizontais.
Existe posse e espera porque os carros que estão nas ruas verticais podem solicitar o acesso às ruas horizontais sem precisar
sair liberar as verticais e vice-versa.
Existe não-preempção porque os carros podem liberar as avenidas quando quiserem, não há nada que remova eles a força.
Existe espera circular porque os carros precisam que os outro carros liberem o recurso enquanto estes não podem libera-lo
até que os demais liberem os outro recursos.  
Uma regra simples que pode ser utilizada é só podem executar suas tarefas ao mesmo tempo os carros das ruas verticais
por um determinado tempo, devendo após esse tempo esperar enquanto os carros das ruas horizontais executam suas tarefas
também por um determinado tempo liberando logo em seguida. E assim o fluxo segue.

## Respostas do Capítulo 14 - Conceitos Básicos

## Respostas do Capítulo 15 - Hardware de Memória

## Respostas do Capítulo 16 - Alocação de Memória

## Respostas do Capítulo 17 - Paginação em Disco
