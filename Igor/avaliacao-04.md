>### Cap. 3
#### Comunicação entre tarefas - Respostas

1.  
     **a)** Comunicação bloqueante: **O envio e a recepção bloqueiam as tarefas no momento que são envidas, deste modo, acaba impedindo possível interferência na hora de trocar as mensagens.**  
     
     Comunicação não-bloqueante: **O software sempre será executando independente da mensagem de retorno, isso permite ao desenvolvedor tratar exceções para sua execução nunca quebrar.**
     
     **b)** Canais com Buffering: **Caso o canal possua um buffering, o seu emissor pode enviar dados simultanêos para o receptor sem preocupação, uma vez que o receptor vai reenviando um-à-um através do buffer. **  
     
     Canais sem Buffering: **Sem buffering, ocorreu exatamente o contrário, teremos uma comunicação realizada de forma direta, sem cópias intermediárias, o que ocasiona um professor mais rápido.**  
     
     **c)** Comunicação por mensagens: **Nesta comunicação as mensagens são enviadas por partes, mesmo sendo enviados por parte o recebimento é de forma completa.**  
     Comunicação por fluxo: **Na comunicação por fluxo, uma mensagem pode ser enviada em vários pacotes, deste modo aumentando as chances de perca durante a transmissão.**  
     
     **d)** Mensagem de tamanho fixo: **O receptor sempre tem conhecimento se houve perca de dados durante a transmissão, desvantagem deste processo é que esta mensagem sempre terá um tamanho fixo.**  
     
     Mensagem de tamanho variável: **O receptor nunca tem conhecimento do tamanho da mensagem, por outro lado, o espaço na memória fica livre até receber a mensagem.**  
     
     **e)** Comunicação 1:1: **Famosa comunicação impementada no protocolo TCP, acontece quando um emissor e um receptor integeram através de um canal de comunicação.**
     
     Comunicação M:N: **Acontece quando 1 ou + emissores envia mensagem para 1 ou + de um receptor.**

2. Existe duas primitivas básicas para implementação da comunicação entre as tarefas. são elas:  
    **Enviar: envia os dados relacionados ao destino indicado;**  
    **Receber: recebe os dados previamente enviados pela origem indicada;**  
 Os canais de comunicação entre as tarefas podem ser nomeados como síncrona e assíncrona, na comunicação **síncrona** podemos dizer que as operação de envio e recepção de dados suspendem as tarefas enquanto não é concluída a comuncição. Na **assíncrona** o envio e a recepção não ficam em estado ausentes, tendo em vista que caso a comunicação apresente dificuldades e as operação invocadas não consigam se concretizar, uma mensagem de erro é retornada. Por fim, o **semissínicrono** têm um comportamente semelhante ao síncrono, mas ele atual em um prazo **pré-definido**, neste caso, se ao final do prazo a comunicação não ocorreu, uma mensagem de erro é exibida.
3. b) II, III, V  (CORRETA)  
4. d) II, IV - (CORRETA)  
5. c) II, IV - (CORRETA) 
6. a) I, III - (CORRETA)  
7. a) I, III, V - (CORRETA)
8. d) V - (CORRETA)
