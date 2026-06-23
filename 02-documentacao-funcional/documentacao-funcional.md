# Documentação Funcional e Plano de Testes

Este documento formaliza o entendimento de negócio, o mapeamento de processos e a matriz de testes funcionais integrados para o projeto de implantação do ERP na **Distribuidora Nordeste Ltda.**

---

## 1. Levantamento de Requisitos (Matriz RTM)

Abaixo estão descritos os requisitos funcionais críticos mapeados durante as reuniões de alinhamento com as áreas de negócio (Estoque, Compras e Faturamento).

| ID | Área | Descrição do Requisito | Severidade / Prioridade |
| :--- | :--- | :--- | :--- |
| **RF-01** | Estoque | O sistema deve controlar lotes e validades de forma automática para evitar perdas de insumos perecíveis. | Alta (Bloqueante) |
| **RF-02** | Compras | Geração automatizada de sugestão de compras baseada no estoque mínimo e giro de produtos. | Média |
| **RF-03** | Faturamento | Emissão de Nota Fiscal Eletrônica (NF-e) integrada de forma nativa ao fluxo de expedição, sem necessidade de digitação manual de chaves. | Alta (Bloqueante) |
| **RF-04** | Logística | Rastreabilidade total do fluxo logístico, desde a entrada do fornecedor até o despacho final. | Média |

---

## 2. Mapeamento de Processos (AS-IS vs. TO-BE)

### 2.1. Processo Anterior (AS-IS) - Fluxo de Recebimento Manual
Antes do ERP, o controle era descentralizado, suscetível a falhas humanas e digitação duplicada.

```mermaid
graph TD
    A[Chegada do Caminhão com NF] --> B[Conferência Manual em Papel]
    B --> C{Erros de Quantidade?}
    C -- Sim --> D[Anotação em Caneta e Contato com Fornecedor]
    C -- Não --> E[Digitação Manual da Nota no Sistema Antigo]
    E --> F[Atualização Manual da Planilha de Estoque]
    F --> G[Fim do Processo]
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style D fill:#ffcccc,stroke:#333,stroke-width:1px
    style F fill:#ffcccc,stroke:#333,stroke-width:1px

    graph TD
    A[Chegada do Caminhão] --> B[Importação Automática do XML da NF-e]
    B --> C[Bipagem dos Produtos / Coletor de Dados]
    C --> D{Divergência entre XML e Físico?}
    D -- Sim --> E[Abertura Automática de Ocorrência de Entrada]
    D -- Não --> F[Entrada Automática no Estoque]
    F --> G[Geração Contábil e Fiscal Integrada]
    G --> H[Fim do Processo]

    style A fill:#bbf,stroke:#333,stroke-width:2px
    style E fill:#ffffcc,stroke:#333,stroke-width:1px
    style F fill:#d4edda,stroke:#333,stroke-width:2px
    style G fill:#d4edda,stroke:#333,stroke-width:2px
    