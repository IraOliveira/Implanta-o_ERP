# 📋 Levantamento de Requisitos

Este documento detalha o mapeamento dos processos atuais da **Distribuidora Nordeste Ltda.** e as necessidades que o novo ERP deverá atender para organizar a operação.

---

## 🛒 1. Setor de Compras

### Processo Atual (Como é feito hoje):
- As solicitações de compras de mercadorias são feitas de forma desalinhada via WhatsApp ou e-mail.
- A aprovação dos pedidos de compras depende da assinatura manual do gerente em um papel, gerando lentidão e perda de histórico.

### Necessidades no ERP (Requisitos):
- **Fluxo de aprovação digital:** O sistema deve bloquear pedidos acima de determinado valor até que o gerente aprove com seu usuário.
- **Controle de fornecedores:** Cadastro centralizado de fornecedores com histórico de preços e prazos de entrega.
- **Sugestão de compra:** Relatório ou tela que sugira o quanto comprar com base no giro do estoque (o que mais vende).

---

## 📦 2. Setor de Estoque

### Processo Atual (Como é feito hoje):
- Toda a contagem e controle de entrada e saída de alimentos é registrada em planilhas de Excel separadas.
- Ocorre grande divergência entre o que está na planilha e o estoque físico real.

### Necessidades no ERP (Requisitos):
- **Inventário rotativo:** Ferramenta para contagem periódica de produtos direto no sistema.
- **Rastreabilidade total:** Controle rigoroso de **Lote e Validade** (fundamental para o segmento de distribuição de alimentos).
- **Alerta de estoque mínimo:** O sistema deve avisar quando um produto estiver acabando.

---

## 💰 3. Setor Financeiro

### Processo Atual (Como é feito hoje):
- Falta de integração com os outros setores. O financeiro só descobre que uma compra foi feita quando o boleto físico chega para pagar.

### Necessidades no ERP (Requisitos):
- **Contas a Pagar integrado:** Geração automática da obrigação financeira assim que o estoque der entrada na Nota Fiscal de compra.
- **Contas a Receber automatizado:** Integração com o faturamento de vendas para controle de cobranças e boletos.
- **Fluxo de Caixa em tempo real:** Gráfico ou relatório consolidado de entradas e saídas previstas.

---

## 🔄 4. Fluxo de Processo Proposto (ERP)

Abaixo está o mapeamento visual de como as informações vão transitar entre os setores da Distribuidora Nordeste Ltda. utilizando o novo ERP:

```mermaid
graph TD
    A[🛒 Pedido de Compra criado] --> B{👤 Aprovação do Gerente}
    B -- Rejeitado --> C[❌ Pedido Cancelado]
    B -- Aprovado --> D[🚚 Recebimento da Carga]
    D --> E[📦 Entrada Física no Estoque]
    E --> F[💰 Geração Automática do Contas a Pagar]
    F --> G[📊 Indicadores Atualizados no Dashboard]
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#bbf,stroke:#333,stroke-width:2px
    style F fill:#bfb,stroke:#333,stroke-width:2px