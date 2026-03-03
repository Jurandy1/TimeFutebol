# Time Futebol - Sistema de Gestão

Este é um sistema simples para gestão de times de futebol, feito em HTML único (Single Page Application).

## Como publicar no GitHub Pages

1.  Certifique-se de que o arquivo principal se chama `index.html` (tudo minúsculo).
    - **Nota:** O arquivo foi renomeado automaticamente para você nesta correção.
2.  Suba os arquivos para o seu repositório no GitHub.
3.  Vá em **Settings** > **Pages**.
4.  Em **Source**, selecione `Deploy from a branch`.
5.  Em **Branch**, selecione `main` (ou `master`) e a pasta `/ (root)`.
6.  Clique em **Save**.
7.  Aguarde alguns instantes e acesse a URL fornecida (ex: `https://seu-usuario.github.io/seu-repo/`).

## Configuração do Firebase (Banco de Dados e Login)

Para que o sistema funcione com dados reais (Login e Cadastro de Atletas), você precisa configurar o Firebase. É gratuito e fácil.

### Passo 1: Criar Projeto no Firebase
1.  Acesse [console.firebase.google.com](https://console.firebase.google.com/) e faça login com sua conta Google.
2.  Clique em **"Adicionar projeto"**.
3.  Dê um nome (ex: `TimeFutebol`) e continue até criar o projeto.

### Passo 2: Habilitar o Banco de Dados (Firestore)
1.  No menu lateral esquerdo, clique em **Criação** > **Firestore Database**.
2.  Clique em **"Criar banco de dados"**.
3.  Escolha o local (pode deixar o padrão, ex: `us-central1` ou `nam5`).
4.  **Importante:** Na tela de regras de segurança, escolha **"Iniciar no modo de teste"** (isso permite que você comece a usar sem configurar regras complexas agora).
5.  Clique em **Criar**.

### Passo 3: Habilitar Login (Authentication)
1.  No menu lateral esquerdo, clique em **Criação** > **Authentication**.
2.  Clique em **"Vamos começar"**.
3.  Na aba **Sign-in method**, clique em **E-mail/senha**.
4.  Ative a opção **"Ativar"** e clique em **Salvar**.
5.  Vá na aba **Users** e clique em **"Adicionar usuário"**.
6.  Crie o usuário administrador (ex: `admin@time.com` e senha `123456`).

### Passo 4: Conectar ao Código
1.  No menu lateral esquerdo, clique no ícone de engrenagem (Configurações) > **Configurações do projeto**.
2.  Role até o final da página até ver "Seus aplicativos" ou "Não há apps no seu projeto".
3.  Você verá ícones redondos (iOS, Android, Web, Unity). **Clique no ícone `</>` (Web)**.
4.  Dê um nome para o app (ex: `Site`) e clique em **Registrar app**.
5.  O Firebase vai te mostrar um código com `const firebaseConfig = { ... }`.
6.  **Copie apenas o trecho dentro das chaves `{ ... }`**, que se parece com isso:
    ```javascript
    apiKey: "AIzaSy...",
    authDomain: "timefutebol.firebaseapp.com",
    projectId: "timefutebol",
    storageBucket: "timefutebol.appspot.com",
    messagingSenderId: "123456...",
    appId: "1:123456..."
    ```
7.  Abra o arquivo `index.html` do seu projeto.
8.  Procure pelas linhas onde diz `// CONFIGURAÇÃO DO FIREBASE - SUBSTITUA COM SEUS DADOS`.
9.  Cole os seus dados lá.

### Passo 5: Atualizar no GitHub
1.  Salve o arquivo `index.html`.
2.  Faça o commit e push para o GitHub.
3.  Pronto! Seu sistema agora tem login real e banco de dados na nuvem.

## Solução de Problemas

Se a tela ficar branca:
- Adicionamos um sistema de detecção de erros. Se houver algum problema no código, uma mensagem vermelha aparecerá no topo da tela com detalhes do erro.
- Verifique se você está acessando via `https`.
- Limpe o cache do seu navegador (Ctrl+Shift+R).

## Credenciais de Acesso (Padrão Local)

Se não configurar o Firebase, o sistema funciona em modo de teste com:
- **Usuário:** `admin`
- **Senha:** `123456`
