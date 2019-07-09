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

3 - Existe **exclusão mútua** porque as ruas verticais não podem ser utilizadas ao mesmo tempo que as ruas horizontais.
Existe **posse e espera** porque os carros que estão nas ruas verticais podem solicitar o acesso às ruas horizontais sem precisar
liberar as verticais e vice-versa.
Existe **não-preempção** porque os carros podem liberar as avenidas quando quiserem, não há nada que remova eles a força.
Existe **espera circular** porque os carros precisam que os outro carros liberem o recurso enquanto estes não podem libera-lo
até que os demais liberem os outro recursos.  
Uma regra simples que pode ser utilizada é só podem executar suas tarefas ao mesmo tempo os carros das ruas verticais
por um determinado tempo, devendo após esse tempo esperar enquanto os carros das ruas horizontais executam suas tarefas
também por um determinado tempo liberando logo em seguida. E assim o fluxo segue.  

## Respostas do Capítulo 14 - Conceitos Básicos

4 - **Na codificação** o programador escolhe ele prórpio o endereço de cada variável na memória. É usado normalmente em programas feitos
com Assembly. **Na compilação** é o compilador que escolhe a posição das variáveis por isso todos os códigos-fontes devem sem conhecidos
pelo compilador no momento da compilação para evitar conflitos. **Na ligação** o compilador traduz o código fonte em binário mas não define os endereções das variáveis, gerando como saída um arquivo objeto que contém o código binário e uma tabela descrevendo as variáveis, funções, seus tipos, onde estão definidas e onde são usadas. A seguir o ligador pega os arquivos objetos e define os endereções de memória dos símbolos e gera o .exe. **Na carga** também é possível definir os endereços como na carga. Nesse caso um carregador é responsável por carregar o código do processo na memória e definir os endereções de memória que devem ser utilizados. O carregador pode ser parte do núcleo do sistema operacional ou uma biblioteca ligada ao executável, ou ambos.  

5 - As principais seções de memória de um processo são: TEXT, DATA, BSS, HEAP e STACK.  

## Respostas do Capítulo 15 - Hardware de Memória

6 - **Endereços lógicos** são os endereços de memória usados pelos processos e pelo SO e portanto são utilizados durante a execução. Eles são definidos de acordo com o espaço de endereçamento do processador. Os **endereços físicos** são os endereços dos bytes de memória física do computador. Eles são definidos pela quantidade de memória disponível na máquina.  

7 - **0:45**: 0:89  
**1:100**: 1:300  
**2:90**: 2:90  
**3:1.900**: endereço lógico inválido
**4:200**: 4:1.400

## Respostas do Capítulo 16 - Alocação de Memória

9 - Alternativa B está correta porque primeiro a área de 5MB irá para a maior área possível que é a B4 que possue 30MB, deixando um espaço de 25MB. Quando for alocar a área de 10MB a maior área disponível continua sendo a B4, após a alocação a área B4 fica com **15MB restantes**. Ao alocar a área de 2MB a maior área disponível é a agora a B6 com 20MB livres.

## Respostas do Capítulo 17 - Paginação em Disco

10 - Falta de página é quando uma página, um conjunto de páginas ou um segmento de memória são movidas para o disco. Quando um processo tenta acessar uma dessas páginas a MMU gera uma interrupção de falta de página e o núcleo do SO recarrega a página faltante na memória.
