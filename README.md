# Road Traffic Flow Prediction – Porto (Group 37)

Este repositório contém o trabalho prático desenvolvido na unidade curricular de **Dados e Aprendizagem Automática** (DAA), no Mestrado em Engenharia e Ciência de Dados da Universidade do Minho (2025/2026).

O projeto foca-se na previsão de níveis de congestionamento de trânsito na cidade do Porto, utilizando técnicas de exploração de dados, engenharia de atributos e modelos de aprendizagem supervisionada.

## 🏆 Resultados e Performance
* **Nota Final:** 19,5 valores.
* **Ranking Kaggle:** 5º lugar no dataset privado.
* **Modelo Final:** XGBoost (Otimizado).
* **Accuracy Final:** ~0.812 no dataset privado (subida de posição face ao leaderboard público).

## 📋 Descrição do Problema
O objetivo é prever a variável `average_speed_diff`, que classifica o tráfego em 5 níveis: `None`, `Low`, `Medium`, `High` e `Very High`. Trata-se de um problema de **classificação multiclasse** com um dataset desbalanceado.

## 🛠️ Pipeline de Desenvolvimento

### 1. Exploração e Tratamento de Dados (EDA)
* **Missing Values:** Tratamento de ~91% de valores nulos em `average_rain`, convertidos para uma escala de intensidade.
* **Limpeza:** Remoção de colunas redundantes ou constantes como `city_name` e `average_precipitation`.

### 2. Feature Engineering (O Fator Diferenciador)
Para melhorar a performance do modelo, foram criadas variáveis específicas de contexto:
* **Tempo Cíclico:** Transformação de horas e meses em componentes seno e cosseno.
* **Eventos Locais:** Flags para feriados, fins de semana, períodos escolares e eventos de grande afluência no Porto (São João, Queima das Fitas, jogos no Estádio do Dragão).
* **Métricas de Tráfego:** Cálculo do `congestion_ratio`.
* **Meteorologia:** Cálculo do *Dew Point* (Ponto de Orvalho).

### 3. Modelação
Foram testados vários algoritmos, incluindo Decision Trees, Random Forest e Redes Neuronais (MLP). O modelo que apresentou maior robustez foi o **XGBoost**.

**Hiperparâmetros Otimizados:**
* `learning_rate`: 0.03
* `n_estimators`: 700
* `max_depth`: 3
* `min_child_weight`: 3

## 📊 Conclusões
A estratégia de focar no contexto temporal e em eventos específicos da cidade do Porto permitiu ao modelo generalizar melhor do que modelos mais complexos mas menos contextualizados. A subida de posição no ranking privado demonstra a ausência de *overfitting*.

## 👥 Autores (Grupo 37)
* **Beatriz Peixoto** (pg59996)
* **Diogo Miranda** (pg60001)
* **Martim Félix** (pg58753)
* **Sandra Cerqueira** (pg60016)

---
*Trabalho realizado no âmbito do MECD - Universidade do Minho.*
