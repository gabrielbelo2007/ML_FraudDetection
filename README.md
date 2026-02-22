## Detecção de Fraude em Cartão de Crédito

Este projeto consiste no desenvolvimento de um modelo de aprendizado de máquina para identificar transações fraudulentas utilizando o dataset de [Credit Fraud do Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud). 
> O foco principal é lidar com o desbalanceamento dos dados e garantir o melhor resultado na métrica de `ROC-AUC`

---

### 🚀 Estrutura do Projeto
O repositório está organizado da seguinte forma:

- [`EDA.ipynb`](EDA.ipynb): Notebook contendo a Análise Exploratória de Dados para entender a distribuição das variáveis e a correlação entre fraudes.

- [`Preprocess_Training.ipynb`](Preprocess_Training.ipynb): Notebook responsável pelo pré-processamento dos dados (tratamento de desbalanceamento, escalonamento) e pelo treinamento do modelo.

- [`Inference.ipynb`](Inference.ipynb): Notebook para execução de inferências em novos dados utilizando o modelo salvo.

- `Model/`: Pasta que armazena os artefatos do modelo:

    - `XGB_RUS_20-20:35:58.pkl`: O melhor modelo treinado (XGBoost com Random Under Sampling).
    - `history_metrics.csv`: Histórico de desempenho e hiperparâmetros utilizados.

- `requirements.txt`: Lista de dependências e bibliotecas necessárias para rodar o projeto.

- `submissao_credit_fraud.csv`: Arquivo de submissão de resultados para o Kaggle.

---

### 🛠️ Pré-requisitos
    Para garantir o funcionamento correto, utilize a versão do Python 3.12.13.

---

### 🔧 Instalação e Configuração

1.Clonar o repositório:

```Bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

2. Criar um ambiente virtual (recomendado):

```Bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

3. Instalar dependências:

```Bash
pip install -r requirements.txt
```

4. Dataset:

Baixe o dataset diretamente do Kaggle: [Credit Card Fraud Detection]((https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)).

> **Importante**: Coloque o arquivos `train.csv`, `test.csv` baixado diretamente no diretório raiz do projeto.

5. Utilização:

- Execute as células presentes no [`EDA.ipynb`](EDA.ipynb), para verificar as discussões comentadas.

- Caso deseje, faça a execução dos treinamentos dos modelos no [`Preprocess_Training.ipynb`](Preprocess_Training.ipynb), sinta-se livre para experimentar as células comentas e analisar os diferentes resultaddos.

- Por fim, mesmo que não tenha executado o notebook de treinamento, o melhor modelo já está salvo na pasta *Model*, e no [`Inference.ipynb`](Inference.ipynb) é possível executar todas as células para verificar as análises das métricas e gerar o `submissao_credit_fraud.csv`.

---

### 📈 Resultados do Modelo

O modelo selecionado para este projeto foi o XGB_RUS, cujos resultados obtidos no treinamento foram:

- *ROC-AUC*: 0.9794
- *Precisão*: 0.04
- *Recall*: 0.90

Os melhores hiperparâmetros identificados via busca foram: `learning_rate: 0.1`, `max_depth: 3`, `n_estimators: 100` e `subsample: 0.8`.

---

### 💻 Como Utilizar
Para reproduzir os resultados ou testar o modelo, siga a ordem dos notebooks:

1. Execute o `EDA.ipynb` para uma visão geral dos dados.

2. Execute o `Preprocess_Training.ipynb` para processar os dados e gerar o arquivo do modelo.

3. Utilize o `Inference.ipynb` para carregar o arquivo .pkl e realizar predições.