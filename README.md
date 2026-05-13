# 📊 Análise de Evasão de Clientes — Telecom X

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c72b0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![Challenge](https://img.shields.io/badge/ONE-Oracle%20Next%20Education%20G9-red?logo=oracle&logoColor=white)

---

## 🧭 Sobre o Projeto

A **Telecom X** é uma operadora fictícia que enfrenta um problema clássico — e caro — do setor: clientes cancelando o serviço em uma taxa alta demais para ignorar. A pergunta que a diretoria fez para o time de dados foi simples: **quem está saindo, em que momento, e por quê?**

Esse projeto foi a minha resposta. Peguei os dados brutos de uma API, limpei, traduzi, organizei e fui atrás dos padrões. O resultado é um diagnóstico completo sobre o churn da empresa e cinco recomendações estratégicas para reduzi-lo.

Foi desenvolvido como **Challenge de Data Science** do programa [ONE — Oracle Next Education G9](https://www.oracle.com/br/education/oracle-next-education/) da [Alura](https://www.alura.com.br/).

---

## 🎯 O Problema de Negócio

> 📌 **Como reduzir a taxa de cancelamento da Telecom X identificando os perfis e momentos de maior risco?**

Para responder isso, eu precisei:

- Entender quem cancela (perfil demográfico, tipo de plano, forma de pagamento)
- Identificar **quando** o cancelamento acontece (tempo de contrato)
- Descobrir **por que** acontece (variáveis associadas ao churn)
- Traduzir tudo em recomendações que o time de retenção possa executar

---

## 📂 Os Dados

Os dados foram consumidos diretamente via API pública da Alura, em formato JSON aninhado:

```
https://raw.githubusercontent.com/alura-cursos/challenge2-data-science/refs/heads/main/TelecomX_Data.json
```

Cada registro representa um cliente, com informações sobre:

- **Perfil:** gênero, idade (sênior ou não), dependentes, parceiro
- **Conta:** tipo de contrato, forma de pagamento, fatura digital, cobrança mensal e total
- **Serviços:** telefonia, internet (DSL/fibra), backup, suporte técnico, streaming
- **Comportamento:** tempo de permanência (tenure) e status de evasão (churn)

---

## 🔄 Pipeline da Análise

```
🌐 API JSON (aninhada)
        │
        ▼
📥 EXTRAÇÃO
   pd.json_normalize() para achatar a estrutura
        │
        ▼
🔧 TRANSFORMAÇÃO
   Limpeza · Conversão de tipos · Padronização
   Tradução PT-BR · Tratamento de nulos
        │
        ▼
📊 ANÁLISE EXPLORATÓRIA
   Análise univariada · Crosstabs · Correlações
   Visualizações por variável e por segmento
        │
        ▼
💡 INSIGHTS & RECOMENDAÇÕES
```

---

## 📈 Principais Descobertas

### 1. Aproximadamente **1 em cada 4 clientes** cancela

![Distribuição da Evasão de Clientes](distribuicao%20da%20evasao%20de%20clientes.png)

A taxa de churn da base é de **26,6%**. Para uma operadora de telecom, isso é dinheiro saindo pela porta todo mês — e cada cancelamento custa mais do que reter.

---

### 2. O **primeiro mês** é decisivo

![Taxa de Evasão ao Longo do Tempo](taxa%20de%20evasao%20ao%20longo%20do%20tempo.png)

Mais de **60% dos clientes** que cancelam fazem isso logo nos primeiros meses de contrato. Depois desse período crítico, a curva cai e estabiliza. Isso é a chamada *cliff de retenção*: se você não fideliza no início, perde.

---

### 3. Contrato mensal é a maior bandeira vermelha

![Evasão por Tipo de Contrato](evasao%20por%20tipo%20do%20contrato.png)

A diferença é gritante:

| Tipo de contrato | Taxa de churn |
|---|---|
| Mensal | **~42%** |
| Anual | ~11% |
| Bienal | **~3%** |

Clientes com contrato bienal são **14× mais leais** que os mensais. O contrato em si é uma forma de retenção.

---

### 4. Fibra óptica tem churn proporcionalmente alto

![Evasão por Tipo de Internet](evasao%20por%20tipo%20de%20internet.png)

Aqui veio o resultado contraintuitivo da análise. A fibra deveria ser o produto premium — e é o que tem proporcionalmente **mais cancelamentos**. Isso aponta para uma possível dor de **qualidade percebida** ou **expectativa não atendida** entre quem paga mais caro.

---

### 5. Quem cancela paga mais

![Evasão vs Cobrança Mensal](evasao%20vs%20cobranca%20mensal.png)

A média de cobrança mensal de quem cancela é **significativamente mais alta** que a média de quem fica. Combinado com o insight anterior, isso sugere que o problema não é só preço — é **custo-benefício percebido**.

---

### 6. Gênero **não é** fator relevante

![Evasão por Variáveis Categóricas](evasao%20por%20variaveis%20categoricas.png)

Importante separar o sinal do ruído: a distribuição de churn entre homens e mulheres é praticamente idêntica. Não é por aí que vale segmentar campanhas.

---

## 💡 Recomendações Estratégicas

Com base nas descobertas acima, propus 5 ações priorizadas:

| Prioridade | Ação | Por quê |
|---|---|---|
| 🥇 Alta | **Onboarding ativo nos primeiros 90 dias** | É onde 60%+ do churn acontece |
| 🥈 Alta | **Migrar mensais para anuais/bienais** com desconto | Reduz churn de 42% para 3-11% |
| 🥉 Média | **Investigar qualidade da fibra óptica** | Produto premium não pode ter o pior churn |
| 4 | **Revisar precificação** dos planos mais caros | Cancelamentos concentrados na faixa alta de cobrança |
| 5 | **Modelo preditivo de churn** | Antecipar o cancelamento usando os padrões encontrados |

---

## 🧠 O Que Aprendi

- **JSON aninhado é o normal, não a exceção.** O `pd.json_normalize()` virou uma das funções que mais uso depois desse projeto.
- **Crosstab é uma das ferramentas mais subestimadas do Pandas.** Para comparar taxas entre segmentos categóricos, não tem nada melhor.
- **Nem todo insight é insight.** A não-correlação com gênero é tão útil quanto a correlação com contrato — evita que o time gaste verba em segmentações que não vão mover o ponteiro.
- **Visualização não é decoração.** É argumentação. Cada gráfico aqui responde a uma pergunta específica.

---

## 🚧 Desafios

- **Achatar a estrutura JSON** sem perder informação — algumas chaves tinham subobjetos com 5+ campos.
- **Padronizar valores categóricos** em português, preservando comparabilidade.
- **Tratar `Total` como numérico** quando vinha como string (com espaços e vírgulas).
- **Decidir o que era *significativo*** estatisticamente versus o que era ruído da amostra.

---

## 🛠 Tecnologias

| Ferramenta | Uso |
|---|---|
| **Python 3.10** | Linguagem principal |
| **Pandas** | Manipulação, agregação e crosstabs |
| **Matplotlib & Seaborn** | Visualizações estatísticas |
| **Requests** | Consumo da API |
| **Google Colab** | Ambiente de desenvolvimento |

---

## 📂 Estrutura do Repositório

```
📦 Analise_evasao_TelecomX
 ┣ 📓 Análise_Evasão_TelecomX_FINAL.ipynb   <- Notebook principal (ETL + EDA)
 ┣ 🖼️  distribuicao da evasao de clientes.png
 ┣ 🖼️  evasao por contrato.png
 ┣ 🖼️  evasao por tipo de internet.png
 ┣ 🖼️  evasao por tipo do contrato.png
 ┣ 🖼️  evasao por variaveis categoricas.png
 ┣ 🖼️  evasao vs cobranca mensal.png
 ┣ 🖼️  taxa de evasao ao longo do tempo.png
 ┗ 📄 README.md
```

---

## ▶️ Como Executar

```bash
# 1. Clone o repositório
git clone https://github.com/danielli-arcari/Analise_evasao_TelecomX.git
cd Analise_evasao_TelecomX

# 2. Instale as dependências
pip install pandas matplotlib seaborn requests

# 3. Abra o notebook
jupyter notebook Análise_Evasão_TelecomX_FINAL.ipynb
```

Ou abra diretamente no **Google Colab** fazendo upload do `.ipynb`.

---

## 📎 Apresentação

A versão executiva do projeto, com slides, está em:

🔗 [Análise de Evasão de Clientes — Telecom X (Gamma)](https://gamma.app/docs/Analise-de-Evasao-de-Clientes--jing6hxmkoou32u)

---

## 👩‍💻 Autora

**Danielli Meilene Coutinho Arçari**

Graduanda em Ciência da Computação (UNINTER) em transição para a área de Dados. Apaixonada por transformar números em narrativas que orientam decisões.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/danielli-arcari/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/danielli-arcari)
[![Portfólio](https://img.shields.io/badge/Portf%C3%B3lio-Vercel-black?style=flat&logo=vercel&logoColor=white)](https://danielliarcari.vercel.app/)

---

*Projeto desenvolvido no âmbito do programa **ONE — Oracle Next Education G9** em parceria com a Alura.*
