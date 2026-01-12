# Projeto de Análise Exploratória e Pré-Processamento de Dados sobre Estatísticas de Funções de Jogadores da NBA (Temporada 2022-2023)

## 🏀 Resumo do Projeto

Este repositório apresenta um projeto explicativo de Análise Exploratória de Dados (EDA) e pré-processamento robusto de estatísticas de funções (posições de jogo) de jogadores da NBA na temporada 2022-2023. Utilizando um dataset abrangente, o notebook guia o usuário através das etapas essenciais para transformar dados brutos em um formato pronto para futuras modelagens, sobretudo de Machine Learning.

Contribuições adicionais para disseminação dos conceitos e acréscimo de novas ideias são sempre bem-vindos.

## 🚀 Principais Etapas e Metodologia

O projeto segue uma abordagem sistemática, cobrindo as seguintes fases:

### 1. Definição do Problema
* Clarificação dos objetivos do projeto, o tipo de problema de aprendizado (inicialmente EDA e pré-processamento), premissas, hipóteses e restrições dos dados.

### 2. Análise de Dados Exploratória (EDA)
* **Estatísticas Descritivas:** Avaliação detalhada de atributos, contagem de instâncias, tipos de dados e identificação de valores ausentes, discrepantes ou inconsistentes.
* **Visualizações:**
    * 📊 **Distribuições:** Histogramas para entender a distribuição de cada atributo numérico (ex: Idade, Minutos por Jogo, Pontos).
    * 🔗 **Relações entre Variáveis:**
        * Boxplots para comparar estatísticas-chave (ex: Pontos) entre diferentes posições de jogadores.
        * Scatter plots para visualizar a correlação entre variáveis (ex: Minutos por Jogo vs. Pontos, Assistências vs. Pontos).
    * Heatmap **(Matriz de Correlação):** Heatmap para identificar as interdependências entre as principais estatísticas dos jogadores.

### 3. Pré-processamento de Dados Otimizado

Etapa fundamental para garantir a integridade dos dados e prevenir o "vazamento de dados" em futuras modelagens de Machine Learning. Apresentou as seguintes fases:

* **Tratamento de Valores Faltantes:** Valores `NaN` em colunas de porcentagem de arremesso (`FG%`, `3P%`, `FT%`, etc.) são preenchidos com `0`. Essa abordagem é adotada para representar zero acerto em zero tentativas, sendo mais realista do que a remoção de linhas ou imputação com média/mediana.
* **Consolidação de Jogadores 'TOT':** Para jogadores que atuaram por múltiplos times em uma única temporada, suas estatísticas são consolidadas em uma única entrada (`Tm` como 'TOT'), garantindo dados únicos e completos por atleta.
* **One-Hot Encoding:** Variáveis categóricas como `Pos` (Posição do Jogador) e `Tm` (Time) são transformadas em um formato numérico binário, essencial para a maioria dos algoritmos de Machine Learning.
* ⭐ **Divisão em Conjuntos de Treinamento e Teste (Ponto Crucial):** O dataset é dividido em conjuntos de treinamento (80%) e teste (20%) **antes** de qualquer operação de escalonamento. Essa ordem é vital para prevenir o vazamento de informações do conjunto de teste para o treinamento, garantindo uma avaliação imparcial e realista do modelo.
* **Normalização/Padronização de Atributos Numéricos:** As features numéricas (`X_train` e `X_test`) e a variável alvo (`y_train` e `y_test`, se aplicável) são escaladas utilizando `MinMaxScaler` (Normalização) e `StandardScaler` (Padronização). **Os parâmetros dos escaladores são ajustados exclusivamente nos dados de treinamento** e, em seguida, aplicados a ambos os conjuntos.
* **Visualização Pós-Padronização:** Demonstrações visuais da distribuição das variáveis após o escalonamento, confirmando a alteração da escala mantendo a forma original da distribuição.

## ✅ Conclusão

O resultado deste projeto é um dataset limpo, consistente e bem estruturado (`X_train`, `X_test`, `y_train`, `y_test` e suas versões escaladas), que está agora pronto para diversas aplicações de Machine Learning. Isso inclui:

* **Regressão:** Para prever o desempenho (ex: pontos por jogo) com base em outras estatísticas.
* **Classificação:** Para identificar a posição de um jogador a partir de suas estatísticas.
* **Agrupamento (Clustering):** Para descobrir perfis de jogadores com base em seus atributos.

A metodologia empregada neste projeto estabelece uma base sólida e confiável para análises futuras e o desenvolvimento de modelos preditivos mais avançados.

## 💡 Fonte dos Dados:

Os dados originais foram obtidos de um dataset público disponível no Kaggle: NBA Player Stats 2022-2023. O arquivo pode ser acessado em: [https://www.kaggle.com/datasets/prxshetty/nba-player-stats-2022-2023].
Para fins didáticos e de referência ao projeto, o arquivo armazenado neste repositório foi renomeado, sem nenhuma alteração em seu conteúdo.

## ⚙️ Tecnologias e Ferramentas:

* Linguagem de Programação: Python

* Bibliotecas Principais:

    * `pandas`: Para manipulação e análise de dados.

    * `numpy`: Para operações numéricas.

    * `matplotlib` e `seaborn`: Para visualização de dados.

    * `scikit-learn`: Para pré-processamento (`MinMaxScaler`, `StandardScaler`, `train_test_split`).

## 🔗 Link direto do Notebook para o Google Colab:
https://colab.research.google.com/github/rodrigobsouza17/Analise_de_Dados/blob/MVP/MVP_An%C3%A1lise_de_dados_2025_V4.ipynb
