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

## 📈 Demonstração Visual

### Interface Mobile e Fluxo de Lógica
<p align="center">
  <img src="WhatsApp Image 2026-03-29 at 16.11.07.jpeg" width="45%" />
  <img src="<img width="235" height="338" alt="Captura de tela 2026-03-29 162159.png" />
" width="45%" />
</p>

### Dashboard Final e Monitoramento de Metas
<p align="center">
  <img src="N<img width="1315" height="752" alt="Captura de tela 2026-03-29 172311" src="https://github.com/user-attachments/assets/a8b8110c-f438-459a-afb5-9b956ac7029c" />
" width="90%" />
</p>

---

## 🧠 Destaques Técnicos

### Modelagem com DAX
Para o monitoramento de metas, foram criadas medidas personalizadas para garantir a precisão dos KPIs:

- **Total Investido:**
  ```dax
  Total Investido = CALCULATE(SUM(Tabela1[valor]), Tabela1[categoria] = "investimento")
