# Sobre o Projeto
Esse projeto foi feito com a [base de dados pública da Olist disponibilizada no Kaggle](https://www.kaggle.com/olistbr/brazilian-ecommerce).

O objetivo do modelo de machine learning é calcular a propensão de que um dado seller da Olist não irá revender nos próximos 6 meses.

# API e Web App

## Steps para execução da API e Web App
### 1. Instale o Git
* Link para download: https://git-scm.com/downloads

### 2. Faça o clone do código fonte
Abra o `CMD` e digite o seguinte comando para baixar o código

```
git clone https://github.com/helio69/propensao-revenda-v2.git
```

Depois de finalizado, digite o comando `dir` e verifique que uma pasta chamada `propensao-revenda` ou `propensao-revenda-main` agora existe no seu computador.
Essa pasta contém todo o código fonte da nossa aplicação. Navegue até a pasta digitando o seguinte comando no `CMD`

```
cd propensao-venda
```

ou 

```
cd propensao-venda-main
```

### 3. Instale o Anaconda e o Miscrosoft Visual Studio Build Tools
* Link para download: https://www.anaconda.com/download/success

No momento da instalação, selecionar a seguinte opção: `Add Anaconda3 to my PATH environment variable`

* Link para download: https://visualstudio.microsoft.com/pt-br/downloads/

### 4. Crie um ambiente python com Anaconda

```
conda create --name ambiente_api python==3.11
```

### 5. Ative o ambiente python criado no passo anterior

```
conda activate ambiente_api
```

### 6. Instale os pacotes necessários

Acesse o caminho onde está o projeto no prompt e depois utilize o camando abaixo.

```
pip install -r requirements.txt
```

Caso o comando acima não funciona, executar o comando abaixo:

```
pip install --user -r requirements.txt
```

### 7. Inicie o serviço da API

```
uvicorn api:app --reload
```

### 8. Experimente a API
Abra o seguinte caminho no seu navegador:
* `http://127.0.0.1:8000/docs`
* Clique no endpoint `/predict` e depois em `Try it out` 
* Só preencher os valores desejados das features e clicar em `Execute` 

### 9. Para executar o Web App, abra outro `CMD` dentro do diretório que estão os códigos e execute os comandos abaixo

```
conda activate ambiente_api # ativar o ambiente python
streamlit run web_app.py # executando o streamlit
```

### 10. Abra a página do web app digitando o endereço abaixo no navegador

```
http://127.0.0.1:8501
```

# Tecnologias Utilizadas

1. [Python](https://www.python.org/): linguagem de programação
2. [Colab](https://colab.research.google.com/notebooks/intro.ipynb): ambiente de treinamento de modelos
3. [Anaconda](https://www.anaconda.com/): gerenciamento de ambientes virtuais
4. [Numpy](https://numpy.org/): processamento de dados
5. [Pandas](https://pandas.pydata.org/): processamento de dados
6. [Scikit-learn](https://scikit-learn.org/stable/): machine learning
7. [Pycaret](https://pycaret.org/): machine learning
8. [FastAPI](https://fastapi.tiangolo.com/): construção de APIs
9. [Streamlit](https://streamlit.io/): construção de Web Apps
10. [Git](https://git-scm.com/): versionamento de código
11. [Github](https://github.com/): repositório de código

# Steps para criação da analytical base table e treinamento do modelo (OPCIONAL)
A tabela utilizada para treinar o modelo, também chamada de dataset ou abt (analytical base table) foi criada a partir dos dados transacionais disponibilizados pela Olist. Para replicar o `ETL` reponsável pela criação do dataset de treinamento, realize os seguintes passos:

1. Faça o download das bases da Olist: https://www.kaggle.com/olistbr/brazilian-ecommerce e disponibilize as bases baixadas na pasta `datasets`.
2. Execute o código `notebooks/01_criando_abt.ipynb`. Esse código no final irá criar e disponibilizar a tabela `datasets/propensao_revenda_abt.csv` na pasta `datasets`;
3. Caso queira também realizar o treinamento do modelo, pode executar o notebook em `notebooks/02_model_training.ipynb` que no final irá criar e disponibilizar um modelo em `models/modelo_final.pkl`.
A tabela utilizada para treinar o modelo, também chamada de dataset ou abt (analytical base table) foi criada a partir dos dados transacionais disponibilizados pela Olist. Para replicar o `ETL` reponsável pela criação do dataset de treinamento, realize os seguintes passos:

1. Faça o download das bases da Olist: https://www.kaggle.com/olistbr/brazilian-ecommerce e disponibilize as bases baixadas na pasta `datasets`.
2. Execute o código `notebooks/01_criando_abt.ipynb`. Esse código no final irá criar e disponibilizar a tabela `datasets/propensao_revenda_abt.csv` na pasta `datasets`;
3. Caso queira também realizar o treinamento do modelo, pode executar o notebook em `notebooks/02_model_training.ipynb` que no final irá criar e disponibilizar um modelo em `models/modelo_final.pkl`.

# Dicas
Comandos importantes para o Anaconda Prompt

### listar ambiente
conda info --envs

### desativar ambiente
conda deactivate

### ativar ambiente
conda activate ambiente_api

### remover ambiente
entra no base e remove
conda env remove --name ambiente_api