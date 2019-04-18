# Sistemas Operacionais: Conceitos e Mecanismos
### Capítulo 3 - Exercícios

## Questão 1

### A:

#### Comunicação Bloqueante:

Garante o recebimento das mensagens, porém uma das tarefas pode ficar suspensa.

#### Comunicação Não-bloqueante:

Tanto o emissor quanto o receptor ficam funcionando enquanto ambos estiverem disponíveis. Por outro lado, se não houver buffer a comunicação torna-se inviável.

### B:

### C:

### D:

### E:

## Questão 2

### Capacidade Nula: 
    
Os dados são enviados diretamente do emissor para o receptor. Por não possuir nenhuma capacidade de armazenamento para buffer, a comunicação é síncrona.
    
### Capacidade Infinita:

O emissor sempre pode enviar dados, que serão armazenados no buffer do canal enquanto o receptor não os consumir. Na comunicação síncrona o receptor pode ficar bloqueado ou na comunicação assícrona é retornado um erro e realizado um nova tentativa. O emissor nunca ficará bloqueado pelo simples motivos de ter espaço "infinito" para armazenar mensagens.

### Capacidade Finita: 

Ao tentar enviar dados em um canal já saturado, o emissor poderá ficar bloqueado até surgir espaço
no buffer do canal e conseguir enviar (comportamento síncrono) ou receber um
retorno indicando o erro (comportamento assíncrono).

## Questão 3

Resposta: B

I: Falso; Na comunicação semibloqueante o tempo de espera não é indefinidamente.

IV: Falso; Na comunicação sícrona o emissor aguarda o receptor ficar pronto para poder enviar a mensagem.

## Questão 4

Resposta: E

I: Falso; Na comunicação semibloqueante o receptor e o emissor espera pelos dados por um tempo X.

II: Falso; Se o canal de comunicação tiver capacidade nula, o emissor e receptor trabalharão com o mecanismo bloqueante.

V: Falso; Irá se comportar como mecanismo não-bloqueante.

## Questão 5

Resposta: A

II: Falso; A maior parte dos sistemas reais operam com canais de capacidade finita.

III: Falso; Os dados serão enviados diretamente para o receptor escolhido (identificado).

## Questão 6

Resposta: C

I: Falso; O contéudo é lido no buffer do canal.

IV: Falso; POSIX não é um exemplo de canal de comunicação com capacidade nula.

## Questão 7

Resposta: B

III: Falso; A memória utilizada é a memória do núcleo.

IV: Falso; Pipes Unix são exemplos de comunicação 1:1.

V: Falso; A comunicação utilizando memória compartilhada não é indicada para compartilhar um grande volume de dados.

## Questão 8

Resposta: D

I: Falso; Apenas um receptor recebe a mensagem.

II: Falso; A mensagem é enviada para todos os receptores.

III: Falso; As filas Posix utilizam conceitos de mailbox.

IV: As filas Posix utilizam a memória do núcleo para transitar.