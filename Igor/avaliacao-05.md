
>### Cap. 4
#### Mecanismos de comunicação - Respostas

1.  Nos primordios da implementação **UNIX System V** as filas de mensagem foram criadas, atualmente, a maioria dos Systems suportam elas. Em contrapartida ao **System V** existe o padrão **POSIX** que define uma interface para manipulação de filas. Um bom exemplo de implementação do conceito de fila é uma caixa de mensagem eletrônica.  

2.  **Pipe** é um dos muitos mecanismos de comunicação existente entre processores simples no ambiente **UNIX**. Quando falamos de interface de linha de comandas, o **pipe** é usado para criar uma conexão entre a saída padrão (stdout) de um comando à entrada padrão (stdin) de outro comando, assim a comunicação é realizada.

3. **Núcleo:** Reponsável pelas chamadas do sistema, uma vez que não existe acesso a variáveis comuns.


4. *D) Processos que se comunicam por memória compartilhada podem acessar a mesma área da RAM.*  
**Errado**, pois os processos que fazem comunicação por memória compartilha podem acessar a mesma área do núcleo.  
*E) Os pipes Unix são um bom exemplo de comunicação M:N*  
**Erado**, o pipes é um bom exemplo de comunicação 1:1
