# 🔄 Plano de Migração de Dados

Este documento descreve a estratégia para extrair os dados históricos das planilhas antigas da **Distribuidora Nordeste Ltda.**, tratá-los para evitar duplicidades e importá-los com segurança para o novo ERP.

---

## 📊 1. Escopo dos Dados Migrados
Definição de quais informações serão trazidas para o novo sistema e qual o critério de limpeza:

*   **Clientes:** Cadastro de clientes ativos com CNPJ, endereço e histórico de crédito. *Critério de limpeza: Clientes sem compras nos últimos 24 meses não serão migrados.*
*   **Fornecedores:** Cadastro de parceiros comerciais ativos e indústrias de alimentos parceiras.
*   **Produtos:** Catálogo completo com código de barras (EAN), descrição padronizada, unidade de medida (Ex: Cx, Kg, Un) e NCM (Nomenclatura Comum do Mercosul).
*   **Saldo de Estoque:** A foto do estoque real no dia anterior à virada de chave do sistema.

---

## ⚙️ 2. O Processo E.T.L. (Extração, Tratamento e Carga)
Passo a passo técnico adotado para garantir a qualidade das informações:

1.  **Extração:** Exportação das planilhas de Excel que a empresa usava para o formato `.CSV`.
2.  **Tratamento (Saneamento de Dados):**
    *   Correção de CNPJs e CPFs inválidos ou com pontos e traços fora do padrão.
    *   Padronização do cadastro de produtos (Ex: transformar "Arroz Tio J. 5kg" e "ARROZ TIO JOAO 5KG" em um único padrão: `ARROZ TIPO 1 TIO JOÃO 5KG`).
    *   Eliminação de cadastros duplicados.
3.  **Carga (Importação):** Utilização das planilhas modelo (templates) do próprio ERP para importação em lote via sistema.

---

## 🧪 3. Homologação e Validação
Como garantiremos que os dados entraram certos?

*   **Validação por Amostragem:** O setor financeiro e de compras vão escolher 20 clientes e 20 produtos aleatórios no ERP e comparar item por item com as planilhas antigas.
*   **Validação de Saldos:** A soma do valor financeiro do estoque na planilha antiga deve bater exatamente com o valor total em estoque gerado pelo relatório do novo ERP.