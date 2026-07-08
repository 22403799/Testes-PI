# Sessão de Teste Exploratória 1 — Notificar

- **Data da Sessão:** 08 de Julho de 2026
- **Testador:** Thays Gomes
- **Objetivo:** Avaliar a conformidade visual do modo noturno, fluxos de recuperação de credenciais, responsividade de layout e validação de consistência em cadastros e depoimentos.
- **Total de Tempo Alocado:** 30 minutos

---

## Visão Geral

- **Escopo:** Interface adaptativa, usabilidade, upload de arquivos e regras de negócio de formulários.
- **Ambiente de Teste:** Aplicativo Móvel (Android).
- **Técnica:** Teste Manual Exploratório.

---

## Sumário de Bugs

**Total de anomalias encontradas: 5**
- ALTO: 2
- MÉDIO: 2
- BAIXA: 1

### Bugs de Severidade Alta

- **[BUG-01](https://github.com/22403799/Testes-PI/issues/29) (ALTO) — Permite o cadastro de veículos com placas inválidas fora do padrão**
  - **Passos:**
    1. Acessar o formulário de cadastro de veículos dentro do aplicativo.
    2. Localizar o campo destinado à inserção da placa.
    3. Digitar uma cadeia de caracteres totalmente inválida e fora das normas de trânsito (ex: uma sequência longa como `"ABCDEFGHIJKLMNOPQRSTUVWXYZ"`).
    4. Clicar no botão para salvar o cadastro do automóvel.
  - **Esperado:** O aplicativo deve validar o texto inserido adequadas ao formato brasileiro tradicional (AAA-1234) ou Mercosul (ABC1D23), bloqueando dados inconsistentes.
  - **Encontrado:** O sistema aceita a gravação e armazena o carro com a placa inválida.

- **[BUG-02](https://github.com/22403799/Testes-PI/issues/30) (ALTO) — Barra de status do sistema esconde elementos do aplicativo**
  - **Passos:**
    1. Iniciar a navegação por qualquer uma das telas principais do aplicativo móvel.
    2. Observar o topo da tela onde se localizam as informações nativas do aparelho (relógio, bateria, rede).
  - **Esperado:** O cabeçalho do aplicativo deve respeitar as margens de segurança das áreas seguras da tela, renderizando botões e títulos abaixo da barra de status.
  - **Encontrado:** A barra de status do sistema operacional está sobrepondo áreas e botões críticos localizados na barra superior do aplicativo, inviabilizando cliques e prejudicando a leitura do menu.

### Bugs de Severidade Média

- **[BUG-03](https://github.com/22403799/Testes-PI/issues/31) (MÉDIO) — Quebra de contraste em campos de texto com o modo noturno ativo**
  - **Passos:**
    1. Ativar o "Modo Noturno" do celular.
    2. Abrir o aplicativo e apertar em qualquer tela contendo inputs de texto (como login).
  - **Esperado:** As cores das fontes e dos fundos dos inputs devem inverter harmonicamente de forma a manter uma legibilidade confortável.
  - **Encontrado:** Ocorre uma quebra de contraste nos campos de texto. O fundo ou a cor da tipografia impossibilitam a visualização correta do que está escrito enquanto o aparelho está sob o esquema de cores escuro.

- **[BUG-04](https://github.com/22403799/Testes-PI/issues/32) (MÉDIO) — Card de Depoimento exibe nome genérico "Usuário" em vez do nome real**
  - **Passos:**
    1. Acessar a seção correspondente e redigir um novo depoimento.
    2. Enviar o texto e visualizar a atualização da listagem pública de depoimentos.
  - **Esperado:** O card de depoimento recém-criado deve mostrar o nome do usuário que o fez.
  - **Encontrado:** Embora o depoimento seja salvo com sucesso, o nome `"Usuário"` é mostrado.

### Bugs de Severidade Baixa

- **[BUG-05](https://github.com/22403799/Testes-PI/issues/33) (BAIXA) — Funcionalidade de anexar fotos e vídeos ao Depoimento indisponível**
  - **Passos:**
    1. Navegar até o fluxo que necessita da inserção de evidências ou mídias.
    2. Clicar no ícone ou botão de upload para anexar uma foto ou vídeo da galeria.
  - **Esperado:** O aplicativo deve solicitar as permissões de armazenamento do sistema e abrir o gerenciador de mídias nativo do dispositivo.
  - **Encontrado:** O fluxo é interrompido por um aviso em tela exibindo a mensagem: *“Funcionalidade de anexo em breve”*.
