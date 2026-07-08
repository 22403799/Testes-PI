# Sessão de Teste Exploratória 1 — SupplyRP

- **Data da Sessão:** 7 de Julho de 2026
- **Testador:** Thays Gomes
- **Objetivo:** Validar os fluxos de autenticação, consistência no cadastro de ativos, tratamento de erros na criação de produtos, integridade do cadastro de setores e links institucionais.
- **Total de Tempo Alocado:** 20 minutos

---

## Visão Geral

- **Escopo:** Autenticação de usuários, módulos de ativos patrimoniais, cadastro de produtos e gerenciamento de setores.
- **Ambiente de Teste:** Aplicação Web.
- **Técnica:** Teste Manual Exploratório.

---

## Sumário de Bugs

**Total de anomalias encontradas: 5**
- CRÍTICO: 1
- ALTO: 2
- MÉDIO: 2

### Bugs Críticos

- **[BUG-01](https://github.com/22403799/Testes-PI/issues/22) (CRÍTICO) — Erro 500 (Internal Server Error) ao criar ativo com valor de aquisição massivo**
  - **Passos:**
    1. Acessar a tela de "Criação de ativos patrimoniais".
    2. Preencher os dados obrigatórios do ativo.
    3. No campo "Valor de Aquisição", preencher com um valor numérico muito grande (ex: `> 1000000000000`).
    4. Clicar em salvar para disparar a requisição.
  - **Esperado:** O sistema deve validar o limite numérico permitido pelo banco de dados e exibir uma mensagem de erro adequada ao usuário na interface, impedindo o estouro de dados.
  - **Encontrado:** A aplicação apresenta um erro genérico e o no console aparece `Erro 500 (Internal Server Error)`.

### Bugs de Severidade Alta

- **[BUG-02](https://github.com/22403799/Testes-PI/issues/23) (ALTO) — Mensagem genérica inadequada ao registrar produto com código duplicado**
  - **Passos:**
    1. Acessar a tela de "Gerenciamento de Produtos".
    2. Tentar cadastrar um produto utilizando um código identificador que já exista no sistema.
  - **Esperado:** O sistema deve validar a duplicidade do código e exibir uma mensagem clara e específica (ex: "Este código de produto já está cadastrado").
  - **Encontrado:** O sistema exibe o alerta genérico: *“Ocorreu um erro inesperado. Por favor, tente novamente mais tarde.”*.

- **[BUG-03](https://github.com/22403799/Testes-PI/issues/24) (ALTO) — Quebra de integridade de dados: Permite salvar Setores com o mesmo nome**
  - **Passos:**
    1. Acessar a tela de "Criação de setores".
    2. Criar um setor com o nome "Almoxarifado".
    3. Tentar criar um novo setor digitando exatamente o mesmo nome "Almoxarifado".
  - **Esperado:** O sistema deve impedir a criação e emitir um aviso informando que já existe um setor cadastrado com esse nome, evitando problemas na segregação setorial (`RF004`).
  - **Encontrado:** O sistema aceita a gravação e salva múltiplos setores homônimos no banco de dados, gerando inconsistência operacional para a filtragem de dados.

### Bugs de Severidade Média

- **[BUG-04](https://github.com/22403799/Testes-PI/issues/25) (MÉDIO) — Botão de “Esqueci a Senha” inoperante na tela de login**
  - **Passos:**
    1. Acessar a tela inicial de Login.
    2. Clicar sobre o botão "Esqueci a Senha".
  - **Esperado:** O sistema deve iniciar o fluxo de recuperação de acesso.
  - **Encontrado:** O botão não possui qualquer funcionalidade associada, comportando-se como um elemento estático na interface.

- **[BUG-05](https://github.com/22403799/Testes-PI/issues/26) (MÉDIO) — Links de “Termos de Uso” e “Política de Privacidade” quebrados**
  - **Passos:**
    1. Navegar até o rodapé da página de cadastro.
    2. Clicar nos links direcionados para os "Termos de Uso" ou "Política de Privacidade".
  - **Esperado:** Abertura dos respectivos links.
  - **Encontrado:** Os links estão quebrados e não executam redirecionamento ou abertura de conteúdo.
