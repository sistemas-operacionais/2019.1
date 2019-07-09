### Felipe Barbosa Nicolau Fernandes

## Capítulo 3

### Q1
## (a)
Na comunicação bloqueante o envio e recepção dos dados são realizados o mais breve possível e há garantias de recepção antes da continuação de ambas as tarefas. Como lado negativo uma das tarefas pode ficar suspensa por muito tempo, aguardando a disponibilidade da outra. Na comunicação não bloqueante ambas as tarefas continuam funcionando até que ambas estejam disponíveis para comunicação. Como lado negativo temos a inviabilidade da comunicação não-bloqueante na ausência de um canal de comunicação sem buffer.
## (b)
Os canais com buffering permitem armazenar mensagens enviadas até que sejam recebidas. Como lado negativo está o custo de implementação.
Os canais sem buffering possuem implementação mais simples. Como lado negativo as partes comunicantes precisam estar sempre sincronizadas.
## (c)
Na comunicação por mensagem a informação é enviada em pacotes que são recebidos ou descartados em sua totalidade, não sendo possível receber “meia mensagem”. Como lado negativo pode ocorrer perda de pacotes comprometendo a informação enviada. Na comunicação por fluxo não há separação lógica na informação enviada em operações de envio distintas. Como lado negativo a recepção fica a critério do receptor que pode receber a informação em diferentes tamanhos, além disso o processo de comunicação é mais custoso, visto que é necessário o controle de até onde a informação foi recebida. 
## (d)
As mensagens de tamanho fixo facilitam a comunicação e são mais fáceis de implementar, contudo, limitar o tamanho da mensagem exige técnicas de dividir a mensagem no tamanho determinado. As mensagens de tamanho variado facilitam o envio da informação, podendo adequar o tamanho ao conteúdo da mensagem, entretanto, o processo de comunicação é de maior dificuldade de implementação, visto que é necessário está sempre informando o tamanho da mensagem.
## (e)
Comunicações 1:1 possuem canais e sistemas de gerência do canal mais simples, entretanto, o número de máquinas que se comunicação é limitado. Nas comunicações M:N é possível comunicar a informação a vários receptores, entretanto a dificuldade de implementar o
canal de comunicação e sua gerência é maior.

### Q3 - b
### Q4 - e
### Q5 - a
### Q6 - c
### Q7 - b
### Q8 - d
