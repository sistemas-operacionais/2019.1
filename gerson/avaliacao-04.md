## Questão 1


## Questão 2

  A comunicação entre tarefas pode ser implementada por duas primitivas básicas: enviar (dados, destino), que envia os dados relacionados ao destino indicado, e receber (dados, origem), que recebe os dados previamente enviados pela origem indicada. Em relação aos aspectos de sincronismo do canal de comunicação, a comunicação entre tarefas pode ser: síncrona ou assíncrona.
  Síncrona: quando as operações de envio e recepção de dados bloqueiam (suspendem) as tarefas envolvidas até a conclusão da comunicação.
  Assíncrona: em um sistema com comunicação assíncrona, as primitivas de envio e recepção não são bloqueantes: caso a comunicação não seja possível no momento em que cada operação é invocada, esta retorna imediatamente com uma indicação de erro.
 
