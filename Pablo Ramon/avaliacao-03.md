## Avaliação 03 - Páginas [12 - 15]
## Discente: **Pablo Ramon Varela de Souza**

1. a) A principal vantagem da comunicação bloqueante (síncrona), é que não haverá erros por causa do receptor não estar disponível
      já que o transmissor só irá mandar os dados quando ambos estiverem prontos, 
      já a desvantagem é que todas as tarefas associadas são paradas (bloqueadas) nesse meio tempo, e também que pode haver um tempo
      de espera até que os dois lados da comunicação estejam prontos.  
        
   b) Um canal com *buffering* permite que uma transmissão seja interrompida e continuada em outro momento pois os dados que são transmitidos
      são salvos temporariamente no buffer permitindo que o receptor leia esses dados quando estiver disponível, isso é uma vantagem
      principalmente na transmissão assíncrona pois ajuda a diminuir os erros de transmissão por indisponibilidade.  
        
      Um canal sem *buffering* é ideal para transmissões síncronas que não precisam que os dados sejam guardados já que ambos os lados
      da transmissão são dedicados a transferir os dados nesse tipo de transmissão. O buffer nesse caso acabaria atrapalhando a transmissão
      sendo uma etapa a mais para a conclusão da mesma.  
        
   c) A maior vantagem da comunicação por mensagens é a divisão dos dados em pacotes, e a não obrigatoriedade dos pacotes chegarem ao mesmo tempo,
      A desvantagem é que isso pode causar a necessidade de vários reenvios por parte do transmissor.
      Na comunicação em fluxo o canal é usado como um arquivo, assim o transmissor **escreve** no canal e o receptor **lê** do canal
      quando fica disponível.  
        
   d)   
   e)  
     
2. Na comunicação síncrona, o processo que usa mensagens para se comunicar usa o canal com capacidade nula, já que não é de seu
   interesse guardar as informações durante o envio. Nesse caso, quando um pacote é perdido ele tem de ser reenviado pelo emissor.
   Na comunicação assíncrona, o processo usa o canal com capacidade finita, então ele empilha mensagens no buffer até chegar a capacidade
   ou acabar a transmissão.
