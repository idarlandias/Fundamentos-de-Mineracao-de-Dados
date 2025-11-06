# Análise Exploratória de Dados do Telegram com Python e DuckDB

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0-blue?style=for-the-badge&logo=pandas)
![DuckDB](https://img.shields.io/badge/DuckDB-0.9-blue?style=for-the-badge&logo=duckdb)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

## 📑 Visão Geral do Projeto

Este repositório contém uma análise exploratória de dados (EDA) detalhada de um dataset de mensagens do Telegram (`fakeTelegram.BR_2022.csv`). O projeto demonstra um fluxo de trabalho completo, desde a limpeza e preparação dos dados até a extração de insights complexos utilizando consultas SQL de alta performance com DuckDB e técnicas de Processamento de Linguagem Natural (PLN).

O objetivo principal é entender padrões de comunicação, comportamento de usuários, tipos de conteúdo compartilhados e o sentimento geral das mensagens na plataforma.

## 🎯 Objetivos da Análise

A análise foi estruturada para responder a uma série de perguntas-chave, agrupadas nas seguintes categorias:

1.  **Estatísticas Gerais:** Quantificar o volume de mensagens, usuários e grupos.
2.  **Análise de Conteúdo:** Diferenciar mensagens de texto e mídia, e categorizar os tipos de mídia.
3.  **Comportamento do Usuário:** Identificar os usuários mais ativos e seus padrões de compartilhamento.
4.  **Análise de Links e Domínios:** Extrair e classificar as URLs e domínios mais compartilhados.
5.  **Análise Textual (PLN):**
    *   Identificar os termos e frases (n-gramas) mais frequentes.
    *   Buscar por mensagens contendo palavras-chave específicas.
    *   Analisar as mensagens com base em seu tamanho.
6.  **Análise de Sentimento:**
    *   Classificar as mensagens mais positivas e negativas.
    *   Identificar os usuários mais "otimistas" e "pessimistas" com base no sentimento médio de suas mensagens.

## 🚀 Tecnologias e Ferramentas

*   **Linguagem:** Python
*   **Ambiente:** Google Colab (Jupyter Notebook)
*   **Bibliotecas Principais:**
    *   **Pandas:** Para a manipulação inicial dos dados e limpeza.
    *   **DuckDB:** Para armazenamento em banco de dados colunar e execução de consultas analíticas SQL de alta velocidade.
    *   **PyArrow:** Para a exportação eficiente dos dados para o formato Parquet.
    *   **Scikit-learn:** Para a extração e contagem de n-gramas (unigramas, bigramas, trigramas).
    *   **LeIA (Léxico para Inferência Adaptada):** Para a análise de sentimento de textos em português do Brasil.
    *   **NLTK:** Para pré-processamento de texto, como a remoção de stopwords.

## 🛠️ Metodologia e Fluxo de Trabalho

O projeto seguiu um fluxo de trabalho estruturado em quatro etapas principais:

#### 1. Carga e Preparação dos Dados
*   O dataset `fakeTelegram.BR_2022.csv` foi carregado em um DataFrame do Pandas.
*   Uma inspeção inicial foi realizada para entender a estrutura dos dados, as colunas disponíveis e os tipos de dados.

#### 2. Limpeza de Dados
*   O principal desafio de limpeza foi a identificação e remoção de **"trava-zaps"** — mensagens maliciosas projetadas para travar o aplicativo.
*   Foi implementada uma função que utiliza critérios heurísticos para detectar essas mensagens, como:
    *   Comprimento excessivo do texto.
    *   Alta proporção de caracteres não alfanuméricos.
    *   Repetição massiva de um único caractere.
*   As linhas identificadas como trava-zaps foram removidas do conjunto de dados.

#### 3. Otimização de Armazenamento e Consulta
*   Para garantir performance e eficiência, o DataFrame limpo foi:
    1.  Exportado para o formato **Parquet**, um formato de armazenamento colunar otimizado para análise.
    2.  Carregado em um banco de dados **DuckDB**, um sistema de gerenciamento de banco de dados analítico em processo, ideal para consultas rápidas e complexas diretamente no ambiente do notebook.

#### 4. Extração e Análise de Insights
*   Todas as 30 análises foram realizadas através de consultas SQL executadas diretamente no DuckDB, com exceção das tarefas de PLN mais complexas.
*   Para a extração de URLs, domínios, n-gramas e análise de sentimento, os dados textuais foram trazidos de volta para o Pandas para aproveitar o poder das bibliotecas especializadas (Regex, Scikit-learn, LeIA).

## 📊 Principais Descobertas e Resultados

*(Esta é uma seção excelente para você preencher com os resultados que encontrou!)*

*   **Usuários Mais Ativos:** A análise revelou que um pequeno número de usuários é responsável por uma grande porcentagem das mensagens totais, indicando a presença de "superusuários" ou bots.
*   **Conteúdo Multimídia:** O tipo de mídia mais compartilhado foi `[TIPO DE MÍDIA]`, sugerindo que o conteúdo visual é predominante nas discussões. *(Exemplo: substitua [TIPO DE MÍDIA] por 'imagem/jpeg' ou 'video/mp4')*
*   **Domínios Populares:** Os domínios mais compartilhados foram `[EXEMPLO DE DOMÍNIO]` e `[OUTRO DOMÍNIO]`, refletindo o consumo de notícias e entretenimento dos usuários. *(Exemplo: substitua por 'youtube.com' ou 'g1.globo.com')*
*   **Análise de Sentimento:** Foi observado que o sentimento médio das mensagens tende a ser `[NEUTRO/NEGATIVO/POSITIVO]`. As mensagens mais negativas frequentemente continham termos relacionados a `[EXEMPLO DE TEMA]`. *(Exemplo: substitua por 'política' ou 'segurança pública')*

## ⚙️ Como Executar o Projeto

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/[SEU-USUARIO]/[SEU-REPOSITORIO].git](https://github.com/idarlandias/Fundamentos-de-Mineracao-de-Dados.git)
    ```
2.  **Ambiente:** Abra o arquivo `.ipynb` no Google Colab ou em um ambiente Jupyter local.
3.  **Dataset:** Faça o upload do arquivo `fakeTelegram.BR_2022.csv` para o ambiente de execução.
4.  **Instale as Dependências:** A primeira célula do notebook contém os comandos `!pip install` para todas as bibliotecas necessárias.
5.  **Execute as Células:** Execute o notebook sequencialmente para replicar a análise.

## ✒️ Autor

*   **Idarlan Rogério Dias Magalhães**
*   **LinkedIn:** https://www.linkedin.com/in/idarlandias/
*   **GitHub:** https://github.com/idarlandias

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.````
