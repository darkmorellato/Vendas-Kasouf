# KF Analytics - Dashboard Executivo

Dashboard de vendas e análise de produtos para acompanhamento mensal.

## Estrutura de Dados

Os dados estão organizados na pasta `dados/` com a seguinte estrutura:

```
dados/
├── metadados.json          # Configuração global e ordem de exibição
├── maio2026.json           # Dados de Maio 2026
├── abril2026.json          # Dados de Abril 2026
├── mar2026.json            # Dados de Março 2026
├── fev2026.json            # Dados de Fevereiro 2026
├── jan2026.json            # Dados de Janeiro 2026
├── dez2025.json            # Dados de Dezembro 2025
├── nov2025.json            # Dados de Novembro 2025
└── out2025.json            # Dados de Outubro 2025
```

### Formato dos Arquivos de Mês

Cada arquivo de mês (ex: `maio2026.json`) contém:

```json
{
  "label": "Maio 2026",          // Nome exibido no seletor
  "total": 84,                   // Total de itens vendidos
  "data": [                      // Lista de produtos
    {
      "name": "CARREGADOR MOTOROLA 50W",
      "quantity": 2,             // Quantidade vendida
      "percentage": "2,38%"      // Percentual sobre o total
    },
    ...
  ]
}
```

### metadados.json

Contém a configuração global:

```json
{
  "_instrucoes": "Instruções para adicionar novo mês...",
  "_ordem_exibicao": [
    "maio2026",
    "abril2026",
    "mar2026",
    ...
  ]
}
```

A chave `_ordem_exibicao` define a ordem em que os meses aparecem no seletor (do mais recente para o mais antigo).

## Como Adicionar um Novo Mês

1. Copie um arquivo de mês existente (ex: `fev2026.json`)
2. Renomeie para o novo mês (ex: `jun2026.json`)
3. Altere os campos:
   - `label`: Nome exibido (ex: "Junho 2026")
   - `total`: Soma das quantidades
   - `data`: Lista de produtos com `name`, `quantity` e `percentage`
4. Adicione a nova chave (ex: `"jun2026"`) no início do array `_ordem_exibicao` em `metadados.json`

**Nota:** A ordem é mais recente primeiro. Lembre-se de atualizar a ordem do array.

## Como Usar

Abra o arquivo `index.html` em um navegador web. O dashboard carregará automaticamente os dados da pasta `dados/`.

## Atualização de Dados

Para atualizar os dados de um mês existente, edite o arquivo correspondente na pasta `dados/`. As alterações serão refletidas ao recarregar a página.

## Tecnologias Utilizadas

- HTML5
- Tailwind CSS
- Chart.js
- JavaScript (Vanilla)

## Funcionalidades

- Seletor de período (mês/ano)
- Estatísticas gerais (total de itens, produtos únicos, top produto)
- Gráficos de distribuição
- Tabela detalhada de produtos
- Filtros por categoria
- Comparação com período anterior
- Exportação de dados

---

Desenvolvido para análise de vendas de produtos eletrônicos e acessórios.
