# 📊 Análise de Evasão de Clientes — Telecom X

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c72b0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![Challenge](https://img.shields.io/badge/ONE-Oracle%20Next%20Education%20G9-red?logo=oracle&logoColor=white)

---

## 🗂 Sobre o Projeto

Este projeto foi desenvolvido como parte do **Challenge de Data Science** do programa **ONE Oracle Next Education G9** da [Alura](https://www.alura.com.br/).

O objetivo é analisar os fatores que influenciam a **evasão de clientes (churn)** na empresa fictícia **Telecom X**, que enfrenta um alto índice de cancelamentos e precisa entender os principais motivos que levam seus clientes a encerrar os serviços.

A análise passa por um pipeline completo de **ETL + EDA**, culminando em insights e recomendações estratégicas baseadas em dados.

---

## 🎯 Objetivos

- Extrair e tratar dados brutos obtidos via API
- Identificar padrões de comportamento associados ao churn
- Visualizar as principais variáveis que influenciam a evasão
- Propor recomendações estratégicas para redução do churn

---

## 📎 Apresentação

Acesse a apresentação completa do projeto no Gamma:

🔗 [Análise de Evasão de Clientes — Telecom X](https://gamma.app/docs/Analise-de-Evasao-de-Clientes--jing6hxmkoou32u)

---

## 🗃 Estrutura do Projeto

```
📦 TelecomX-Churn-Analysis
 ┣ 📓 Análise_Evasão_TelecomX_FINAL.ipynb   # Notebook principal com ETL + EDA
 ┣ 📊 distribuicao_da_evasao_de_clientes.png
 ┣ 📊 evasao_por_contrato.png
 ┣ 📊 evasao_por_tipo_de_internet.png
 ┣ 📊 evasao_por_tipo_do_contrato.png
 ┣ 📊 evasao_por_variaveis_categoricas.png
 ┣ 📊 evasao_vs_cobranca_mensal.png
 ┣ 📊 taxa_de_evasao_ao_longo_do_tempo.png
 ┗ 📄 README.md
```

---

## 🔄 Pipeline de Análise

```
API (JSON)
   │
   ▼
📥 EXTRAÇÃO
   │  pd.json_normalize()
   ▼
🔧 TRANSFORMAÇÃO
   │  Limpeza · Tipagem · Padronização · Tradução
   ▼
📦 CARGA
   │  Análise Descritiva · Visualizações · Crosstabs
   ▼
💡 INSIGHTS & RECOMENDAÇÕES
```

---

## 📈 Principais Insights

| # | Insight |
|---|---------|
| 1 | **26,6%** dos clientes cancelaram o serviço — aproximadamente 1 em cada 4 |
| 2 | A taxa de evasão chega a **+60%** no primeiro mês de contrato |
| 3 | Clientes com **contrato mensal** têm churn ~42% vs ~3% nos bienais |
| 4 | Clientes com **internet fibra** apresentam proporção de evasão significativamente maior |
| 5 | Clientes que cancelaram pagam, em média, **mensalidades mais altas** |
| 6 | **Gênero** não é um fator determinante para a evasão |

---

## 💡 Recomendações Estratégicas

1. 🎯 **Onboarding ativo nos primeiros meses** — acompanhar e engajar clientes novos
2. 📅 **Incentivar contratos anuais e bienais** — descontos e benefícios para migração
3. 💰 **Revisar precificação** — avaliar custo-benefício dos planos mais caros
4. 🔍 **Investigar a fibra óptica** — pesquisar satisfação dos usuários
5. 🤖 **Modelo preditivo de churn** — usar os padrões encontrados para antecipar cancelamentos

---

## 🛠 Tecnologias Utilizadas

| Ferramenta | Uso |
|---|---|
| Python 3.10 | Linguagem principal |
| Pandas | Manipulação e análise de dados |
| Matplotlib | Visualizações estáticas |
| Seaborn | Visualizações estatísticas |
| Requests | Extração de dados via API |
| Google Colab | Ambiente de desenvolvimento |

---

## ▶️ Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/telecomx-churn-analysis.git
```

2. Instale as dependências:
```bash
pip install pandas matplotlib seaborn requests
```

3. Abra o notebook:
```bash
jupyter notebook Análise_Evasão_TelecomX_FINAL.ipynb
```

Ou acesse diretamente pelo **Google Colab** fazendo upload do `.ipynb`.

---

## 📡 Fonte dos Dados

Os dados foram obtidos via API pública disponibilizada pela Alura para o Challenge:

```
https://raw.githubusercontent.com/alura-cursos/challenge2-data-science/refs/heads/main/TelecomX_Data.json
```

---

## 👩‍💻 Autora

Desenvolvido como parte do **Challenge Data Science — ONE Oracle Next Education G9**

[![Alura](https://img.shields.io/badge/Alura-ONE%20G9-blue?logo=alura)](https://www.alura.com.br/)
[![Oracle](https://img.shields.io/badge/Oracle-Next%20Education-red?logo=oracle)](https://www.oracle.com/br/education/oracle-next-education/)
