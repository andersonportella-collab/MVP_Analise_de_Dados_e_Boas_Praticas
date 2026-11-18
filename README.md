# MVP — Análise de Dados e Boas Práticas

**MBA em Ciência de Dados e Analytics — PUC-Rio**

**Tema:** Movimentação de óleo diesel A S10 em terminais aquaviários do Sudeste brasileiro, em 2025.

Este repositório contém o notebook de análise exploratória e pré-processamento de dados desenvolvido como MVP da disciplina Análise de Dados e Boas Práticas. O estudo é **descritivo**: não treina modelos de aprendizado de máquina.

## Notebook

- [MVP_ANP_Terminais.ipynb](MVP_ANP_Terminais.ipynb)
- [Abrir notebook no Google Colab](https://colab.research.google.com/github/andersonportella-collab/MVP_Analise_de_Dados_e_Boas_Praticas/blob/main/MVP_ANP_Terminais.ipynb) (verificar permissões e execução antes da entrega)

## Perguntas investigadas

- **H1:** Como o volume mensal de recepção aquaviária de diesel A S10 se distribuiu entre os terminais do Sudeste em 2025?
- **H2:** Qual foi a participação de cada modo de transporte nas entregas de diesel A S10 registradas, por terminal com entregas reportadas?

## Fonte e proveniência

**Fonte:** Agência Nacional do Petróleo, Gás Natural e Biocombustíveis (ANP), [Movimentação dos Terminais Aquaviários](https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/movimentacao-dos-terminais-aquaviarios).

**Arquivo consultado pelo notebook:**

https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/arquivos/arquivos-movimentacao-dos-terminais-aquaviarios/dados-abertos-movimentacao-terminais-aquaviarios.csv

**Dicionário oficial:** [Metadados de movimentação dos terminais aquaviários](https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/arquivos/arquivos-movimentacao-dos-terminais-aquaviarios/metadados-movimentacao-terminais-aquaviarios.pdf).

A versão recebida no desenvolvimento, documentada no notebook, tinha **190.944 linhas**, **13 colunas** e o hash SHA-256:

`5e4a123e8013fc9b36bfe54a58a4d8bcb7f5332eef89b7ec8e309cd92e0edc86`

Embora a URL termine em `.csv`, o arquivo recebido foi identificado pelo conteúdo binário como Excel. O carregamento do notebook detecta o formato efetivo.

**Cópia arquivada no repositório:** [dados-abertos-movimentacao-terminais-aquaviarios.xlsx](dados-abertos-movimentacao-terminais-aquaviarios.xlsx), na raiz da branch `main` (arquivo de 10.978.111 bytes, conforme metadados do GitHub). O hash SHA-256 desse arquivo arquivado **ainda precisa ser conferido** contra o hash da versão usada no desenvolvimento. O código atual continua buscando a fonte original da ANP; a cópia no GitHub não é carregada automaticamente.

## Como reproduzir

1. Abra o notebook pelo link do Colab acima.
2. Utilize um ambiente novo com Python 3 e execute as células na ordem, de cima para baixo.
3. São usadas as bibliotecas **pandas**, **openpyxl** e **matplotlib**, além de módulos da biblioteca padrão do Python. As versões relevantes são impressas pelo notebook durante a execução.
4. Garanta acesso à internet para baixar o arquivo da ANP pela URL indicada. O carregamento não depende de credenciais pessoais.
5. Confira a impressão do SHA-256, a quantidade de linhas e os resultados. Se o hash diferir do valor de referência, a fonte pode ter sido atualizada: **não presuma reprodução numérica exata**.
6. O autor informou ter executado todas as células, uma a uma, no Colab, sem erros. A validação em uma **sessão inteiramente nova**, com execução sequencial completa, continua recomendada antes da entrega.

## Escopo e procedimento

O código recorta os registros de **2025**, dos terminais do **Sudeste**, e seleciona o produto pelo código ANP **420105001**, que abrange variações textuais da descrição de diesel A S10.

O notebook documenta:
- caracterização da fonte, da unidade de observação e das variáveis;
- análise de ausências, repetições, inconsistências e volumes extremos;
- estatísticas descritivas e frequências;
- comparação de alternativas em decisões metodológicas D1, D2 e D3;
- tabelas e gráficos associados a H1 e H2;
- respostas às perguntas, limites da interpretação e checklist de entrega.

## Nota técnica: preservação dos registros publicados

As análises principais preservam as linhas do recorte conforme recebidas da ANP, inclusive linhas exatamente idênticas, volumes iguais a zero e volumes sinalizados como extremos. Isso mantém a rastreabilidade em relação ao arquivo recebido e evita excluir observações sem evidência suficiente de erro.

A preservação **não significa que as repetições tenham sido comprovadas como operações distintas**. Como a base não apresenta um identificador individual de operação que permita resolver essa questão, o notebook compara os resultados com e sem cópias exatas, quantificando seu efeito. Também distingue valores zero explicitamente informados de combinações de terminal e mês sem registro; estas últimas não são automaticamente convertidas em zero.

Essa opção metodológica é justificada e sujeita a limitações, não uma garantia de ausência de problemas de qualidade. A reprodutibilidade também depende da preservação da versão exata do arquivo de origem, identificada pelo hash.

## Limitações e transparência

Os resultados descrevem movimentações informadas à ANP para o recorte, sem estabelecer causalidade, demanda final, origem do produto ou capacidade instalada. Alterações futuras do arquivo publicado podem afetar a reprodução numérica. A declaração de uso de IA, referências completas e interpretações estão no notebook e devem ser revisadas pelo autor antes da submissão.

## Entrega

Antes de submeter, verificar:
- [x] execução célula a célula no Colab sem erros, conforme informação do autor;
- [ ] execução integral no Colab a partir de ambiente novo, se ainda não realizada;
- [ ] correspondência do hash do arquivo arquivado com a versão analisada;
- link do Colab, permissões e demais requisitos do ambiente da disciplina;
- identificação do aluno, declaração de IA e commit válido para o prazo de entrega.

**Status:** dados arquivados no GitHub; execução célula a célula reportada pelo autor como bem-sucedida. Conferência do SHA-256, validação em ambiente novo e demais etapas de submissão ainda não concluídas.
