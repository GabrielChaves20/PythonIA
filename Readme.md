
# 🔍 Previsão de Score de Crédito com Machine Learning

Este projeto utiliza **Python** e a biblioteca **Scikit-learn** para treinar um modelo de aprendizado de máquina que prevê a classificação do **score de crédito** de clientes com base em características como profissão, mix de crédito e comportamento de pagamento.

## 🧠 Objetivo

Construir um modelo de IA capaz de prever se o **score de crédito** de um cliente será **Ruim**, **Médio** ou **Bom**, com base em dados históricos. Isso pode ser útil para instituições financeiras, fintechs ou e-commerces na tomada de decisões sobre concessão de crédito.

---

## 📁 Estrutura do Projeto

```
├── clientes.csv              # Base de dados com clientes existentes e score conhecido
├── novos_clientes.csv       # Base de dados com novos clientes para previsão
├── inicial.ipynb            # Script com todo o pipeline de machine learning
├── README.md                 # Documentação do projeto
```

---

## 📦 Requisitos

- Python 3.7+
- pandas
- scikit-learn

### Instalação das dependências

Você pode instalar os pacotes necessários com:

```bash
pip install pandas scikit-learn
```

---

## 🧪 Etapas do Projeto

### 1. 📥 Importação dos Dados

Os dados são carregados usando `pandas` a partir de dois arquivos:

- `clientes.csv`: utilizado para treinar e testar o modelo.
- `novos_clientes.csv`: utilizado para prever o score com o modelo treinado.

### 2. 🧹 Pré-processamento

- **Label Encoding** nas colunas categóricas: `profissao`, `mix_credito`, `comportamento_pagamento`.
- Remoção da coluna `id_cliente` (não relevante para o modelo).
- Separação entre `X` (features) e `y` (target).

### 3. 🧠 Treinamento dos Modelos

Dois algoritmos foram testados:

- **Random Forest Classifier** 🌲
- **K-Nearest Neighbors (KNN)**

Ambos foram treinados com os dados processados.

### 4. ✅ Avaliação

Foi usada a métrica de **acurácia** para avaliar o desempenho. O modelo Random Forest teve melhor desempenho:

```
Árvore de decisão: 82.87%
Nearest Neighbors: 74.20%
```

### 5. 🔮 Previsão com Novos Dados

O modelo de Random Forest foi utilizado para prever o score de crédito dos clientes em `novos_clientes.csv`.

---

## 📊 Exemplo de Saída

```bash
Árvore de decisão: 82.87%
Nearest Neighbors: 74.20%
[2 1 0 2 1]
```

*Legenda:*
- `Poor` = Ruim
- `Standart` = Médio
- `Good` = Bom

---

## ⚠️ Observações Importantes

- O `LabelEncoder` foi aplicado separadamente nos dados de treino e de teste, o que pode causar inconsistências. Em produção, recomenda-se **usar o mesmo encoder treinado** nos dados originais.
- O projeto não inclui validação cruzada nem ajuste de hiperparâmetros (tuning), mas isso pode ser facilmente adicionado.

---

## 🚀 Próximos Passos

- Adicionar pipeline com `ColumnTransformer` e `OneHotEncoder`.
- Usar `GridSearchCV` para melhorar o desempenho do modelo.
- Implementar uma interface com Streamlit ou Flask para uso interativo.

---

## 👨‍💻 Autor

**Gabriel Chaves**  
📧 gabrielbsc0720@gmail.com  
🔗 [LinkedIn](www.linkedin.com/in/gabriel-borges-ch)

---

## 📄 Licença

Este projeto está licenciado sob a **MIT License**.
