## Respostas do Capítulo 20 - Software de entrada e saída  

1 - Porque entre dispositivos similares há centenas de modelos de diferentes fabricantes com interfaces distintas. Então acima dos drivers existe uma camada de código, denominada generic device interface, que tem a finalidade de contruir uma visão genérica dos dispositivos para que o sistema operacional não precise conhecer todas as características próprias de cada dispositivo mas possa tratá-los por famílias ou classes.

## Respostas do Capítulo 21 - Discos rígidos  

2 - RAID 0 (striping), RAID 1, RAID 5.

## Respostas do Capítulo 22 - O conceito de arquivo

3 - **Extensão do nome**: usar parte do nome do arquivo para indicar o tipo do conteúdo. Uma vantagem é a fácil identificação do tipo do arquivo pelo usuário.  
**Números mágicos**: usar alguns bytes no início do conteúdo do arquivo para a definição de seu tipo. Nos sistemas UNIX, o utilitário file permite identificar o tipo de arquivo através da análise de seus bytes iniciais e do restante de sua estrutura interna, sem levar em conta o nome do arquivo.   
**Atributos adicionais**: sistemas operacionais definem atributos adicionais no sistema de arquivos para identificar o conteúdo de cada arquivo.  
**Tipos MIME**:  define tipos de arquivos através de uma notação uniformizada na forma “tipo/subtipo”. É usado para identificar arquivos transferidos como anexos de e-mail e conteúdos obtidos de páginas Web.

4 - a) **Incorreta.** Porque um magic number corresponde ao bytes iniciais do arquivo para identificar seu tipo. Não é um atributo numérico separado.  
b) **Correta.**  
c) **Correta.**  
d) **Correta.**  
e) **Incorreta**. Ambos são arquivos de código. O ELF (Executable and Linking Format) é um formato de arquivo usado para programas executáveis e bibliotecas na maior parte das plataformas UNIX modernas. O PE (Portable Executable) é o formato usado para executáveis e bibliotecas na plataforma Windows.

## Respostas do Capítulo 23 - Uso de arquivos

## Respostas do Capítulo 24 - Sistema de arquivos

## Respostas do Capítulo 25 - Diretórios e atalhos
