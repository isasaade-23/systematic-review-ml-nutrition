# 🚀 Guia: Configurar GitHub para a Revisão Sistemática

## Passo 1: Criar Conta no GitHub (se não tiver)
1. Acesse: https://github.com
2. Clique em "Sign up"
3. Use seu email da USP (facilita acesso a recursos acadêmicos)

---

## Passo 2: Criar Repositório

1. Clique no **+** no canto superior direito → "New repository"
2. Configure:
   - **Repository name**: `systematic-review-ml-nutrition`
   - **Description**: `Systematic review: ML for childhood nutritional outcomes`
   - **Visibility**: `Private` (até publicar)
   - ✅ Marque "Add a README file"
   - **Add .gitignore**: Selecione `Python`
   - **License**: Deixe em branco por agora
3. Clique em "Create repository"

---

## Passo 3: Estrutura de Pastas

Crie a seguinte estrutura no repositório:

```
systematic-review-ml-nutrition/
│
├── README.md                    # Descrição do projeto
├── .gitignore                   # Arquivos a ignorar
│
├── data/
│   ├── raw/                     # Dados originais (Excel)
│   │   └── extracao_v2.xlsx
│   └── processed/               # Dados processados
│       └── extraction_clean.xlsx
│
├── notebooks/
│   └── analysis.ipynb           # Notebook de análise
│
├── outputs/
│   ├── tables/                  # Tabelas para publicação
│   │   ├── Table1.xlsx
│   │   └── Table2.xlsx
│   └── figures/                 # Figuras
│       ├── fig1_outcomes.png
│       └── fig2_auc_boxplot.png
│
├── docs/
│   ├── COLUMN_DEFINITIONS.md    # Definições das colunas
│   ├── PROBAST_GUIDE.md         # Guia PROBAST
│   └── manuscript/              # Manuscrito (opcional)
│
└── scripts/                     # Scripts Python (se necessário)
    └── data_processing.py
```

### Como criar pastas no GitHub:
1. Clique em "Add file" → "Create new file"
2. No campo de nome, digite: `data/raw/.gitkeep`
3. Clique em "Commit new file"
4. Repita para outras pastas

---

## Passo 4: Upload de Arquivos

### Via interface web:
1. Navegue até a pasta desejada (ex: `data/raw/`)
2. Clique em "Add file" → "Upload files"
3. Arraste os arquivos
4. Clique em "Commit changes"

### Arquivos para upload:
- `data/raw/extracao_artigo1_v2.xlsx`
- `docs/COLUMN_DEFINITIONS.md`
- `docs/PROBAST_GUIDE.md`
- `notebooks/analysis.ipynb`

---

## Passo 5: Conectar com Google Colab

1. Abra o Google Colab: https://colab.research.google.com
2. Vá em "File" → "Open notebook"
3. Selecione a aba "GitHub"
4. Autorize o acesso ao GitHub
5. Cole a URL do repositório
6. Selecione o notebook `notebooks/analysis.ipynb`

### Alternativa: Clonar o repo no Colab
```python
!git clone https://github.com/SEU_USERNAME/systematic-review-ml-nutrition.git
%cd systematic-review-ml-nutrition
```

---

## Passo 6: Salvar Alterações do Colab no GitHub

### Opção 1: Salvar diretamente
1. No Colab, vá em "File" → "Save a copy in GitHub"
2. Selecione o repositório e branch
3. Clique em "OK"

### Opção 2: Download e upload manual
1. No Colab: "File" → "Download" → "Download .ipynb"
2. No GitHub: Upload na pasta `notebooks/`

---

## README.md Sugerido

```markdown
# Systematic Review: ML for Childhood Nutritional Outcomes

## Overview
Systematic review following PRISMA 2020 guidelines examining machine learning applications for predicting nutritional outcomes in children aged 0-11 years.

## Outcomes
- Stunting (HAZ < -2 SD)
- Underweight (WAZ < -2 SD)
- Overweight (BAZ > +2 SD)
- Obesity (BAZ > +3 SD)

## Structure
- `/data/` - Extraction spreadsheets
- `/notebooks/` - Analysis notebooks
- `/outputs/` - Tables and figures
- `/docs/` - Documentation

## Authors
- [Your name] - PhD Student, USP

## Status
🔄 In progress

## Registration
PROSPERO: [Number TBD]
```

---

## Checklist Final

- [ ] Criar conta GitHub
- [ ] Criar repositório privado
- [ ] Criar estrutura de pastas
- [ ] Upload do Excel de extração
- [ ] Upload dos documentos (COLUMN_DEFINITIONS, PROBAST_GUIDE)
- [ ] Upload do notebook
- [ ] Testar abertura no Colab
- [ ] Atualizar README

---

## Dúvidas Comuns

**P: Posso deixar o repo público?**
R: Só depois de publicar. Dados de revisão podem ter restrições.

**P: Como compartilhar com colaboradores?**
R: Settings → Collaborators → Add people (pelo username/email)

**P: E se eu errar algo?**
R: GitHub mantém histórico. Você pode reverter qualquer alteração.

---

**Precisa de ajuda?** Me mande uma mensagem!
