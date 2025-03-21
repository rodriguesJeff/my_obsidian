
---
#### **# [GLPI#2112379082] [LEITURA E EMISSÃO DE FATURAS] [PRODUÇÃO] [MELHORIA] Ajuste da tela**
##### Descrição dada pelo cliente
* Ajustar o tamanho das telas para que não seja necessário clicar em mostrar mais informações ou rolar a tela.
* Esse ajuste é essencial para um melhor desempenho dos leituras em campo.
* Segue prints das telas coletor x celular.
* Tarefa 050
##### Plano de ação
- [x] Diminuir tamanho dos componentes na tela de Leitura para que o usuário não precise rolar a tela
- [x] Expandir botão de "Mostrar mais informações" por padrão na tela de listagem de logradouros
##### O que fiz?
Instalei o device preview para testar o app em tamanhos de tela diferentes.
Diminuí os tamanhos dos campos de formulário na tela de Leitura
Diminuí os espaçamentos entre os componentes na tela de leitura
Removi a opção de expandir componente de selecionar logradouro

---
#### **# [GLPI#2112379065] [LEITURA E EMISSÃO DE FATURAS] [PRODUÇÃO] [BUG] Diferença de valor na faixa maior que 30m3 - Arquivo RC
##### Descrição dada pelo cliente
* Comparando os arquivos de saída (RC) Coletor x Celular, identificou-se uma diferença no campo de m3 de tratamento.
* Esse campo encontra-se na posição 592 com tamanho de 11
* Segue a fatura e o arquivo de comparação, onde a primeira linha é a leitura feita no coletor e a segunda linha é a leitura feita no celular.
##### Plano de ação
- [x] Ler o arquivo de saída, procurar pelo cliente com código: 867226
- [x] Verificar a coluna 592
- [x] Comparar os valores que temos no RC do app e identificar a diferença
- [x] Verificar o cálculo para faixa de 30m³
- [x] Checar app antigo (se for preciso) e entender como esse valor é passado
- [x] Validar no app novo se recebemos algum dado parecido com o do app antigo e onde é inserido (ou não)
##### O que eu fiz?
Verificando os arquivos, esses foram os resultados obtidos:
- Linha 1: `1410`
- Linha 2: `32800`
Identificado o problema:
![[Pasted image 20250320135822.png]]
Na posição do array que está marcada, estava passando o valor da água, mas é preciso passar do tratamento, que no caso seria:
> retornoDoCalculoFaixas.valores`[3][6]`

Portanto, o resultado foi:
![[Pasted image 20250320145946.png]]
Onde a primeira linha é o valor emitido pelo leitor, o segundo é o do app na versão anterior que estava com erro e o terceiro é o corrigido.

#### # [GLPI#2112379084] [LEITURA E EMISSÃO DE FATURAS] [PRODUÇÃO] [BUG] Logradouro -Quebra de rua
##### Descrição dada pelo cliente
* Na tela de Logradouro, ajustar a quebra das ruas.
* A quebra da rua deve ser pelo número da tarefa e o nome da rua.
* Segue prints das telas Coletor x Celular para comparação.
##### Plano de ação  
- [x] Ver qual o código da tarefa em questão
- [x] Verificar no retorno da API como vêm as ruas
- [x] Verificar como o app antigo separava as ruas
- -> O app antigo cria uma classe de Logradouro com base no código da tarefa, nome do logradouro, tipo e bairro.
- [x] Verificar como o app trata as ruas e como as separa umas das outras
- [x] Aprimorar o algoritmo que separa as ruas em listas para considerar não somente o nome das ruas mas também o código da tarefa
##### O que eu fiz?
Tive que modificar o setter de imóveis, bem como o fromJson do Imovel e do logradouro, para pegar o código da tarefa.
Tive que modificar também como funcionam os contadores de leituras já realizadas e por realizar pois após fazer as correções acima, o app não estava mais conseguindo comparar a rua de um imóvel com a lista de ruas e assim fazer a validação.