# Sessão de Teste Exploratória 1 — Open Book Reader

- **Data da Sessão:** 24 de Junho de 2026
- **Testador:** Thays Gomes
- **Objetivo:** Validar fluxo de autenticação, inserção e visualização de PDFs.
- **Total de Tempo Alocado:** 40 minutos

---

## Visão Geral

- **Escopo:** Login, inserção e visualização de PDFs. 
- **Ambiente de Teste:** Android 16 (Samsung S26+), Open Book Reader v0.1.0.
- **Técnica:** Teste Manual.

---

## Sumário de Bugs

**Total de anomalias encontradas: 5**
- ALTO: 2
- MÉDIO: 3

### Bugs Críticos

- **[BUG-01](https://github.com/22403799/Testes-PI/issues/1) (ALTO) — Não permite redefinição de senha esquecida**
  - Passos: 
    1. Na tela de login, aperte "Recuperar".
    2. Na tela de recuperação, digite o e-mail.
    3. Aperte "Verificar e-mail"
  - Esperado: Conseguir fazer a recuperação da senha da conta.
  - Encontrado: Impossível recuperar a conta.

### Observações e Comportamentos Inesperados

- **[BUG-02](https://github.com/22403799/Testes-PI/issues/2) (MÉDIO) — Visualização de PDF cortada quando o celular está no modo Paisagem**
  - Passos: 
    1. Adicione um PDF
    2. Abra o PDF
    3. Rotacione o celular para o modo paisagem (deitado)
  - Esperado: Conseguir ler o PDF inteiro.
  - Encontrado: Visualização do PDF cortada. 

- **[BUG-03](https://github.com/22403799/Testes-PI/issues/3) (MÉDIO) — Botões de Aumentar e Diminuir Zoom não funcionam**
  - Passos: 
    1. Adicione um PDF
    2. Abra o PDF
    3. Aperte no botão de aumentar zoom ou de diminuir zoom.
  - Esperado: Poder manipular o zoom.
  - Encontrado: Botão sem funcionalidade.

- **[BUG-04](https://github.com/22403799/Testes-PI/issues/4) (MÉDIO) — Botão de Favoritar não funciona**
  - Passos: 
    1. Adicione um PDF
    2. Aperte no botão de favoritar (ícone de coração).
  - Esperado: PDF ser marcado como favorito.
  - Encontrado: Botão sem funcionalidade.

- **[BUG-05](https://github.com/22403799/Testes-PI/issues/5) (MÉDIO) — Botão de Configurações não funciona**
  - Passos: 
    1. Faça login
    2. Aperte no botão de configurações.
  - Esperado: Abrir a tela de configurações.
  - Encontrado: Botão sem funcionalidade.
