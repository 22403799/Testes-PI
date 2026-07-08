# Sessão de Teste Exploratória 1 — Turistei

- **Data da Sessão:** 08 de Julho de 2026
- **Testadores:** Thays Gomes
- **Objetivo:** Acessar o aplicativo
- **Total de Tempo Alocado:** 15 minutos

---

## Visão Geral

- **Ambiente de Teste:** Aplicativo Móvel e Aplicação Web.
- **Técnica:** Teste Manual.

---

## Sumário de Bugs

**Total de anomalias encontradas: 2**
- BLOQUEANTE: 2
- CRÍTICO: 0
- ALTO: 0

### Bugs Bloqueantes

- **[BUG-01] (BLOQUEANTE) — Crash na inicialização do Aplicativo Móvel**
  - **Passos:**
    1. Efetuar o download e instalação do aplicativo através do link do Google Play Console.
    2. Tentar abrir o aplicativo.
    3. Observar a mensagem de erro do sistema operacional: "O aplicativo fechou porque este app tem um bug. Tente excluir o cache do app primeiro e depois reabra o app.".
    4. Acessar as configurações do Android, realizar a limpeza completa do cache do aplicativo e tentar reabri-lo.
  - **Esperado:** O aplicativo abrir corretamente.
  - **Encontrado:** O aplicativo sofre um crash imediato após a tentativa de abertura.

- **[BUG-02] (BLOQUEANTE) — URL inacessível na Aplicação Web**
  - **Passos:**
    1. Num navegador web, digitar e tentar acessar a URL pública homologada do projeto: `https://sticker-ant-walking-variable.trycloudflare.com/`
    2. Ver mensagem de erro: “Não é possível acessar esse site. Verifique se há um erro de digitação em sticker-ant-walking-variable.trycloudflare.com. DNS_PROBE_FINISHED_NXDOMAIN”*
  - **Esperado:** Abrir o aplicativo web.
  - **Encontrado:** Erro de DNS.
