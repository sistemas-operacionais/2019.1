1. a) comunicações bloqueantes garantem que a mensagem vai ser entregue, com o problema de atraso de performance, já que tanto o receptor quanto o emissor precisam esperar para a divulgação da mesma; enquanto isso, na não bloqueante não há esta espera, o que não garante a entrega da mensagem, porém com ganho na perfomance.
b) comunicações com buffering podem mandar mensagens para uma espécie de depósito provisório, onde elas podem esperar o momento apropriado para serem enviadas para o receptor. O problema é que os buffers podem ficar cheios, o que atrasaria o envio de novas mensagems. Processos sem buffer são sempre atrasados de uma maneira mais estável.
c) Comunicações por mensagens enviam mensagens únicas, individuais e completas. A mensagem precisa chegar por inteiro e na ordem correta, enquanto no de fluxo as mensagens são enviadas uma após a outra, em sucessão, porém pode haver perda de integridade das mesmas.
d) mensagens de tamanho fixo são mais fáceis de sincronizar, já que sempre terão um tamanho fixo, porém são limitadas no seu tamanho e logo não se pode enviar mensagens maiores; porém as mensagens de tamanho variável, mais versáteis, podem atrasar o sistema.
e) comunicação 1:1 é de um único emissor para um único receptor, enquanto N:M é de vários emissores que podem enviar para vários receptores. O primeiro é mais organizado e pode evitar mais conflitos, porém é limitado a apenas uma comunicação por vez; enquanto o segundo é mais rápido, mas pode sofrer de conflitos/gargalos e necessita de maior perfomance.

2. quando de forma sincrona, ambos os processos fazem uma parada quando a mensagem é enviada, esperando que a mesma seja recebida pelo receptor. quando de forma assincrona, torna-se necessario criar um buffer já que não existe esta espera, geralmente com capacidade finita (já que capacidade infinita seria utopico). logo, quando o buffer fica saturado, finalmente o emissor é bloqueado e precisa esperar até a liberação.

3. b) II, III e V
 - A I está errada pois neste tipo de comunicação (semi-bloqueante) o processo só espera por um determinado prazo.
 - A IV está errada pois neste tipo de comunicação não há sequer razão para haver mensagem de erro, já que ambos emissor e receptor vão esperar pela informação no mesmo espaço de tempo sincronizado.

4. e) III e IV
- A I está errada pois neste tipo de comunicação ambos esperam pela informação, embora por períodos de tempo limitados e talvez de forma assincrona.
- A II está errada pois exatamente nesta situação (capacidade nula) ambos o emissor e receptor DEVEM usar mecanismos bloqueantes para garantir a integridade da comunicação.
- A V está errada pois um mecanismo de comunicação semi-bloqueante com prazo t=0 nunca poderia se comunicar.

5. a) II e III, pois existem mais usos para canais com capacidades finitas do que a definição de algoritmos, como por exemplo os pipes do UNIX e na comunicação direta o dado é enviado do emissor ao receptor diretamente, enquanto um canal de comunicação é somente usado na comunicação indireta.

6. d) I e IV. I - Nem toda troca de mensagens necessariamente precisa de buffer para ser feita e IV - As filas de posix são um grande exemplo de implementação de mailbox, impossibilitando que seja de capacidade nula.

7. e) III e V. I está errada pois não é a memoria compartilhada que faz isso, já que ela serve apenas como um ponto em comum entre os processos. II está errada pois a troca de dados pela memoria compartilhada é melhor para processos que se comunicam num mesmo sistema físico. A IV está errada pois os pipes do UNIX são um bom exemplo de comunicação 1:1, e não N:M. 

8. d) V. A I e a II estão erradas pois seus significados estão trocados: mailbox envia cada mensagem a um receptor, enquanto canal de eventos replica as mensagens para todos os receptores. A III está errada pois as filas de mensagens POSIX sao na verdade um bom exemplo de MAILBOX. IV está errada pois os arquivos criados pelo POSIX não passam pelo disco.
