# 🎬 Análise e Limpeza de Dados de Filmes Brasileiros

Este repositório contém um script em Python desenvolvido para o **Google Colab** com o objetivo de importar, analisar e realizar o tratamento de dados de uma planilha de filmes da Programadora Brasil. O foco principal do script é a limpeza e padronização da coluna de Unidades Federativas (UF), permitindo uma contagem precisa da produção audiovisual por estado.

## 📂 Fonte dos Dados

Os dados originais utilizados neste projeto são públicos e foram disponibilizados pelo Governo Federal por meio do Portal de Dados Abertos. 

* **Conjunto de dados:** Filmes e Sessões da Programadora Brasil
* **Link para acesso:** [dados.gov.br/dados/conjuntos-dados/filmes-e-sessoes-da-programadora-brasil](https://dados.gov.br/dados/conjuntos-dados/filmes-e-sessoes-da-programadora-brasil)
* **Arquivo utilizado:** `15pb-filmes-pbi-a-pbvi.xlsx`

## ✨ O que o script faz?

O código está dividido em células lógicas para o Google Colab e realiza as seguintes etapas:

* **Instalação de Dependências:** Instala bibliotecas necessárias para manipulação de planilhas (`openpyxl`, `odfpy`) e requisições (`requests`).
* **Importação e Inspeção Visual:** Carrega a base de dados em um *DataFrame* do Pandas, exibindo as primeiras linhas e a estrutura geral (tipos de dados, valores nulos).
* **Seleção de Colunas:** Isola colunas de interesse (`Título do filme`, `Direção`, `Ano`, `UF`).
* **Filtragem Específica:** Cria um recorte específico para analisar filmes produzidos no estado do Amazonas (`AM`).
* **Tratamento e Exploração de Dados (Explode):**
    * Padroniza diferentes separadores de UF presentes na base (como `/`, `-`, `,`) para um delimitador único (`;`).
    * Separa filmes que foram co-produzidos por múltiplos estados em linhas individuais (função `explode`).
    * Remove espaços em branco, formata o texto para maiúsculas e limpa valores nulos/inválidos (`NAN`, `NONE`).
* **Geração de Relatório:** Gera uma tabela final limpa com a contagem exata de filmes por Estado (UF).

## 🚀 Como executar no Google Colab

Como o script foi projetado para rodar em nuvem, siga os passos abaixo:

1. **Abra o Google Colab:** Crie um novo notebook ou importe o arquivo `.ipynb` deste repositório (caso aplicável).
2. **Upload do Arquivo de Dados:**
    * Baixe a planilha diretamente no link da fonte de dados acima (ou utilize a versão presente neste repositório, se houver).
    * No menu lateral esquerdo do Colab, clique no ícone de pasta (📁 "Arquivos").
    * Faça o upload da planilha com o nome exato: `15pb-filmes-pbi-a-pbvi.xlsx`.
    * *Nota: O script procura o arquivo diretamente no caminho padrão de uploads do Colab: `/content/15pb-filmes-pbi-a-pbvi.xlsx`.*
3. **Execute as Células:** Rode as células de código sequencialmente. O script indicará quando as instalações forem concluídas e exibirá as tabelas ao longo do processo.

## 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Python 3.x**
* **Pandas:** Para manipulação, limpeza e análise dos dados.
* **Openpyxl:** Engine para leitura de arquivos Excel modernos.
* **Odfpy:** Engine de suporte caso haja manipulação de arquivos OpenDocument.

## 📊 Estrutura Esperada do Arquivo Original

Para que o script funcione perfeitamente, o arquivo `.xlsx` deve conter as seguintes colunas (exatamente com estas grafias):
* `Título do filme`
* `Direção`
* `Ano`
* `UF` (Esta coluna é o foco principal do tratamento de dados)

## 🧏‍♂️ Perguntas que fundamentaram este script

* Quais as produções por Unidade Federativa?
* Quais as produções do ano de 2007?
* Quais produções foram feitas no Estado de São Paulo no ano de 2007?
* Quantas produções foram feitas por Unidade Federativa (UF)?
* Quantas produções foram feitas no Estado de São Paulo no ano de 2007?
* Quantas produções foram feitas por ano em cada estado?

# 👀 Conclusão

Este projeto teve origem a partir de um curso que concluí no programa TIC EM TRILHAS da PUC-Rio (Pontifícia Universidade Católica do Rio de Janeiro), onde pude aplicar conceitos de análise de dados utilizando a linguagem Python e a biblioteca Pandas.

Durante o desenvolvimento, identifiquei que os dados originais apresentavam diversas inconsistências de formatação. No entanto, essas barreiras foram superadas através do processo de limpeza de dados (data cleaning). Um exemplo prático estava na coluna 'UF', que continha registros duplicados por causa de espaçamentos invisíveis (como "SP" e "SP "), o que distorceria os resultados finais caso não fossem devidamente padronizados.
---
*Este script é um excelente exemplo de como tratar dados sujos (dirty data) em colunas que contêm múltiplos valores categóricos agregados em uma única célula utilizando a biblioteca Pandas.*
