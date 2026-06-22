# 🚀 Plano de Go-Live (Virada de Sistema)

Este documento estabelece o roteiro de ações e o checklist de segurança para a transição do sistema antigo (planilhas) para a entrada oficial do novo ERP na **Distribuidora Nordeste Ltda.**

A virada será realizada durante o final de semana para não interromper as operações comerciais e de faturamento da empresa.

---

## 📅 Cronograma do Final de Semana da Virada

*   **Sexta-feira (18:00h):** Bloqueio total das planilhas antigas. Nenhum funcionário poderá dar entradas ou saídas. Início da contagem física final do estoque.
*   **Sábado (08:00h às 14:00h):** Digitação e validação do saldo final de estoque no ambiente oficial do ERP.
*   **Sábado (14:00h às 18:00h):** Importação dos saldos iniciais do Contas a Pagar e Contas a Receber.
*   **Domingo (09:00h às 12:00h):** Testes de faturamento (emissão de nota fiscal de teste em ambiente de produção) e testes de impressão de etiquetas de paletes.
*   **Segunda-feira (07:00h):** Abertura oficial das portas com o novo ERP ativo.

---

## 📋 Checklist de Pré-Requisitos (Go/No-Go)
O sistema só entrará no ar na segunda-feira se todos os itens abaixo estiverem marcados como **OK**:

- [ ] Todos os usuários do sistema cadastrados e com suas respectivas permissões configuradas.
- [ ] Cadastro de Clientes, Fornecedores e Produtos 100% migrados e validados.
- [ ] Saldo de estoque físico batendo com o saldo inserido no ERP.
- [ ] Certificado Digital instalado no servidor para emissão de Notas Fiscais (NF-e).
- [ ] Impressoras térmicas e de rede testadas e configuradas nas estações de trabalho do estoque.
- [ ] Termos de homologação assinados por todos os gestores de área.

---

## 🦺 Equipe de Suporte Operacional (War Room)
Durante a primeira semana de uso, uma equipe ficará dedicada exclusivamente para resolver dúvidas e gargalos de forma imediata na distribuidora:

| Nome do Integrante | Papel no Projeto | Área de Atuação no Dia |
| :--- | :--- | :--- |
| **Você (Irá Jorge)** | Consultor de Implantação Líder | Coordenação Geral e Fiscal |
| **João Silva** | Analista de Suporte ERP | Atendimento ao Setor de Compras e TI |
| **Maria Souza** | Key User (Estoque) | Apoio presencial aos estoquistas na expedição |
| **Carlos Lima** | Key User (Financeiro) | Apoio presencial no caixa e faturamento |