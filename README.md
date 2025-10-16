# Expense Tracker


Português

- Descrição
  - Aplicativo web simples para controle financeiro pessoal. Permite registrar receitas e despesas, navegar por meses, visualizar lançamentos em uma tabela e acompanhar um resumo com total de receitas, despesas e balanço.
  - Projeto front-end em React + TypeScript, sem backend. Os dados iniciais são definidos em arquivos locais e novos lançamentos são mantidos apenas em memória (não há persistência ao recarregar a página).

- Funcionalidades
  - Adicionar lançamento com Data, Categoria, Título e Valor.
  - Navegar entre meses (setas para mês anterior e próximo).
  - Tabela de lançamentos filtrada pelo mês selecionado.
  - Resumo com Receitas, Despesas e Balanço, com cores (verde para receitas, vermelho para despesas).
  - Formatação monetária em BRL (pt-BR).
  - Categorias com título, cor e flag de despesa/receita.
  - Tipagem forte com TypeScript.

- Stack e dependências principais
  - React 18, TypeScript 4.
  - styled-components.
  - Create React App (react-scripts 5).
  - Testing Library (Jest + @testing-library/react).

- Estrutura do projeto (resumo)
  - src/App.tsx: Componente raiz; gerencia estado, filtros e cálculos de resumo.
  - src/App.styles.ts: Estilos globais do layout principal via styled-components.
  - src/components/
    - Field: Wrapper de campo de formulário (rótulo + input/select).
    - InfoArea: Cabeçalho do mês atual e resumo (Receitas, Despesas, Balanço).
    - InputArea: Formulário para inserir novos lançamentos.
    - TableArea: Tabela com cabeçalho e corpo para lista filtrada.
    - TableItem: Linha da tabela com formatação de data, categoria (cor), título e valor.
    - ResumeItem: Cartões de resumo com total formatado.
  - src/helpers/
    - dateFilter.ts: Funções para obter mês atual, filtrar por mês, formatar data e nome do mês.
    - formatPrice.ts: Função para formatar valores monetários em pt-BR (BRL).
  - src/data/
    - categories.ts: Mapa de categorias (título, cor, expense).
    - items.ts: Lista inicial de lançamentos de exemplo.
  - src/types/
    - Item.ts: Tipo do lançamento.
    - Category.ts: Tipo do mapa de categorias.

- Como executar
  - Pré-requisitos: Node.js 16+ e npm.
  - Instalação:
    - `npm install`
  - Ambiente de desenvolvimento:
    - `npm start`
    - Abre em http://localhost:3000/.
  - Testes:
    - `npm test`
  - Build de produção:
    - `npm run build`

- Como usar
  - Selecione o mês usando as setas na área de informações.
  - Use o formulário para adicionar um novo lançamento informando Data, Categoria, Título e Valor; clique em "Adicionar".
  - Os lançamentos são exibidos na tabela e filtrados pelo mês selecionado. Os valores de despesa aparecem em vermelho; receitas, em verde.
  - O resumo mostra os totais de receitas, despesas e o balanço (Receitas − Despesas).

- Configuração e personalização
  - Categorias: edite `src/data/categories.ts` para adicionar/alterar categorias. Exemplo:
    ```ts
    export const categories = {
      food: { title: "Alimentação", color: "blue", expense: true },
      rent: { title: "Aluguel", color: "brown", expense: true },
      salary: { title: "Salário", color: "green", expense: false },
      // nova categoria
      transport: { title: "Transporte", color: "purple", expense: true },
    };
    ```
  - Dados iniciais: ajuste `src/data/items.ts` para seus próprios lançamentos de exemplo.
  - Formatação de moeda: altere `src/helpers/formatPrice.ts` para outro locale/moeda, por exemplo USD:
    ```ts
    Intl.NumberFormat("en-US", { style: "currency", currency: "USD" }).format(value)
    ```
  - Idioma dos meses: edite o array de meses em `formatCurrentMonth` dentro de `src/helpers/dateFilter.ts`.

- Limitações conhecidas
  - Sem persistência: ao recarregar a página, os dados voltam ao estado inicial.
  - Validações mínimas no formulário (ex.: não há validação de categoria obrigatória além do select).
  - Não há edição/remoção de lançamentos.
  - Interface e formatação monetária focadas em pt-BR por padrão.

- Roadmap sugerido
  - Persistência via localStorage ou backend (API/DB).
  - Edição e exclusão de lançamentos.
  - Validações de formulário mais robustas.
  - Internacionalização (i18n) da interface.
  - Filtros por categoria e busca textual.
  - Gráficos de evolução mensal.
  - Testes de unidade e integração adicionais.

- Scripts disponíveis
  - `npm start` — inicia o servidor de desenvolvimento.
  - `npm test` — executa a suíte de testes.
  - `npm run build` — gera build de produção.
  - `npm run eject` — exibe as configs do CRA (irreversível).

- Licença
  - Nenhuma licença especificada no package.json. Considere adicionar uma licença (por exemplo, MIT) conforme sua necessidade.

---

English

- Overview
  - Simple web app for personal finance tracking. You can record incomes and expenses, navigate across months, view entries in a table, and see a summary with totals for income, expenses, and balance.
  - Front-end only (React + TypeScript), no backend. Initial data is defined in local files and newly added entries live in memory only (no persistence on page reload).

- Features
  - Add entries with Date, Category, Title, and Amount.
  - Navigate between months (previous/next arrows).
  - Table filtered by the selected month.
  - Summary showing Income, Expenses, and Balance with color coding (green for income, red for expenses).
  - Currency formatting in BRL (pt-BR).
  - Categories with title, color, and expense/income flag.
  - Strong typing with TypeScript.

- Tech stack
  - React 18, TypeScript 4.
  - styled-components.
  - Create React App (react-scripts 5).
  - Testing Library (Jest + @testing-library/react).

- Project structure (summary)
  - src/App.tsx: Root component; manages state, filters, and summary calculations.
  - src/App.styles.ts: Main layout styles using styled-components.
  - src/components/
    - Field: Form field wrapper (label + input/select).
    - InfoArea: Current month header and summary (Income, Expenses, Balance).
    - InputArea: Form to add new entries.
    - TableArea: Table with header and body for the filtered list.
    - TableItem: Row with formatted date, category (color), title, and value.
    - ResumeItem: Summary cards with formatted totals.
  - src/helpers/
    - dateFilter.ts: Helpers to get current month, filter by month, format dates and month names.
    - formatPrice.ts: Formats currency values in pt-BR (BRL).
  - src/data/
    - categories.ts: Category map (title, color, expense).
    - items.ts: Initial example entries.
  - src/types/
    - Item.ts: Entry type.
    - Category.ts: Category map type.

- Getting started
  - Prerequisites: Node.js 16+ and npm.
  - Install:
    - `npm install`
  - Development:
    - `npm start`
    - Opens at http://localhost:3000/.
  - Tests:
    - `npm test`
  - Production build:
    - `npm run build`

- Usage
  - Select the month using the arrows in the info area.
  - Use the form to add a new entry with Date, Category, Title, and Amount; click "Adicionar" (Add).
  - Entries appear in the table and are filtered by the selected month. Expense values are shown in red; income values in green.
  - The summary displays totals for income, expenses, and the balance (Income − Expenses).

- Configuration & customization
  - Categories: edit `src/data/categories.ts` to add/modify categories. Example:
    ```ts
    export const categories = {
      food: { title: "Alimentação", color: "blue", expense: true },
      rent: { title: "Aluguel", color: "brown", expense: true },
      salary: { title: "Salário", color: "green", expense: false },
      transport: { title: "Transporte", color: "purple", expense: true },
    };
    ```
  - Seed data: adjust `src/data/items.ts` to your own example entries.
  - Currency formatting: change `src/helpers/formatPrice.ts` to another locale/currency, e.g. USD:
    ```ts
    Intl.NumberFormat("en-US", { style: "currency", currency: "USD" }).format(value)
    ```
  - Month names: edit the months array in `formatCurrentMonth` within `src/helpers/dateFilter.ts`.

- Known limitations
  - No persistence: reloading the page resets data to the initial state.
  - Minimal form validation.
  - No editing/deleting entries.
  - UI and currency formatting default to pt-BR.

- Suggested roadmap
  - Persist data via localStorage or a backend (API/DB).
  - Edit and delete entries.
  - Improved form validations.
  - UI internationalization (i18n).
  - Category filters and text search.
  - Charts for monthly trends.
  - Additional unit and integration tests.

- Available scripts
  - `npm start` — start dev server.
  - `npm test` — run tests.
  - `npm run build` — build for production.
  - `npm run eject` — expose CRA configs (irreversible).

- License
  - No license specified in package.json. Consider adding one (e.g., MIT).