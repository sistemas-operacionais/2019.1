## Respostas do Catítulo 08 - Comunicação entre Tarefas

1 - a) Comunicação bloqueante: garante que a aplicação não vai continuar sem obter a resposta, porém ela impede que nesse durante esse tempo de espera outras tarefas utilizam o processador.  
       Comunicação não-bloqueante: caso a comunicação não seja possível no momento em que cada operação é invocada, esta retorna imediatamente com uma indicação de erro. É necessário criar um canal ou buffer para armazenar os dados da comunicação entre eles.  
       
   b) Buffering: uma quantidade finita de dados pode ser enviada pelo emissor sem que o receptor os consuma. Todavia, ao tentar enviar dados em um canal já saturado, o emissor poderá ficar bloqueado até surgir espaço no buffer do canal.  
      Sem-buffering: a comunicação é feita por transferência direta dos dados do emissor para o receptor, sem cópias intermediárias. Essa situação implica em uma forte sincronização entre as partes. Por outro lado, a comunicação assíncrona torna-se inviável.  
      
   c) Por mensagem: cada mensagem consiste de um pacote de dados que pode ser tipado ou não. Esse pacote é recebido ou descartado pelo receptor em sua íntegra; não existe a possibilidade de receber “meia mensagem”. Podem ocorrer perdas de mensagens.  
      Por fluxo:  o canal de comunicação é visto como o equivalente a um arquivo: o emissor “escreve” dados nesse canal, que serão “lidos” pelo receptor respeitando a ordem de envio dos dados. Não há separação lógica entre os dados enviados em operações separadas: eles podem ser lidos byte a byte ou em grandes blocos a cada operação de recepção, a critério do receptor. Pode ocorrer perde de sequências de bytes.        
   e) 1:1: a vantagem é que o canal de comunicação fica exclusivo para eles.  
      M:N: O canal é compartilhado. Podendo haver colisões.  
      
 2 - O emissor será bloqueado até que a informação seja recebida pelo receptor. O emissor poderá ficar bloqueado até surgir espaço no buffer do canal e conseguir enviar (comportamento síncrono) ou receber um retorno indicando o erro.  
 
 3 - a) Correta.  
     b) Incorreta. A maioria dos sistemas reais opera com canais de capacidade finita.  
     c) Na comunicação direta, o emissor envia os dados diretamente ao receptor.  
     d) Correta.  
     e) Incorreta. Não é o núcleo que transfere os pacotes. O emissor envia os pacotes para o receptor.  
     
4 - a) Incorreta. Possue um comportamento síncrono (bloqueante) durante um prazo pré-definido. Caso esse prazo se esgote sem que a comunicação tenha ocorrido, a primitiva se encerra com uma indicação de erro.  
    b) Incorreta. O receptor é quem permance bloqueado até que o receptor receba a mensagem.  
    c) Correta.  
    d) Incorreta. Isso acontece na comunicação assíncrona.  
    e) Correta.  
    f) Correta.  
