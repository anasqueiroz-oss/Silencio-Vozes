# Meu Visual Novel

## Objetivo

Criar um jogo do tipo visual novel: uma história interativa em que o jogador
lê diálogos, vê cenários e personagens e faz escolhas que mudam o rumo da história.

## Como rodar

Frontend:

    cd frontend
    npm install
    npm run dev

Backend (opcional no início):

    cd backend
    npm install
    npm run dev

Antes de rodar o backend, copie `backend/.env.example` para `backend/.env` e preencha os valores.

## O que cada arquivo faz

### Raiz

| Arquivo | Função |
|---|---|
| `README.md` | Explica o projeto (este arquivo) |
| `.gitignore` | Lista o que o Git não deve enviar (`node_modules`, `.env`) |
| `.vscode/extensions.json` | Extensões do VS Code recomendadas para a equipe |

### frontend/

| Arquivo | Função |
|---|---|
| `index.html` | Página única do jogo. O React é montado dentro dela |
| `package.json` | Nome do projeto, bibliotecas usadas e comandos (`npm run dev`) |
| `vite.config.js` | Configuração do Vite (servidor de desenvolvimento) |
| `public/favicon.ico` | Ícone da aba do navegador |
| `src/main.jsx` | Liga o React ao `index.html`. Primeiro arquivo executado |
| `src/App.jsx` | Tela principal. Junta todos os componentes |
| `src/index.css` | Estilos globais (cores, fontes, tela cheia) |
| `src/components/DialogueBox.jsx` | Caixa com o nome de quem fala e o texto |
| `src/components/ChoiceButtons.jsx` | Botões de escolha do jogador |
| `src/components/Menu.jsx` | Menu principal e de pausa |
| `src/core/engine.js` | Controla a história: cena atual, escolhas, save e load |
| `src/core/parser.js` | Lê e valida o roteiro (JSON) |
| `src/story/chapter1.json` | Roteiro do capítulo 1: falas, escolhas e comandos |
| `src/story/characters.json` | Lista de personagens: nome, cor e expressões |

### frontend/src/assets/ (só arquivos de mídia, sem código)

| Pasta | O que guarda |
|---|---|
| `backgrounds/` | Cenários |
| `sprites/` | Personagens e suas expressões |
| `audio/bgm/` | Músicas de fundo |
| `audio/sfx/` | Efeitos sonoros |
| `ui/` | Botões, caixas de diálogo, fontes |

### backend/

| Arquivo | Função |
|---|---|
| `package.json` | Nome, bibliotecas e comandos do servidor |
| `.env` | Senhas e configurações reais. Nunca vai para o Git |
| `.env.example` | Modelo do `.env`, sem valores secretos |
| `src/server.js` | Liga o servidor |
| `src/app.js` | Configura o Express e registra as rotas |
| `src/config/db.js` | Conexão com o banco de dados |
| `src/routes/authRoutes.js` | Endereços de cadastro e login |
| `src/routes/saveRoutes.js` | Endereços de salvar e carregar progresso |
| `src/controllers/authController.js` | Lógica de cadastro e login |
| `src/controllers/saveController.js` | Lógica de salvar e carregar progresso |
| `src/models/User.js` | Como o usuário é guardado no banco |
| `src/models/SaveState.js` | Como o save é guardado no banco |

## Regra principal

A lógica da história fica em `core/`. O visual fica em `components/`. Não misture os dois.