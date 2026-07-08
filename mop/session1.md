# Sessão de Teste Exploratória 1 — MOP

* **Data da Sessão:** 06 de Julho de 2026 
* **Testador:** Thays Gomes
* **Objetivo:** Validar o fluxo de autenticação, usabilidade de segurança, visualização, filtragem de dados e exportação de relatórios.
* **Total de Tempo Alocado:** 20 minutos

---

## Visão Geral

* **Escopo:** Fluxos de criação de conta e login (Web), visualização de dashboards no modo noturno, mecanismos de filtros no feed e exportação gerencial.
* **Ambiente de Teste:** Aplicação Web (https://mopiphan-gwy9z5.flutterflow.app).
* **Técnica:** Teste Manual Exploratório.

---

## Sumário de Bugs

**Total de anomalias encontradas: 8**

* CRÍTICO: 3
* ALTO: 2
* MÉDIO: 3

### Bugs Críticos

* **[BUG-01](https://github.com/22403799/Testes-PI/issues/14) (CRÍTICO) — Login permitido sem criar conta**
  * **Passos:**
    1. Acessar a tela inicial.
    2. Deixar os campos de e-mail e senha vazios.
    3. Clicar diretamente no botão "Sign In".
  * **Esperado:** Bloqueio imediato com aviso de campos obrigatórios e impedimento de acesso ao sistema .
  * **Encontrado:** O sistema permite ignorar as credenciais e efetua o login direto na aplicação sem validar ou exigir a conta.


* **[BUG-02](https://github.com/22403799/Testes-PI/issues/15) (CRÍTICO) — Sistema aceita senhas inválidas**
  * **Passos:**
    1. Acessar a aba "Criar login" na tela de autenticação.
    2. Digitar senhas completamente diferentes nos dois campos obrigatórios de definição de senha.
    3. Confirmar a criação da conta.
  * **Esperado:** Exibição de mensagem informando que os campos não conferem e rejeição do cadastro.
  * **Encontrado:** A conta é registrada com sucesso, aceitando senhas divergentes e gerando uma inconsistência de segurança.


* **[BUG-03](https://github.com/22403799/Testes-PI/issues/16) (CRÍTICO) — Cadastro de e-mails em formato inválido ou corrompido**
  * **Passos:**
    1. Acessar a aba "Criar login".
    2. Inserir uma sequência de texto qualquer que não siga o padrão de e-mail (ex: "teste@teste").
    3. Confirmar a criação da conta.
  * **Esperado:** Validação sintática do e-mail impedindo o cadastro caso o formato esteja errado.
  * **Encontrado:** Sistema aceita e-mails fora de formatação padrão e conclui o registro.

---

### Bugs de Severidade Alta

* **[BUG-04](https://github.com/22403799/Testes-PI/issues/17) (ALTO) — Impossível realizar Logout**
  * **Passos:**
    1. Estar logado no site.
  * **Esperado:** Conseguir realizar logout.
  * **Encontrado:** Não existe botão de logout.

* **[BUG-05](https://github.com/22403799/Testes-PI/issues/18) (ALTO) — Falha de acessibilidade por quebra de contraste**
  * **Passos:**
    1. Navegar pelo dashboard de gráficos.
  * **Esperado:** Os textos serem visíveis com boa legibilidade.
  * **Encontrado:** O contraste de texto fica extremamente ruim e ilegível.

---

### Bugs de Severidade Média

* **[BUG-06](https://github.com/22403799/Testes-PI/issues/19) (MÉDIO) — Botão de recuperação de conta (Esqueci Senha) não funcional**
  * **Passos:**
    1. Na tela de entrada, clicar no botão "Forgot Password".
  * **Esperado:** Direcionamento automático para o fluxo ou tela de recuperação de e-mail/senha.
  * **Encontrado:** O botão não engaja nenhuma ação ou alteração na tela (sem funcionalidade associada).


* **[BUG-07](https://github.com/22403799/Testes-PI/issues/20) (MÉDIO) — Impossível filtrar dados**
  * **Passos:**
    1. Acessar o feed de notícias.
  * **Esperado:** O painel se ajustar e exibir estritamente as menções que correspondam à filtragem.
  * **Encontrado:** Impossível aplicar filtros.


* **[BUG-08](https://github.com/22403799/Testes-PI/issues/21) (MÉDIO) — Impossível Exportar de Relatórios**
  * **Passos:**
    1. Ir até a tela inicial e ver os gráficos.
  * **Esperado:** Conseguir fazer o download imediato do arquivo analítico estruturado.
  * **Encontrado:** Nenhum botão de exportar relatório.
