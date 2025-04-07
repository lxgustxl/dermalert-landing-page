# 🔁 Tutorial CompCriar projeto vite
Guia direto e funcional para:

- Remover tudo (Node, npm, Tailwind, Vite)
- Reinstalar do zero com versões estáveis
- Criar projeto com Vite + Tailwind v3
- Gerar e testar build estático

---

## 🧨 ETAPA 0 — Limpar Tudo do Sistema

### 0.1 Parar servidores de desenvolvimento
Criar projeto vitede.js e npm (Linux)

```bash
sudo apt remove nodejs npm
sudo apt purge nodejs npm
sudo apt autoremove
```

---

### 0.3 Apagar rastros manuais

```bash
sudo rm -rf /usr/local/bin/node
sudo rm -rf /usr/local/bin/npm
sudo rm -rf ~/.npm
sudo rm -rf ~/.nvm
sudo rm -rf ~/.node*
```

---

### 0.4 Verificar se sumiu

```bash
node -v
npm -v
```

Se der "command not found", tá limpo.

---

## 🔧 ETAPA 1 — Reinstalar Node.js com NVM

### 1.1 Instalar NVM

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

### 1.2 Recarregar terminal

```bash
source ~/.nvm/nvm.sh
```

### 1.3 Instalar Node LTS

```bash
nvm install --lts
nvm use --lts
```

### 1.4 Confirmar instalação

```bash
node -v
npm -v
```

---

## 🚀 ETAPA 2 — Criar Projeto com Vite

```bash
npm create vite@latest minha-landing -- --template vanilla
cd minha-landing
npm install
```

---Criar projeto vite

## 🎨 ETAPA 3 — Instalar TailwindCSS v3 (versão estável)

```bash
npm install -D tailwindcss@3.4.1 postcss autoprefixer
npx tailwindcss init -p
```

---

## ⚙️ ETAPA 4 — Configurar o Projeto

### 4.1 Editar `tailwind.config.js`

```js
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

---

### 4.2 Criar `src/style.css`

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

### 4.3 Importar o CSS no `src/main.js`

```js
import './style.css';
```

---

## 💻 ETAPA 5 — Rodar o Projeto

```bash
npm run dev
```

Acesse no navegador: `http://localhost:5173`

---

## 📦 ETAPA 6 — Gerar Build Estático

```bash
npm run build
```

Isso gera a pasta `dist/` com os arquivos finais.

---

## 🔍 ETAPA 7 — Testar o Build Estático Localmente

### Se tiver o `serve` instalado:

```bash
npx serve dist
```

### Se não tiver:

```bash
npm install -g serve
serve dist
```

Abra o link no navegador (geralmente `http://localhost:3000`). Se a landing aparecer corretamente, o build estático tá 100% funcional.

---

Pronto! Seu projeto tá limpo, atualizado e preparado pra produção.  
Se quiser, posso seguir com deploy, layout da landing ou estrutura de componentes — só falar!