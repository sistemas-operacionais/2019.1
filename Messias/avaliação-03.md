<h1>Respostas cap 03</h1>
<h3>1. Quais são as vantagens e desvantagens das abordagens a seguir, sob as óticas
do sistema operacional e do programador de aplicativos?</h3>
<p>(a) Comunicação bloqueante ou não-bloqueante: Como o envio e a recepção bloqueiam
as tarefas enviadas, isso impede que haja interferência na hora da troca de mensagens de
dados, uma vantagem disso é o tempo de espera para o emissor e o receptor. </p>
<p>(b) Canais com buffering ou sem buffering: Se o canal possuir um buffering, o emissor
pode enviar vários dados para o receptor ao mesmo tempo sem se preocupar, pois o receptor
vai reenviando um a um através do buffer, a desvantagem é que se a capacidade do buffering
for finita e o emissor acabar atingindo, ele terá que esperar o receptor receber alguns dados
para liberar espaço.
Sem buffering: ​ a comunicação é feita de forma direta, sem cópias intermediárias, o que torna
o processo mais rápido, em contrapartida o emissor e o receptor permanecem bloqueados até
finalizar o envio.</p>
<p>(c) Comunicação por mensagens ou por uxo: ​ A abordagem por mensagem tem como
vantagem o envio de dados como pacotes, então esse dado é enviado e recebido de forma
completa. A desvantagem é que caso perca algum dado no meio do caminho não é possível
receber meia mensagem.
Na abordagem por fluxo é criado um canal onde o emissor vai enviar dados que serão lidos
de forma sequencial, respeitando a ordem de envio. A desvantagem é que não será possível
priorizar algum dado por para ser lido primeiro.</p>
<p>(d) Mensagens de tamanho xo ou variável: ​ No fixo, tem como vantagem o conhecimento
por parte do receptor de saber que ele precisa reservar espaço de memória suficiente para o
recebimento dos dados, em contrapartida, aquele espaço de memória reservado pode ou não
ser utilizado, e o espaço não utilizado acaba ficando preso sem que outros processos possam
utilizá-los.
Na mensagem variável, faz com que o receptor esteja sujeito ao recebimento de mensagens
de qualquer tamanho, em compensação o espaço de memória fica até o recebimento das
mensagens.</p>
<p>(e) Comunicação 1:1 ou M:N: ​ Na comunicação 1:1 há uma conexão direta entre emissor e
receptor, através de um canal fazendo com que o envio das mensagens seja de forma rápida.
Na desvantagem o emissor só pode enviar dados para um receptor de cada vez.
Na M:N, há uma conexão entre vários emissores e receptores, fazendo com que o envio das
mensagens se torne um pouco lento, mas em compensação existe uma comunicação
simultânea entre vários emissores e receptores, fazendo com que não seja preciso criar várias
comunicações.</p>


<h3> 2. Explique como processos que comunicam por troca de mensagens se comportam
em relação à capacidade do canal de comunicação, considerando as semânticas
de chamada síncrona e assíncrona.   </h3>
<p>Síncrona: Quando as operações de envio e recepção de dados bloqueiam (suspendem) as
tarefas envolvidas até a conclusão da comunicação. O emissor será bloqueado até que a
informação seja recebida pelo receptor, e vice-versa. Esta modalidade de interação também é
conhecida como comunicação bloqueante.</p>
<p>Assíncrona: Um sistema com comunicação assíncrona, as primitivas de envio e recepção não
são bloqueantes. Caso a comunicação não seja possível no momento em que cada operação é
invocada, esta retorna imediatamente com uma indicação de erro. Deve-se observar que, caso
o emissor e o receptor operem ambos de forma assíncrona, torna-se necessário criar um canalou buffer para armazenar os dados da comunicação entre eles. Sem esse canal, a comunicação
se tornará inviável, pois raramente ambos estarão prontos para comunicar ao mesmo tempo.
Esta forma de comunicação, também conhecida como comunicação não-bloqueante.</p>

<h3>3. Sobre as afirmações a seguir, relativas mecanismos de comunicação, indique
quais são incorretas, justificando sua resposta:</h3>
<p>a. Na comunicação semi-bloqueante, o emissor espera indenidamente pela
possibilidade de enviar os dados.</p>
<p>b. Na comunicação síncrona ou bloqueante, o receptor espera até receber a mensagem.</p>
<p>c. Um mecanismo de comunicação semi-bloqueante com prazo t =∞ equivale a um
mecanismo bloqueante.</p>
<p>d. Na comunicação síncrona ou bloqueante, o emissor retorna uma mensagem de erro
caso o receptor não esteja pronto para receber a mensagem.</p>
<p>e. A comunicação com semântica bloqueante usando canais sem buffer é chamada
Rendez-Vous.</p>
<p>As asserções corretas são:</p>
<p>(a) I, III</p>
<p>(b) II, III, V</p>
<p>(c) I, II, IV</p>
<p>(d) II, III <= Correta</p>
<p>(e) III, IV, V</p>
<p>Resposta:
I está errada porque na comunicação semi-bloqueante, o emissor espera durante um prazo
pré-definido pela possibilidade de enviar os dados.
IV está errada porque é na comunicação assíncrona ou não-bloqueante, o emissor retorna uma
mensagem de erro caso o receptor não esteja pronto para receber a mensagem.
V está errada porque a comunicação com semântica bloqueante usando canais com buffer é
chamada Rendez-Vous.</p>


<h3>4. Sobre as afirmações a seguir, relativas à sincronização na comunicação entre
processos, indique quais são incorretas, justificando sua resposta:    </h3>
<p>I. Na comunicação semi-bloqueante, o emissor espera pelo envio dos dados, mas o
receptor não.</p>
<p>II. Se o canal de comunicação tiver capacidade nula, emissor e receptor devem usar
mecanismos não-bloqueantes.</p>
<p>III. A comunicação não-bloqueante em ambos os participantes só é viável usando canais
de comunicação com buffer não-nulo.</p>
<p>IV. Os pipes do UNIX são um bom exemplo de comunicação bloqueante.</p>
<p>V.Um mecanismo de comunicação semi-bloqueante com prazo t = 0 equivale a um
mecanismo bloqueante.</p>
<p>As asserções corretas são:</p>
<p>(a) I, II, IV</p>
<p>(b) II, III</p>
<p>(c) III, IV, V <= Correta</p>
<p>(d) I, IV</p>
<p>(e) III, IV</p>
<p>Resposta:
I está errada porque na comunicação semi-bloqueante, o emissor e receptor esperam pelo
envio dos dados, mas raramente ambos estarão prontos para comunicar ao mesmo, torna-se
necessário criar um buffer.
II está errada porque se o canal de comunicação tiver capacidade nula, emissor e receptor
devem usar mecanismos bloqueantes.</p>


<h3> 5 -   </h3>
<p>1. A comunicação indireta(por canais) é mais adequada para sistemasdistribuídos.</p>
<p> 2. Canais com capacidade nita somente são usados na denição de algoritmos, não
sendo implementáveis na prática.</p>
<p>3. Na comunicação direta, o emissor envia os dados diretamente a um canal de
comunicação.</p>
<p>4. Na comunicação por uxo, a ordem dos dados enviados pelo emissor é mantida
do lado receptor.</p>
<p>5. Na comunicação por troca de mensagens, o núcleo transfere pacotes de dados do
processo emissor para o processo receptor.</p>
<p>As asserções erradas são:</p>
<p>(c) II, IV <= Correta</p>
<p>Resposta:
II está errada porque a maioria dos sistemas reais opera com canais de capacidade nita.
IV está errada porque na comunicação por informação enviada pode ser como uma sequência
de mensagens independentes, cada uma com seu próprio conteúdo, ou como um uxo
sequencial e contínuo de dados, imitando o comportamento de um arquivo com acesso
sequencial.</p>

<h3>  6-  </h3>
<p><I. Na comunicação por troca de mensagens, o processo emissor copia o conteúdo da
mensagem no buffer do processo receptor./p>
<p>II. O buffer do canal de comunicação entre dois processos distintos é geralmente
mantido pelo núcleo do sistema operacional.</p>
<p><III. Se a capacidade do buffer do canal de comunicação for considerada innita,
somente o receptor pode se bloquear./p>
<p>IV. As las de mensagens POSIX são um exemplo de canal de comunicação com
capacidade nula.</p>
<p>V. O protocolo de rede TCP é um exemplo de comunicação por uxo de dados.</p>
<p>As asserções erradas são:</p>
<p>(a) I, III <= Correta</p>
<p>I está errada porque na comunicação por troca de mensagens, a implementação deste canal se
baseia nas primitivas de mensagem, como receptor envia a mensagem e o receptor.
III está está errada porque se a capacidade do buffer do canal de comunicação for considerada
innita, o emissor sempre pode enviar dados, que serão armazenados no buffer do canal
enquanto o receptor não os consumir.</p>
<h3>7 - </h3>
<p>I. A memória compartilhada provê mecanismos de sincronização para facilitar a
comunicação entre os processos. </p>
<p>II. A troca de dados através de memória compartilhada é mais adequada para a
comunicação em rede. </p>
<p>III. Processos que se comunicam por memória compartilhada podem acessar a mesma
área da RAM. </p>
<p> IV. Os pipes Unix são um bom exemplo de comunicação M:N.</p>
<p>V. A comunicação através de memória compartilhada é particularmente indicada para
compartilhar grandes volumes de dados entre dois ou mais processos. </p>
<p> As asserções corretas são:</p>
<p>(b) I, II <= Correta </p>
<p>Resposta;
III está errada porque os processos que se comunicam por memória compartilhada podem
acessar a mesma área do núcleo.
IV está errada porque os pipes Unix são um bom exemplo de comunicação 1:1
V A comunicação através de memória compartilhada é ineficiente caso a comunicação seja
muito volumosa e frequente, ou envolvam muitos processos. </p>


<h3> 8 -   </h3>
<p>I. Em um mecanismo de mailbox, cada mensagem enviada é replicada a todos os
receptores.</p>
<p>II. Em um canal de eventos, as mensagens enviadas são distribuídas alternadamente
entre os receptores.</p>
<p>III. As las de mensagens POSIX são um bom exemplo de canal de eventos.</p>
<p>IV. Nas las de mensagens POSIX, as mensagens transitam através de arquivos em
disco criados especialmente para essa nalidade.</p>
<p>V. Em UNIX, um pipe é um canal de comunicação unidirecional que liga a saída padrão
de um processo à entrada padrão de outro.</p>
<p>As asserções corretas são:</p>
<p>(d) V <= Correta</p>
<p>Resposta:
I está errada porque em um mecanismo mailbox, cada mensagem é recebida por apenas um
receptor.
II está errada porque em um canal de eventos, cada mensagem é recebida por todos os
receptores.
III está errada porque as las de mensagens POSIX são um bom exemplo de canal de
mailbox.
IV. Nas las de mensagens POSIX, as mensagens transitam através de arquivos UNIX
System V criados especialmente para manipulação de filas de mensagens.</p>
<p></p>
<p></p>
<p></p>
