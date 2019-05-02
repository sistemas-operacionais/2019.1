## Avaliação 03 - Capítulo 08 - Comunicação entre tarefas
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
          
   e) Na comunicação 1:1, não é necessário tratar colisões de comunicação por exemplo, mas só um receptor recebe essa msg ou fluxo por vez, já na M:N eu posso ter a mesma informação sendo mandada simultâneamente para vários receptores, mas há um maior perigo de ocorrer algum problema de sincronização.
     
2. Usando capacidade nula, o emissor teria de enviar todos as mensagens de uma vez, sendo assim, a utilização do método síncrono seria mais vantajosa, sendo que na forma assíncrona o emissor teria que checar se o receptor está pronto para receber todo o tempo.  
Usando capacidade infinita, o emissor poderia enviar as mensagens despreocupadamente, enquanto o receptor poderia receber assim que ele estivesse disponível sabendo que as informações sempre estariam disponíveis no buffer.  
Usando a capacidade finita (real), o emissor a cada emissão deve checar se o buffer está cheio, se ele não estiver a mensagem é enviada se não ele deve esperar até que o buffer fique vazio. O receptor ainda teria a liberdade de consumir as informações como fosse necessário.  
  
3. b) Canais de capacidade finita, e nula são os únicos que podem ser implementados realmente, sendo o de capacidade finita amplamente utilizado na prática.  
c) Na comunicação direta, o emissor envia direto para o receptor, e não para um canal.  
e) Não é o núcleo e sim o canal de comunicação.  
  
4. a) Isso ocorre dentro de um prazo pré-definido.  
c) Ele se equipara a um sistema de comunicação não-bloqueante.
d) Isso ocorre na comunicação não bloqueante.  
e) Eles devem usar sistemas bloqueantes.
f) É melhor com buffer, mas a implementação é possível mesmo sem o buffer.
