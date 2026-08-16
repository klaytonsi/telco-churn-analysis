![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-success)
![License](https://img.shields.io/badge/Licen%C3%A7a-MIT-yellow)
![Made with Colab](https://img.shields.io/badge/Made%20with-Google%20Colab-orange?logo=googlecolab)

# 📉 Análise Preditiva de Churn de Clientes — Telco

**Identifiquei os 5 principais fatores que levam clientes a cancelar o serviço em uma operadora de telecom, com um modelo preditivo de 84% de AUC-ROC, permitindo à empresa priorizar ações de retenção nos clientes de maior risco.**

🔗 **[Acesse o dashboard interativo no Looker Studio](https://datastudio.google.com/reporting/7429be75-9dfb-4801-b746-f1cefff852da)**

![Dashboard completo com KPIs, segmentação por contrato e importância das variáveis](imagens/dashboard_hero.jpg)

---

## 🎯 Sobre o projeto

Este é um projeto de ponta a ponta (end-to-end) de Ciência de Dados, desenvolvido **100% em ambiente mobile** (Android), analisando o dataset público *Telco Customer Churn* (Kaggle) para responder à pergunta: **por que os clientes cancelam, e quem são os próximos com maior risco de sair?**

O projeto cobre todo o ciclo: limpeza e tratamento de dados (ETL), análise exploratória, modelagem preditiva com Machine Learning, dashboard interativo e relatório de negócio com recomendações acionáveis.

## 🔑 Principais Insights

A análise (validada tanto pela exploração dos dados quanto pelos dois modelos de Machine Learning) identificou **5 fatores centrais de churn**:

| Fator | Insight |
|---|---|
| **Tempo de contrato (tenure)** | Clientes novos têm risco de cancelamento muito maior — reforça a importância dos primeiros meses de relacionamento |
| **Tipo de contrato** | Contratos mensais (*month-to-month*) têm taxa de churn de **~43%**, contra ~11% (1 ano) e ~3% (2 anos) |
| **Serviço de internet fibra óptica** | Associado a taxas de cancelamento mais altas — possível sinal de insatisfação com preço ou qualidade |
| **Forma de pagamento (boleto eletrônico)** | Clientes que pagam por *electronic check* cancelam mais que os demais métodos |
| **Gasto mensal elevado** | Mensalidades mais altas aumentam a probabilidade de cancelamento |

![Detalhe: taxa de churn por tipo de contrato](imagens/contract_churn_insight.jpg)

> 📊 Um ponto de atenção documentado na análise: existe multicolinearidade entre a variável `tenure` (bruta) e a variável derivada `Tenure_Group`, o que foi tratado e registrado no relatório técnico para não distorcer a interpretação dos coeficientes do modelo.

## 🛠️ Tecnologias e Ferramentas

Todo o projeto foi construído em fluxo **100% gratuito e mobile**:

- **Linguagem:** Python (Pandas, NumPy, Scikit-learn)
- **Execução:** Google Colab
- **Modelagem:** Regressão Logística + Random Forest
- **Dashboard:** Google Looker Studio (alternativa gratuita e mobile-friendly ao Power BI, que não roda em Android)
- **Ponte de dados:** Google Sheets
- **Relatório final:** Microsoft Word
- **Versionamento:** Git e GitHub

## 📈 Resultados do Modelo

| Métrica | Valor |
|---|---|
| Total de clientes analisados | 7.043 |
| Clientes em churn | 1.869 |
| Taxa de churn geral | 26,54% |
| Ticket médio mensal | $64,76 |
| **AUC-ROC do melhor modelo** | **0,84** |

## 📊 Dashboard Interativo

O dashboard permite explorar a taxa de churn segmentada por Contrato, Tipo de Internet, Forma de Pagamento, Faixa de Tempo de Contrato e Perfil de Idade (Senior Citizen), além de visualizar as variáveis mais importantes segundo o modelo.

🔗 **Acesse o dashboard:** [Looker Studio — Análise de Churn](https://datastudio.google.com/reporting/7429be75-9dfb-4801-b746-f1cefff852da)

## 💡 Recomendações de Negócio

- **Retenção:** priorizar contato proativo com clientes em contrato mensal nos primeiros meses de relacionamento, oferecendo incentivo para migração a contratos anuais.
- **Produto:** investigar causas de insatisfação entre clientes de internet fibra óptica (preço, qualidade, suporte).
- **Atendimento/Financeiro:** oferecer formas de pagamento automatizadas (débito automático, cartão) como alternativa ao boleto eletrônico, reduzindo fricção e risco de cancelamento.

*(Detalhamento completo das recomendações por área no [relatório final](reports/Relatorio_Final_Analise_Churn.docx))*

## 📁 Estrutura do Repositório

```
├── data/               # Dataset (Telco Customer Churn - Kaggle)
├── notebooks/          # Notebooks de ETL, EDA e Machine Learning (Colab)
├── imagens/            # Screenshots do dashboard
├── reports/            # Relatório final de negócio (Word)
├── README.md
└── LICENSE
```

## 🚀 Como reproduzir

1. Clone este repositório
2. Abra os notebooks em `notebooks/` no Google Colab
3. Instale as dependências: `pip install -r requirements.txt`
4. Execute as células em ordem: ETL → EDA → Modelagem

## 🔮 Melhorias Futuras

- Testar modelos adicionais (XGBoost, LightGBM) para comparação de performance
- Deploy de um app interativo (Streamlit) para simulação de risco de churn por cliente
- Automatizar atualização do dashboard via pipeline de dados

## 📄 Licença

Este projeto está sob a licença MIT — veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

📫 Desenvolvido por **Klayton** | [LinkedIn](https://www.linkedin.com/in/klayton-silva-9b5a23428) | Projeto de portfólio em Dados & IA
