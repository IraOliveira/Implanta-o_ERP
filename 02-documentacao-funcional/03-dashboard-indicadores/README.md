# Dashboard de Indicadores de Implantação (KPIs de Go-Live)

Este módulo do portfólio apresenta a estrutura de dados, métricas de sucesso e o modelo conceitual de um **Dashboard de Controle de Rollout**, projetado para gerenciar projetos de implantação de sistemas em larga escala (múltiplas filiais/pontos de venda).

O objetivo deste painel é munir a gerência de projetos e a diretoria com visibilidade em tempo real sobre a saúde da virada de chave (*Go-Live*), mitigando riscos de atraso e gargalos de treinamento.

---

## 1. Indicadores Chave de Performance (KPIs) Mapeados

O painel foi estruturado com base em 4 pilares indispensáveis para governança de projetos de sistemas:

*   **Percentual de Avanço do Cronograma (% Rollout Executado):** Proporção de lojas/unidades que concluíram com sucesso todas as fases em relação ao escopo total planejado.
*   **Desvio de Cronograma (Slippage Rate):** Métrica que calcula a variação em dias entre a data planejada para o *Go-Live* e a data de conclusão real.
*   **Volumetria de Chamados Críticos (Blocked Issues):** Contagem de incidentes de Severidade 1 (Bloqueantes) abertos nas primeiras 48 horas pós-implantação.
*   **Índice de Adoção de Usuários (Training Score):** Média de aproveitamento das equipes operacionais nas avaliações pós-treinamento obrigatório.

---

## 2. Estrutura da Base de Dados (Mock Data)

Para alimentar os visuais do Power BI, foi modelada a tabela fato abaixo, representando o monitoramento das ondas de migração de unidades de negócio:

| ID Unidade | Nome da Filial | Região | Onda de Migração | Status Atual | Data Prevista | Data Real | Chamados Críticos (48h) | Nota Treinamento |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **UN-001** | Distribuidora Matriz | Nordeste | Onda 1 | Concluído | 10/05/2026 | 10/05/2026 | 0 | 9.2 |
| **UN-002** | Filial Salvador | Nordeste | Onda 1 | Concluído | 15/05/2026 | 17/05/2026 | 2 | 8.5 |
| **UN-003** | Filial Recife | Nordeste | Onda 2 | Concluído | 22/05/2026 | 22/05/2026 | 1 | 7.8 |
| **UN-004** | Filial Fortaleza | Nordeste | Onda 2 | Em Andamento | 12/06/2026 | - | 0 | 9.0 |
| **UN-005** | Filial Natal | Nordeste | Onda 3 | Planejado | 30/06/2026 | - | 0 | - |

---

## 3. Modelo de Visão e Layout Sugerido (Wireframe Conceitual)

Para que o Dashboard seja altamente executivo, a disposição dos cartões e gráficos no Power BI segue a seguinte arquitetura de informação:

### 3.1. Linha Superior (Cartões de Resumo / High-Level)
*   **[Cartão 1]** Total de Lojas Escopadas: `5`
*   **[Cartão 2]** % Conclusão: `60%`
*   **[Cartão 3]** Média de Erros Críticos por Loja: `0.6`
*   **[Cartão 4]** Média de Satisfação do Usuário: `8.6/10`

### 3.2. Corpo Central (Gráficos de Tendência e Alocação)
*   **Gráfico de Barras Empilhadas:** Status de Implantação por Onda de Migração (Eixo X: Ondas | Eixo Y: Qtd de Unidades | Legenda: Planejado, Em Andamento, Concluído).
*   **Gráfico de Linhas (Burn-down do Projeto):** Linha acumulada de Lojas Previstas vs. Linha acumulada de Lojas Realizadas ao longo dos meses.
*   **Matriz Detalhada:** Tabela dinâmica listando as unidades com atraso superior a 2 dias (destacadas com formatação condicional em vermelho).

---

## 4. Próximos Passos & Expansão do Repositório

*   [ ] Disponibilizar o arquivo de extração de dados em formato `.csv` na pasta raiz deste módulo.
*   [ ] Publicar os prints das telas do painel construído no Power BI Desktop diretamente neste arquivo de documentação.
*   [ ] Integrar metas automáticas utilizando a ferramenta de Metas (*Goals*) do ecossistema Microsoft Power BI.
