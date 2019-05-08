
>### Cap. 4
#### Mecanismos de comunicação - Respostas

1.  Nos primordios da implementação **UNIX System V** as filas de mensagem foram criadas, atualmente, a maioria dos Systems suportam elas. Em contrapartida ao **System V** existe o padrão **POSIX** que define uma interface para manipulação de filas. Um bom exemplo de implementação do conceito de fila é uma caixa de mensagem eletrônica.  

2.  **Pipe** é um dos muitos mecanismos de comunicação existente entre processores simples no ambiente **UNIX**. Quando falamos de interface de linha de comandas, o **pipe** é usado para criar uma conexão entre a saída padrão (stdout) de um comando à entrada padrão (stdin) de outro comando, assim a comunicação é realizada.

3. **Núcleo:** Reponsável pelas chamadas do sistema, uma vez que não existe acesso a variáveis comuns.


4. *D) Processos que se comunicam por memória compartilhada podem acessar a mesma área da RAM.*  
**Errado**, pois os processos que fazem comunicação por memória compartilha podem acessar a mesma área do núcleo.  
*E) Os pipes Unix são um bom exemplo de comunicação M:N*  
**Erado**, o pipes é um bom exemplo de comunicação 1:1  
*F) A comunicação através de memória compartilhada é particulamente indicada para compartilhar grandes volumes de dados entre dois ou mais processos*  
**Errado**, a comunicação por meio de memória compartilhada é pobre caso a comunicação possua um grande volume frequente de dados ou esteja envolvendo muitos processos.  
*G) As filas de mensagens POSIX são um bom exemplo de canal de eventos.*  
**Errado**, um bom exemplo de filas de mensagens POSIX é uma caixa correio eletrônico.  
*H) Nas filas de mensagens POSIX, as mensagens transitam através de arquivos em disco criados especialmente para essa finalidade.*  
**Errado**, As mensagens seguem fluxos de arquivos UNIX System V onde as finalidades destes arquivos é a manipulação filas de mensagens.
