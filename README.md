# Relatório Executivo de Vendas e Lucratividade – Power BI

## Sobre o Projeto

Este projeto consiste na construção de um **dashboard executivo de análise financeira** a partir da base de dados *Financial Sample*, utilizando o Power BI. O objetivo foi transformar uma tabela única em um modelo dimensional do tipo **Star Schema**, criando tabelas dimensão e fato para permitir análises rápidas e precisas sobre vendas, lucro, margem e desempenho por segmento, país, produto e período.

O relatório final apresenta uma visão consolidada dos principais indicadores de negócio, com foco em **rentabilidade**, **evolução temporal** e **distribuição geográfica**, sendo uma ferramenta valiosa para tomada de decisão em operações comerciais e financeiras.

---

## Autor

**Silvanio Gois**  
📊 Gestor de Operações e Negócios Orientado a Dados

- 🌐 [Portfólio](https://www.silvaniogois.com.br/)  
- 💼 [LinkedIn](https://www.linkedin.com/in/silvanio-gois-6667b918b)

---

## 📁 Estrutura do Repositório

| Arquivo | Descrição |
|---------|-----------|
| `Financial Sample.xlsx` | Base de dados original utilizada no projeto |
| `Modelar&TransformarDadosComDax.pbix` | Arquivo do Power BI com o modelo e o dashboard |
| `Modelar&TransformarDadosComDax.pdf` | Documentação complementar do modelo e medidas DAX |
| `Modelar&TransformarDadosComDax.png` | Imagem do dashboard final (versão estática) |
| `ModelagemProjetoDIO.png` | Imagem do modelo Star Schema (diagrama de relacionamentos) |

---

## 🔗 Acesso ao Relatório Online

O dashboard está publicado no serviço Power BI e pode ser acessado pelo link abaixo:

👉 [Acessar Relatório Executivo](https://app.powerbi.com/view?r=eyJrIjoiZmFjY2RlMTItNGE3NS00Mzg2LWJmM2QtMmQ3MThjOWMxNGMyIiwidCI6IjJlYmQyYzU0LWY1ZDMtNGVmYi05ZGE3LWU4Yzk0YmQyMWQzOSJ9)

---

## 🧩 Modelagem de Dados – Star Schema

A base original foi transformada em um modelo estrela com as seguintes tabelas:

### Tabelas Dimensão
- **D_Calendario** – criada via DAX com a função `CALENDAR()`, contendo hierarquia de datas (ano, mês, dia da semana, trimestre).
- **D_Produtos** – contém `ID_Produto`, nome do produto e métricas agregadas (média de unidades vendidas, média, máximo e mínimo de valor de venda).
- **D_Produtos_Detalhes** – detalhamento adicional por produto e faixa de desconto.
- **D_Descontos** – dimensão com as faixas de desconto e o desconto médio.
- **D_Detalhes** – agrupa as informações de `Segment` e `Country`.

### Tabela Fato
- **F_Vendas** – tabela fato com as métricas de vendas (`Sales`, `Profit`, `Units Sold`, `COGS`, etc.) e chaves estrangeiras para todas as dimensões.

### Relacionamentos
Todas as dimensões se conectam à tabela fato em relacionamentos do tipo **um-para-muitos**, garantindo a integridade referencial e o desempenho das consultas.

---

## 📊 Medidas DAX Criadas

As principais medidas utilizadas no dashboard foram:

| Medida | Fórmula DAX | Descrição |
|--------|-------------|-----------|
| **Total Vendas** | `SUM(F_Vendas[Sales])` | Soma total do faturamento líquido |
| **Total Lucro** | `SUM(F_Vendas[Profit])` | Soma total do lucro |
| **Total Unidades** | `SUM(F_Vendas[Units Sold])` | Quantidade total de unidades vendidas |
| **Margem Lucro %** | `DIVIDE([Total Lucro], [Total Vendas], 0)` | Margem de lucro percentual |
| **Lucro YTD** | `TOTALYTD([Total Lucro], D_Calendario[Date])` | Lucro acumulado no ano |
| **Lucro por Unidade** | `DIVIDE([Total Lucro], [Total Unidades], 0)` | Lucro médio por unidade vendida |
| **Preço Médio Venda** | `AVERAGE(F_Vendas[Sale Price])` | Preço médio praticado |

---

## 📈 Visuais do Dashboard

O relatório foi organizado em uma única página com os seguintes elementos:

1. **Cartões (KPIs)** – Total de Vendas, Total de Lucro e Margem de Lucro %.
2. **Gráfico de Linhas** – Evolução mensal do Total de Vendas e Total de Lucro.
3. **Gráfico de Barras Horizontais** – Top 5 Produtos por faturamento.
4. **Gráfico de Colunas Empilhadas** – Vendas por Segmento (detalhado por País).
5. **Gráfico de Rosca** – Participação percentual das vendas por Segmento.
6. **Mapa** – Distribuição geográfica do lucro por País.
7. **Slicers** – Filtros interativos para Ano, Segmento e Produto.

---

## 🛠️ Ferramentas e Tecnologias

- **Power BI Desktop** – modelagem, medidas DAX e construção do dashboard.
- **Power Query** – transformação e limpeza dos dados.
- **DAX (Data Analysis Expressions)** – criação de medidas e colunas calculadas.
- **Power BI Service** – publicação e compartilhamento online do relatório.

---

## 📌 Como Reproduzir o Projeto

1. Baixe o arquivo `Financial Sample.xlsx` e o `.pbix` deste repositório.
2. Abra o arquivo `.pbix` no Power BI Desktop.
3. Verifique as tabelas e relacionamentos no modelo.
4. Explore as medidas e os visuais criados.
5. Publique no seu próprio workspace do Power BI Service, se desejar.

---

## 📚 Aprendizados e Destaques

- Aplicação prática do modelo **Star Schema** em um cenário real.
- Uso de funções DAX como `CALENDAR`, `SUMMARIZE`, `ADDCOLUMNS`, `LOOKUPVALUE`, `TOTALYTD` e `DIVIDE`.
- Criação de um dashboard executivo com foco em usabilidade e clareza visual.
- Integração entre modelagem de dados e visualização para suporte à decisão.

---

## 📬 Contato

Fique à vontade para entrar em contato para dúvidas, sugestões ou oportunidades de colaboração.

- 📧 E-mail: [sg@silvaniogois.com.br](mailto:sg@silvaniogois.com.br)  
- 🌐 [silvaniogois.com.br](https://www.silvaniogois.com.br/)  
- 💼 [LinkedIn](https://www.linkedin.com/in/silvanio-gois-6667b918b)

---

*Este projeto foi desenvolvido como parte do desafio de modelagem e transformação de dados com DAX na DIO.*