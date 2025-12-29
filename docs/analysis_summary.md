# 📊 RESUMO DA ANÁLISE - Systematic Review ML + Childhood Nutrition

**Data**: 29/12/2024  
**Arquivo analisado**: `extracao_artigo1_v2.xlsx`

---

## 📈 NÚMEROS GERAIS

| Métrica | Valor |
|---------|-------|
| Total de linhas (artigos × outcomes) | 62 |
| Artigos únicos | 52 |
| Artigos com múltiplos outcomes | 10 |
| Artigos faltando | 1 (AA_31) |

---

## 🎯 DISTRIBUIÇÃO POR OUTCOME

| Outcome | N | % |
|---------|---|---|
| **Stunting** | 32 | 51.6% |
| **Obesity** | 9 | 14.5% |
| **Underweight** | 7 | 11.3% |
| **Overweight** | 5 | 8.1% |
| Wasting (EXCLUIR) | 2 | 3.2% |
| Malnutrition genérico (REVISAR) | 2 | 3.2% |

### ⚠️ Ação necessária:
- **EXCLUIR**: AA_08, AA_09 (wasting)
- **REVISAR**: AA_10, AA_12 (outcome genérico "malnutrition")

---

## 🌍 DISTRIBUIÇÃO GEOGRÁFICA

| País | N | % |
|------|---|---|
| Indonesia | 23 | 37.1% |
| China | 5 | 8.1% |
| Bangladesh | 5 | 8.1% |
| India | 4 | 6.5% |
| Morocco | 4 | 6.5% |
| Outros | 21 | 33.9% |

---

## 🤖 ALGORITMOS MAIS USADOS

| Algoritmo | N | % |
|-----------|---|---|
| Random Forest | 19 | 30.6% |
| XGBoost | 6 | 9.7% |
| Gradient Boosting | 4 | 6.5% |
| Logistic Regression | 4 | 6.5% |
| Neural Networks (DNN/LSTM/ANN) | 4 | 6.5% |
| Outros | 25 | 40.3% |

---

## ⚠️ PROBAST - RISK OF BIAS

| Rating | N | % |
|--------|---|---|
| **HIGH** | 51 | 82.3% |
| LOW | 1 | 1.6% |
| Unclear | 1 | 1.6% |
| *Missing* | 9 | 14.5% |

### Validação Externa
| Status | N | % |
|--------|---|---|
| **No** | 50 | 94.3% |
| Yes | 3 | 5.7% |

---

## 📈 PERFORMANCE (AUC)

| Outcome | N com AUC | Range | Mediana |
|---------|-----------|-------|---------|
| Stunting | ~18 | 0.50 - 1.00 | 0.72 |
| Underweight | ~4 | 0.64 - 1.00 | 0.76 |
| Overweight | ~3 | 0.62 - 0.81 | 0.66 |
| Obesity | ~6 | 0.65 - 0.96 | 0.81 |

### ⚠️ AUC Suspeitos:
- **AA_02**: AUC = 1.00 (Stunting e Underweight) → DATA LEAKAGE confirmado

---

## 🚨 DATA LEAKAGE IDENTIFICADO

### Problema crítico: **30 linhas** (~48%) têm data leakage

| Tipo de Leakage | Artigos Afetados |
|-----------------|------------------|
| HEIGHT → Stunting | AA_02, AA_03, AA_04, AA_13, AA_19, AA_20, AA_21, AA_22, AA_23, AA_26, AA_27, AA_28, AA_30, AA_35, AA_37, AA_39, AA_40, AA_41, AA_46, AA_47, AA_52 |
| WEIGHT → Underweight | AA_01, AA_02, AA_52 |
| BMI → Obesity/Overweight | AA_07, AA_17, AA_32, AA_33, AA_50 |

### Implicações:
1. Estes modelos **não têm utilidade clínica** - estão usando o próprio outcome como preditor
2. Métricas de performance **artificialmente infladas**
3. Deve ser **reportado como limitação crítica** no manuscrito
4. Considerar **análise separada** excluindo estudos com leakage

---

## 📋 PRÓXIMOS PASSOS

### 1. Limpeza de Dados
- [ ] Remover AA_08, AA_09 (wasting)
- [ ] Decidir sobre AA_10, AA_12 (outcome genérico)
- [ ] Localizar AA_31 (faltando)

### 2. Análises Necessárias
- [ ] Tabela 1: Características dos estudos
- [ ] Tabela 2: Performance por outcome
- [ ] Tabela 3: PROBAST summary
- [ ] Tabela 4: Top predictors
- [ ] Análise separada: COM vs SEM data leakage

### 3. Figuras
- [ ] PRISMA flow diagram
- [ ] Forest plot AUC por outcome
- [ ] PROBAST traffic light
- [ ] Mapa geográfico

### 4. GitHub Setup
- [ ] Criar repositório
- [ ] Estrutura de pastas
- [ ] Notebooks Colab
- [ ] README

---

## 📁 O QUE VOCÊ PRECISA ME ENVIAR

1. **Confirmar números PRISMA**:
   - Registros identificados (por base)
   - Duplicatas removidas
   - Excluídos título/abstract
   - Excluídos full-text (com motivos)

2. **Data final da busca** (para inserir no manuscrito)

3. **Número PROSPERO** (quando disponível)

4. **Decisão sobre**:
   - AA_10, AA_12 (manter ou excluir?)
   - AA_31 (localizar ou confirmar exclusão?)

---

*Gerado automaticamente em 29/12/2024*
