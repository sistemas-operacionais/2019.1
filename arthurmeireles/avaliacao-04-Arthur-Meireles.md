#Arthur Meireles da Silva - 20181014040032

#  Sistemas Operacionais: Conceitos e Mecanismos
##  Capítulo 3 - Exercícios


##  Questão 1

###  A:
####  Comunicação Bloqueante:
Garante o recebimento das mensagens, porém uma das tarefas pode ficar suspensa.
####  Comunicação Não-bloqueante:
Tanto o emissor quanto o receptor ficam funcionando enquanto ambos estiverem disponíveis. Por outro lado, se não houver buffer a comunicação torna-se inviável.

## Questão 2

A comunicação entre tarefas pode ser implementada por duas primitivas básicas: enviar (dados, destino), que envia os dados relacionados ao destino indicado, e receber (dados, origem), que recebe os dados previamente enviados pela origem indicada. Em relação aos aspectos de sincronismo do canal de comunicação, a comunicação entre tarefas pode ser: síncrona ou assíncrona. Síncrona: quando as operações de envio e recepção de dados bloqueiam (suspendem) as tarefas envolvidas até a conclusão da comunicação. Assíncrona: as primitivas de envio e recepção não são bloqueantes: caso a comunicação não seja possível no momento em que cada operação é invocada, esta retorna imediatamente com uma indicação de erro. Semissíncrona: têm um comportamento síncrono (bloqueante) durante um prazo pré-definido. Caso esse prazo se esgote sem que a comunicação tenha ocorrido, a primitiva se encerra com uma indicação de erro.

## Questão 3

### Resposta B

## Questão 4

### Resposta D

## Questão 5

### Resposta C

## Questão 6

### Resposta A

## Questão 7

### Resposta A

## Questão 8

### Resposta D
