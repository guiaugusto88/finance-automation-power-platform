# 📊 Automação de Gestão Financeira End-to-End (Power Platform)

Este projeto demonstra a criação de uma solução completa de **Arquitetura de Dados e BI**, integrando entrada de dados móvel, processamento em nuvem e visualização de KPIs em tempo real. A solução foi desenhada para eliminar o trabalho manual de preenchimento e centralizar a gestão de ativos e despesas.

---

## 🛠️ Stack Tecnológico

* **Engine de Automação:** [Power Automate](https://powerautomate.microsoft.com/)
* **Business Intelligence:** [Power BI Service & Desktop](https://powerbi.microsoft.com/)
* **Banco de Dados/Storage:** Excel Online (OneDrive for Business)
* **Interface de Usuário:** Power Automate Mobile App

---

## 🏗️ Arquitetura da Solução

O projeto segue um fluxo de dados **ETL (Extract, Transform, Load)** simplificado e eficiente:

1.  **Input (Smartphone):** Registro de dados através do app do Power Automate. Utilização de campos opcionais para tratar dados heterogêneos (ex: Ativos de Investimento vs. Despesas Fixas).
2.  **Processamento (Cloud):** O fluxo executa a lógica de inserção na tabela do Excel Online e dispara um trigger de atualização (API) para o Power BI.
3.  **Analytics (Power BI):** Modelagem de dados com **DAX** para cálculo de metas e visualização de performance via Scorecards e Gráficos de Gauge.

---

## ⚙️ Lógica da Automação (Power Automate)

Fluxo automatizado responsável por registrar e processar os dados financeiros:

1. Gatilho manual via aplicativo mobile
2. Coleta de dados inseridos pelo usuário (valor, categoria, data)
3. Validação dos campos obrigatórios
4. Inserção automática em tabela no Excel Online
5. Atualização dos dados para consumo no Power BI

### Estrutura do Fluxo

Trigger: "Disparar um fluxo manualmente"
↓
Ação: "Adicionar uma linha em uma tabela (Excel Online)"
↓
Conexão com OneDrive for Business

---

## 🎯 Resultados e Impacto

- Redução significativa do esforço manual no registro financeiro
- Padronização dos dados para análise
- Atualização automática de indicadores (KPIs)
- Visibilidade em tempo real do progresso financeiro
- Base pronta para escalabilidade e integração com outras fontes

## 📈 Demonstração Visual

### Interface Mobile e Fluxo de Lógica
<p align="center">
  <img src="WhatsApp Image 2026-03-29 at 16.11.07.jpeg" width="45%" />
  <img src="https://github.com/user-attachments/assets/63c512d7-3a24-4bd9-a6e1-9c0f8834bd0c" width="45%" />
</p>

### Dashboard Final e Monitoramento de Metas
<p align="center">
  <img src="https://github.com/user-attachments/assets/a8b8110c-f438-459a-afb5-9b956ac7029c" width="90%" />
</p>

---

## 🗃️ Estrutura de Dados

Os dados são armazenados em uma tabela estruturada no Excel Online com o seguinte schema:

| Campo        | Tipo        | Descrição                          |
|-------------|------------|------------------------------------|
| valor       | Decimal     | Valor da transação financeira     |
| categoria   | Texto       | Tipo (Alimento, Investimento...)  |
| data        | Data        | Data do registro                  |
| quantidade  | Inteiro     | Quantidade (opcional)             |
| preco_unitario | Decimal  | Valor unitário (opcional)         |

A estrutura foi projetada para permitir integração direta com o Power BI e modelagem analítica.


## 📊 Destaques Técnicos

### Modelagem com DAX

Criação de medidas para análise de performance financeira:

#### Total Investido
```DAX
Total Investido = 
CALCULATE(
    SUM(Tabela[Valor]),
    Tabela[Categoria] = "Investimento"
)

## 🚀 Próximos Passos

- Integração com APIs bancárias
- Armazenamento em banco de dados relacional (SQL)
- Deploy de dashboard interativo com autenticação
- Monitoramento de erros e logs da automação
- Integração com Power Apps para interface mais robusta
