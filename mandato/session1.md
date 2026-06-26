# Sessão de Teste Exploratória — Mandato Novo

* **Data da Sessão:** 26 de Junho de 2026
* **Testador:** Thays Gomes
* **Objetivo:** Validar fluxos de autenticação, feed de notícias, funcionalidade de busca e responsividade de dashboards.
* **Total de Tempo Alocado:** 30 minutos

---

## Visão Geral

* **Escopo:** Tela de Login, Recuperação de Senha, Feed de Notícias, Sistema de Busca e Dashboard de Insights.
* **Ambiente de Teste:** Android 16 (Samsung S26+)
* **Técnica:** Teste Manual.

---

## Sumário de Bugs

**Total de anomalias encontradas: 7**

* ALTO: 3
* MÉDIO: 5
* BAIXO: 1

### Bugs Críticos

* **[BUG-01](https://github.com/22403799/Testes-PI/issues/7) (ALTO) — Recuperação de senha não implementada**
  * Passos:
    1. Na tela de login, aperte "Esqueci minha senha".
  * Esperado: O sistema deve direcionar o usuário para um fluxo de redefinição de credenciais.
  * Encontrado: A funcionalidade não está implementada no aplicativo.


* **[BUG-02](https://github.com/22403799/Testes-PI/issues/8) (ALTO) — Notícias não atualizam**
  * Passos:
    1. Acessar a tela inicial de notícias.
    2. Tentar recarregar.
  * Esperado: O aplicativo deve trazer as notícias mais recentes.
  * Encontrado: O feed permanece o mesmo, os dados não são atualizados.
 
* **[BUG-03](https://github.com/22403799/Testes-PI/issues/10) (MÉDIO) — Autenticação sucedida mesmo com senha incorreta**
  * Passos:
    1. Inserir um e-mail válido.
    2. Tentar realizar o login com uma senha incorreta.
  * Esperado: Avisar o usuário que as credenciais estão incorretas.
  * Encontrado: O sistema autentica o usuário.

### Observações e Comportamentos Inesperados

* **[BUG-04](https://github.com/22403799/Testes-PI/issues/9) (MÉDIO) — Validação de e-mail insuficiente no Login**
  * Passos:
    1. Na tela de Login, inserir o e-mail no formato "email@email" (sem o .com).
    2. Inserir qualquer senha e confirmar.
  * Esperado: O formulário deve apresentar um erro de validação alertando sobre o formato inválido antes de tentar a submissão.
  * Encontrado: O sistema aceita o texto inválido e prossegue com a autenticação.


* **[BUG-05](https://github.com/22403799/Testes-PI/issues/11) (MÉDIO) — Falha no carregamento das imagens das notícias**
  * Passos:
    1. Navegar pelo feed de notícias ou abrir uma publicação específica.
  * Esperado: As imagens de capa do artigo devem ser exibidas adequadamente.
  * Encontrado: As imagens não carregam, deixando blocos em cinza.


* **[BUG-06](https://github.com/22403799/Testes-PI/issues/12) (MÉDIO) — Dashboard de Insights com gráficos cortados no modo retrato**
  * Passos:
    1. Acessar o Dashboard de Insights.
    2. Manter o celular na orientação vertical.
  * Esperado: Os gráficos são visíveis.
  * Encontrado: Os gráficos ficam cortados, não sendo possível ver todos os dados.

* **[BUG-07](https://github.com/22403799/Testes-PI/issues/13) (BAIXO) — Pesquisa não ignora acentuação**
  * Passos:
    1. Acessar a barra de busca.
    2. Digitar a palavra "transparencia" (sem acento).
  * Esperado: O sistema deve retornar os artigos que contenham a palavra "Transparência" (com acento).
  * Encontrado: Nenhum resultado é exibido.
