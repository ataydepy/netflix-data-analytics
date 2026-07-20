# 🎬 Netflix Data Analytics: Catálogo e Comportamento de Dados 2025/2026

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Power BI](https://img.shields.io/badge/Power_BI-Data_Visualization-yellow.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data_Cleaning-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📌 Sobre o Projeto
Este projeto consiste no desenvolvimento de um pipeline de **Engenharia de Dados (ETL)** utilizando Python e Pandas para o tratamento de uma base de dados em escala de produção com mais de 210 mil registros da Netflix, culminando na criação de um **Dashboard Interativo e Inteligente no Power BI** utilizando modelagem avançada e fórmulas em código DAX.

> **Nota de Governança de Dados:** Este projeto utiliza um *Synthetic Dataset* (dados sintéticos) que simula perfeitamente cenários reais de distribuição, outliers e valores nulos de negócio, garantindo a conformidade com leis de privacidade de dados (como LGPD/GDPR) enquanto valida regras complexas de engenharia e BI.

---

## 📁 Estrutura do Repositório

* 📁 `data/` -> Contém o dataset original e o arquivo higienizado `movies_limpo.csv`.
* 📁 `notebooks/` -> Scripts do Jupyter Notebook contendo toda a lógica do pipeline de ETL.
* 📁 `dashboard/` -> Arquivo `.pbix` do Power BI com o painel interativo.
* 📄 `LICENSE` -> Termos da Licença MIT aplicada ao projeto.

---

## 🛠️ Fase 1: Engenharia de Dados & ETL (Python)
A primeira etapa focou em preparar os dados brutos ("sujos") para garantir que nenhum cálculo matemático futuro fosse distorcido. Os principais tratamentos aplicados via Pandas foram:

1. **Substituição por Valor Fixo (`.fillna(0)`)**: Identificação de mais de 700 campos nulos nas colunas de temporadas e episódios. O pipeline identificou logicamente que se tratavam de *Filmes* e preencheu os campos com `0` de forma segura.
2. **Inputação por Mediana (`.median()`)**: Tratamento de 150 registros sem nota no IMDb. Em vez de usar a média (sensível a valores extremos) ou zerar os dados (o que destruiria os indicadores de qualidade), foi aplicada a mediana da distribuição.
3. **Higienização de Categorias**: Campos nulos em gêneros secundários foram tratados para a categoria padrão `'Nenhum'`.
4. **Exportação Otimizada**: Salvamento dos dados tratados ocultando colunas redundantes de indexação (`index=False`).

---

## 📊 Fase 2: Business Intelligence Avançado (Power BI)
Diferente de relatórios estáticos, este dashboard foi construído focando em **programação e interatividade**, utilizando expressões analíticas de dados (**DAX**) para criar métricas customizadas e dinâmicas na camada de Front-end.

### Perguntas de Negócio Respondidas:
* **Catálogo de Mídias**: Qual a proporção exata e real de Filmes vs. Séries na plataforma?
* **Guerra dos Gêneros**: Quais categorias dominam as produções originais e licenciadas?
* **Análise Financeira (Orçamento vs. Retorno)**: Investimentos milionários em produções convertem em maiores bilheterias e notas de críticos do IMDb?

---

## 🚀 Como Executar o Projeto

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/SEU-USUARIO/netflix-data-analytics.git](https://github.com/SEU-USUARIO/netflix-data-analytics.git)
