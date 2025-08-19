
# 📊 Previsão de Evasão de Clientes - Telecom X

Este projeto tem como objetivo prever a evasão de clientes (churn) da empresa fictícia **Telecom X**, utilizando técnicas de Machine Learning e análise de dados.

---

## 🧠 Desafio

Após uma análise exploratória bem-sucedida na Parte 1, o desafio agora é construir modelos preditivos capazes de identificar clientes com maior probabilidade de cancelar seus serviços.

---

## 🔧 Etapas do Projeto

1. **Importação e Exploração dos Dados**
   - Carregamento do arquivo `dados_tratados.csv` com dados limpos e padronizados.
   - Verificação de tipos de dados, valores nulos e estatísticas básicas.

2. **Pré-processamento**
   - Remoção de colunas irrelevantes (`customerID`, `genero`, `telefone_ativo`, `multiplas_linhas`, `tipo_internet`).
   - Codificação de variáveis categóricas com One-Hot Encoding.
   - Normalização com MinMaxScaler e padronização com StandardScaler.

3. **Análise de Correlação**
   - Identificação de variáveis com maior correlação com a evasão (`cancelou`), como `valor_diario`, `mensalidade`, `tipo_contrato`, `tempo_cliente_meses`.

4. **Balanceamento de Classes**
   - Aplicação de SMOTE para equilibrar as classes `cancelou` (0, 1, 2).

5. **Modelagem Preditiva**
   - Modelo 1: Regressão Logística (com normalização).
   - Modelo 2: Random Forest (sem normalização).

6. **Avaliação dos Modelos**
   - Métricas: Acurácia, Precisão, Recall, F1-score, Matriz de Confusão.
   - Visualizações: Boxplots, Scatter plots, Heatmaps de correlação.

---

## 🤖 Modelos Utilizados

### 🔹 Regressão Logística
- **Justificativa**: Modelo linear, sensível à escala, útil para interpretação de variáveis.
- **Pré-processamento**: Normalização com MinMaxScaler.
- **Resultado**:
  - Acurácia: 77.7%
  - Classe 0: Excelente desempenho
  - Classe 2: Razoável
  - Classe 1: Não prevista

### 🔹 Random Forest
- **Justificativa**: Modelo baseado em árvore, robusto e não sensível à escala.
- **Pré-processamento**: Dados originais sem normalização.
- **Resultado**:
  - Acurácia: 75.2%
  - Classe 0: Forte desempenho
  - Classe 2: Moderado
  - Classe 1: Não prevista

---

## 📈 Análise Comparativa

| Métrica       | Regressão Logística | Random Forest |
|---------------|---------------------|----------------|
| Acurácia      | 77.7%               | 75.2%          |
| Classe 0      | Precision: 0.82 / Recall: 0.90 | Precision: 0.82 / Recall: 0.87 |
| Classe 1      | Não prevista        | Não prevista   |
| Classe 2      | Precision: 0.61 / Recall: 0.52 | Precision: 0.58 / Recall: 0.50 |

- Ambos os modelos falharam em prever a classe 1, indicando possível underfitting ou necessidade de redefinição da classe.
- Regressão Logística teve melhor desempenho geral, mas Random Forest foi mais equilibrado.

---

## 📌 Conclusão

- Variáveis como `valor_diario`, `mensalidade`, `tipo_contrato` e `tempo_cliente_meses` são fortes influenciadoras da evasão.
- O balanceamento com SMOTE foi essencial para melhorar a representatividade das classes.
- A combinação de modelos com e sem normalização permite avaliar diferentes abordagens e melhorar a robustez da solução.

---

## 🚀 Próximos Passos

- Testar modelos mais avançados como XGBoost ou LightGBM.
- Ajustar hiperparâmetros para melhorar recall da classe 1.
- Gerar relatório final com insights estratégicos para retenção de clientes.

