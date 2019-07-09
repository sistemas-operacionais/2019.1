1-
a) Quando as operações de envio e recepção de dados suspendem as tarefas envolvidas até a conclusão da comunicação, o emissor será bloqueado até que a informação seja recebida pelo receptor, e vice-versa. já na não bloqueante, caso a comunicação não seja possível no momento em que cada operação é invocada, esta retorna imediatamente com uma indicação de erro. Deve-se observar que, caso o emissor e o receptor operem ambos de forma assíncrona, torna-se necessário criar um canal ou buffer para armazenar os dados da comunicação entre eles. Sem esse canal, a comunicação se tornará inviável, pois raramente ambos estarão prontos para comunicar ao mesmo tempo.

b) O comportamento síncrono ou assíncrono de um canal de comunicação pode ser afetado pela presença de buffers que permitam armazenar temporariamente os dados em trânsito, ou seja, as informações enviadas pelo emissor e que ainda não foram recebidas pelo receptor.

c) A informação enviada pelo emissor ao receptor pode ser vista basicamente de duas formas: como uma sequência de mensagens independentes, cada uma com seu próprio conteúdo cada mensagem consiste de um pacote de dados que pode ser tipado ou não, esse pacote é recebido ou descartado pelo receptor em sua íntegra, não existe a possibilidade de receber meia mensagem, ou como um fluxo sequencial e contínuo de dados, imitando o comportamento de um arquivo com acesso sequencial, o canal de comunicação é visto como o equivalente a um arquivo: o emissor escreve dados nesse canal, que serão lidos pelo receptor respeitando a ordem de envio dos dados, não há separação lógica entre os dados enviados em operações separadas eles podem ser lidos byte a byte ou em grandes blocos a cada operação de recepção, a critério do
receptor.

d) Capacidade nula, a comunicação é feita por transferência direta entre emissor e receptor. Capacidade infinita, o emissor sempre pode enviar dados, que serão armazenados no buffer do canal enquanto o receptor não os consumir. Capacidade finita, uma quantidade finita de dados pode ser enviada pelo emissor sem que o receptor os consuma.

e) 1:1 : um emissor e um receptor interagem através do canal de comunicação. M:N : um ou mais emissores enviam mensagens para um ou mais receptores.

2- Capacidade nula, a comunicação é feita por transferência direta entre emissor e receptor. Capacidade infinita, o emissor sempre pode enviar dados, que serão armazenados no buffer do canal enquanto o receptor não os consumir. Capacidade finita, uma quantidade finita de dados pode ser enviada pelo emissor sem que o receptor os consuma.

3- 
b) A maioria dos sistemas reais opera com canais de capacidade finita.
c) Abordagem, na qual o emissor identifica claramente o receptor e vice-versa, é denominada comunicação direta.

4- a) ela possi um prazo pré-definido.
d) isso ocorre no caso da assincrona.
f) o buffer pode ser nulo.
