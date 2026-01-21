# Previsão de Custos Médicos com Machine Learning

Projeto de Machine Learning para prever custos médicos individuais utilizando técnicas de regressão.

## 📋 Descrição do Projeto

Este projeto implementa e compara dois modelos de regressão para prever custos médicos (`charges`) com base em características demográficas e de estilo de vida dos pacientes. O objetivo é identificar os principais fatores que influenciam os custos de saúde e desenvolver um modelo preditivo preciso.

## 🎯 Objetivos

- Explorar e analisar dados de custos médicos
- Identificar fatores determinantes nos custos de saúde
- Implementar e comparar modelos de regressão
- Avaliar o desempenho dos modelos usando métricas apropriadas

## 📊 Dataset

O dataset contém **1.338 registros** com as seguintes variáveis:

### Variáveis Independentes (Features)
- **age**: Idade do beneficiário
- **sex**: Sexo do beneficiário (female/male)
- **bmi**: Índice de Massa Corporal (Body Mass Index)
- **children**: Número de filhos/dependentes cobertos pelo seguro
- **smoker**: Status de fumante (yes/no)
- **region**: Região residencial nos EUA (northeast, northwest, southeast, southwest)

### Variável Dependente (Target)
- **charges**: Custos médicos individuais faturados pelo seguro de saúde

## 🔧 Tecnologias Utilizadas

- **Python 3.x**
- **Pandas**: Manipulação e análise de dados
- **NumPy**: Computação numérica
- **Matplotlib & Seaborn**: Visualização de dados
- **Scikit-learn**: Modelagem e avaliação de machine learning

## 📁 Estrutura do Projeto

```
Machine_Learning - projeto_2/
│
├── data/
│   └── custo_medico.csv          # Dataset original
│
├── projeto_2_custo_medico.ipynb  # Notebook principal com análise completa
└── README.md                      # Este arquivo
```

## 🚀 Como Executar

1. **Clone o repositório**
   ```bash
   git clone <url-do-repositorio>
   cd "Machine_Learning - projeto_2"
   ```

2. **Instale as dependências**
   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn
   ```

3. **Execute o notebook**
   ```bash
   jupyter notebook projeto_2_custo_medico.ipynb
   ```

## 📈 Metodologia

### 1. Exploração Inicial
- Carregamento e inspeção dos dados
- Identificação de variáveis numéricas e categóricas
- Análise de estatísticas descritivas

### 2. Análise Exploratória (EDA)
- Visualização da relação entre idade e custos
- Análise da influência do IMC nos custos
- Comparação de custos entre fumantes e não fumantes
- Identificação de padrões e correlações

### 3. Pré-processamento
- **Encoding**: Transformação de variáveis categóricas usando One-Hot Encoding
- **Divisão dos dados**: 80% treino / 20% teste
- **Padronização**: Normalização das variáveis numéricas (age, bmi, children)

### 4. Modelagem
Dois modelos foram implementados e comparados:

#### 4.1 Regressão Linear
- Modelo baseline para estabelecer performance mínima
- Assume relações lineares entre features e target

#### 4.2 Random Forest Regressor
- Modelo ensemble baseado em árvores de decisão
- Capaz de capturar relações não-lineares

### 5. Avaliação
Métricas utilizadas:
- **MAE** (Mean Absolute Error): Erro médio absoluto
- **RMSE** (Root Mean Squared Error): Raiz do erro quadrático médio
- **R²** (Coefficient of Determination): Proporção da variância explicada

## 📊 Resultados

| Modelo              | MAE      | RMSE     | R²     |
|---------------------|----------|----------|--------|
| Linear Regression   | 4181.19  | 5796.28  | 0.7836 |
| **Random Forest**   | **2543.98** | **4567.78** | **0.8656** |

### Principais Descobertas

1. **Tabagismo é o fator mais determinante**: Fumantes apresentam custos médicos significativamente mais altos
2. **Idade influencia positivamente**: Custos tendem a aumentar com a idade, especialmente para fumantes
3. **IMC tem impacto moderado**: Índice de massa corporal mostra correlação com custos
4. **Random Forest supera Regressão Linear**: O modelo ensemble capturou melhor as relações não-lineares, explicando 86.5% da variância dos custos

### Importância das Features (Random Forest)
O modelo identificou as seguintes features como mais importantes (em ordem decrescente):
1. Smoker (Fumante)
2. Age (Idade)
3. BMI (IMC)
4. Children (Número de filhos)
5. Demais variáveis regionais e de sexo

## ⚠️ Limitações

- **Tamanho do dataset**: Conjunto relativamente pequeno (1.338 registros) pode limitar a generalização
- **Features limitadas**: Não considera fatores como histórico familiar, doenças preexistentes ou outros hábitos de vida
- **Granularidade geográfica**: A variável `region` é muito ampla e não captura diferenças locais de custo
- **Dados temporais**: Não há informação sobre quando os custos foram incorridos (inflação médica)

## 🔮 Melhorias Futuras

- [ ] Incluir mais features clínicas (pressão arterial, colesterol, glicemia)
- [ ] Adicionar dados de estilo de vida (exercícios, dieta, consumo de álcool)
- [ ] Implementar técnicas de feature engineering
- [ ] Testar outros algoritmos (XGBoost, LightGBM, Redes Neurais)
- [ ] Realizar tuning de hiperparâmetros com GridSearch/RandomSearch
- [ ] Implementar validação cruzada para avaliação mais robusta
- [ ] Criar uma API para servir o modelo em produção

## 👨‍💻 Autor

Projeto desenvolvido por Lucas para fins de estudo e aprendizado.

## 📄 Licença

Este projeto é de código aberto e está disponível para fins educacionais.

---

**Nota**: Este projeto foi desenvolvido com fins educacionais e não deve ser utilizado para decisões médicas ou de seguros reais.
