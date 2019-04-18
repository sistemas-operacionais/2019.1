## RESPOSTAS DO CAPÍTULO 03

1 - |             |  Vantagens | Desvantagens  |   
    |-------------|------------|---------------|
    | monolítico  | bom desempenho | erros podem se propagar facilmente pelo núcleo | 
    |             |            | manuntenção e evolução do núcleo complexas |
    | micronúcleo | maior modularidade (serviços desenvolvidos independente dos demais | baixo desempenho|
    |             | mais flexibilidade (serviços podem ser carregados e desativados conforme a necessidade)|               | 
    |             | mais robustez (caso um serviço falhe somente ele será afetado) |               | 
    | em camadas  | níveis de abstração e gerência sofisticados | Desempenho prejudicado pois cada pedido de uma aplicação demora para chegar no dispositivo periférico |
    |             |  | Nem sempre a divisão de funcionalidades do sistema em camadas é óbvia |
    | híbridos    | melhor desempenho |  |
    | máquina virtual    | permite a execução de vários sistemas independentes e isolados entre si sobre o mesmo hardware |  |
    |                    | permite a execução de código independente de plataforma |  |
    |                    | baixo custo adicional |  |
    | contêiner | cada domínio é alocada uma parcela dos recursos do sistema operacional |  |
    |           | os domínios são vistos como sistemas distintos |  |
   
   2 - O Linux possue um núcleo monolítico, mas seu código vem sendo gradativamente estruturado e modularizado. Fazendo dele dessa maneira
   um sistema híbrido.
   
   
