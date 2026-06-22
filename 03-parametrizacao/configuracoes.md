# ⚙️ Parametrização e Configuração do Sistema

Este documento descreve as configurações base do ERP para atender a operação da **Distribuidora Nordeste Ltda.**, garantindo segurança nos acessos, conformidade fiscal e organização financeira.

---

## 👥 1. Cadastro Base e Segurança (Usuários e Permissões)
Para evitar que funcionários acessem dados confidenciais, dividiremos os perfis de acesso no ERP:

- **Perfil Compras:** Permissão para cadastrar fornecedores, emitir pedidos de compras e visualizar relatórios de giro de estoque. *Bloqueado para alterações financeiras.*
- **Perfil Estoque:** Permissão para dar entrada de mercadorias via XML, realizar inventário e emitir relatórios de saldo. *Bloqueado para visualizar preços de custo ou dados financeiros.*
- **Perfil Financeiro:** Permissão total para contas a pagar, contas a receber, fluxo de caixa e liberação de crédito de clientes.
- **Perfil Gerencial/Diretoria:** Acesso total ao sistema (Dashboard) e aprovação de pedidos de compras acima do limite permitido.

---

## 🧾 2. Parametrização Fiscal (Regras de Entrada e Saída)
Como lidamos com distribuição de alimentos, configuraremos as seguintes regras tributárias automáticas para evitar erros de digitação:

- **CFOP (Código Fiscal de Operações):**
  - `5.102` / `6.102`: Venda de mercadoria adquirida de terceiros (saídas estaduais e interestaduais).
  - `1.102` / `2.102`: Entrada de mercadoria para comercialização.
- **CST / CSOSN:** Configuração automática dos códigos de situação tributária para ICMS, PIS e COFINS conforme o regime tributário da empresa.
- **Controle de Lote e Validade:** Campo obrigatório ativado em todas as telas de movimentação para produtos perecíveis.

---

## 💰 3. Estrutura Financeira (Plano de Contas e Centros de Custo)
Organização das gavetas financeiras para gerar relatórios precisos de onde o dinheiro está entrando e saindo:

### Centro de Custo (Quem gasta?):
- `100` - Administrativo
- `200` - Comercial / Vendas
- `300` - Logística / Estoque
- `400` - Operacional / Compras

### Plano de Contas Simplificado (O que gasta?):
- **1. ATIVO** -> 1.1 Disponibilidades (Caixa e Bancos)
- **2. PASSIVO** -> 2.1 Fornecedores a Pagar / 2.2 Obrigações Fiscais
- **3. RECEITAS** -> 3.1 Venda de Alimentos
- **4. DESPESAS** -> 4.1 Folha de Pagamento / 4.2 Combustível e Manutenção de Frota