### Exercicios do capitulo 3 - Comunicação entre tarefas 


2. Explique como processos que comunicam por troca de mensagens se comportam em relação à capacidade do canal de comunicação, considerando as semânticas de chamada síncrona e assíncrona.

 - Capacidade nula (n = 0) : Caso a comunicação seja síncrona, o emissor permanece bloqueado até que o destinatário receba os
 dados, e vice-versa. Essa situação específica (comunicação síncrona com canais de capacidade nula) implica em uma forte 
 sincronização entre as partes,  Por outro lado, a comunicação assíncrona torna-se inviável usando canais de capacidade  nula.

 - Capacidade finita (0 < n < ∞) : neste caso, uma quantidade finita (n) de dados pode ser enviada pelo emissor sem que o   
receptor os consuma. Todavia, ao tentar enviar dados em um canal já saturado em uma comunicação síncrona , o emissor poderá 
ficar bloqueado até surgir espaço no buffer e em uma comunicação  assíncrona lançará  um erro.



3. Em relação à sincronização na comunicação entre processos, podemos afirmar que: 

I. Na comunicação semi-bloqueante, o emissor espera indefinidamente pela possibilidade de enviar os dados. 

II. Na comunicação síncrona ou bloqueante, o receptor espera até receber a mensagem. 

III. Um mecanismo de comunicação semi-bloqueante com prazo t = ∞ equivale a um mecanismo bloqueante.

 IV. Na comunicação síncrona ou bloqueante, o emissor retorna uma mensagem de erro caso o receptor não esteja pronto 
 para receber a mensagem. 
 
V. A comunicação com semântica bloqueante usando canais sem buffer é chamada Rendez-Vous.
 As asserções corretas são: 

(a) I, III 

(x) II, III, V - correta

(c) I, II, IV 

(d) II, III 

(e) III, IV, V



4. Em relação à sincronização na comunicação entre processos, podemos afirmar que: 

I. Na comunicação semi-bloqueante, o emissor espera pelo envio dos dados, mas o receptor não.

 II. Se o canal de comunicação tiver capacidade nula, emissor e receptor devem usar mecanismos não-bloqueantes. 
 
III. A comunicação não-bloqueante em ambos os participantes só é viável usando canais de comunicação com buffer não-nulo.

 IV. Os pipes do UNIX são um bom exemplo de comunicação bloqueante. 
 
V. Um mecanismo de comunicação semi-bloqueante com prazo t = 0 equivale a um mecanismo bloqueante. 

As asserções corretas são: 

(a) I, II, IV 

(b) II, III 

(c) III, IV, V 

(x) I, IV  -    correta 

(e) III, IV




5. Dadas as seguintes características dos mecanismos de comunicação:

 I. A comunicação indireta (por canais) é mais adequada para sistemas distribuídos. 
 
II. Canais com capacidade finita somente são usados na definição de algoritmos, não sendo implementáveis na prática. 

III. Na comunicação direta, o emissor envia os dados diretamente a um canal de comunicação. 

IV. Na comunicação por fluxo, a ordem dos dados enviados pelo emissor é mantida do lado receptor. 

V. Na comunicação por troca de mensagens, o núcleo transfere pacotes de dados do processo emissor para o processo receptor. 

As asserções erradas são: 

(a) II, III 

(b) I, III

(x) II, IV - correta 

(d) III, V

(e) I, IV 





6. Dadas as seguintes características dos mecanismos de comunicação:

 I. Na comunicação por troca de mensagens, o processo emissor copia o conteúdo da mensagem no buffer do processo receptor.
 
II. O buffer do canal de comunicação entre dois processos distintos é geralmente mantido pelo núcleo do sistema operacional. 

III. Se a capacidade do buffer do canal de comunicação for considerada infinita, somente o receptor pode se bloquear.

IV. As filas de mensagens POSIX são um exemplo de canal de comunicação com capacidade nula. 
 
V. O protocolo de rede TCP é um exemplo de comunicação por fluxo de dados. 

As asserções erradas são: 

(X) I, III  - Correta

(b) II, III 

(c) I, IV 

(d) II, IV 

(e) II, V
 


7. Dadas as seguintes características dos mecanismos de comunicação:

I. A memória compartilhada provê mecanismos de sincronização para facilitar a comunicação entre os processos.

II. A troca de dados através de memória compartilhada é mais adequada para a comunicação em rede. 

III. Processos que se comunicam por memória compartilhada podem acessar a mesma área da RAM. 

IV. Os pipes Unix são um bom exemplo de comunicação M:N. V. A comunicação através de memória compartilhada é 
particularmente indicada para compartilhar grandes volumes de dados entre dois ou mais processos.

As asserções corretas são:

 (X) I, III, V  -  correta 
 
(b) I, II 

(c) III, IV

(d) II, IV

(e) III, V
 


8. Dadas as seguintes características dos mecanismos de comunicação: 

I. Em um mecanismo de mailbox, cada mensagem enviada é replicada a todos os receptores. 

II. Em um canal de eventos, as mensagens enviadas são distribuídas alternadamente entre os receptores. 

III. As filas de mensagens POSIX são um bom exemplo de canal de eventos. IV. Nas filas de mensagens POSIX, 
as mensagens transitam através de arquivos em disco criados especialmente para essa finalidade. 

V. Em UNIX, um pipe é um canal de comunicação unidirecional que liga a saída padrão de um processo à entrada padrão de outro.

As asserções corretas são: 

(a) I, III 

(b) II 

(c) III, IV 

(X) V  - correta 

(e) nenhuma delas 


