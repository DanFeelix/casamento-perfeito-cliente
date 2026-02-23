# Como o Portal Cliente funciona — e como criar novas telas

## Preciso fazer tudo duas vezes (web e app)?

**Com a estrutura atual, sim:** você tem dois apps (React para web e React Native para mobile), então cada **tela/UI** você implementa uma vez em cada app.

Mas você **não precisa** manter sempre assim. Há três caminhos:

---

### Opção 1 — Escrever uma vez: Web como app (PWA + Capacitor)

**Uma base de código só.** Você desenvolve só o app **web** (React em `apps/web`). Depois usa **Capacitor** para empacotar esse mesmo site como app nativo (Android/iOS). O app mobile é basicamente o site rodando dentro de um app.

- **Vantagem:** uma tela, uma lógica, um código. Ideal para MVP.
- **Desvantagem:** o app não é 100% nativo (menus, gestos, performance podem ser de “página web”).
- **Documento de negócio** (negocio_completo.md) previa exatamente isso: “Web + PWA + Capacitor”.

Nesse cenário você **apaga ou ignora** `apps/mobile` e foca em `apps/web`; o “app” é o build do Capacitor em cima do build da web.

---

### Opção 2 — Escrever uma vez: React Native em todo lugar (Expo + react-native-web)

**Uma base de código só**, mas em **React Native**. Você desenvolve só em `apps/mobile` (React Native + Expo). O Expo consegue rodar o mesmo projeto na **web** (usando `react-native-web`). Ou seja: um conjunto de telas e componentes, que servem web, Android e iOS.

- **Vantagem:** um código, três plataformas; experiência mais “app” em todo lugar.
- **Desvantagem:** você não usa mais “React web clássico” (DOM, CSS); tudo é componente e StyleSheet do React Native. A web fica com cara de app.

Nesse cenário você **não usa** `apps/web` (ou usa só para redirect); o “site” é o build web do projeto React Native.

---

### Opção 3 — Manter dois apps mas compartilhar a lógica (monorepo com pacote shared)

Você **mantém** `apps/web` e `apps/mobile` e aceita que **telas e layout** são feitos duas vezes (web com HTML/CSS, mobile com React Native). Mas toda a **lógica** (chamadas à API, tipos, regras, estado global) fica em um **pacote compartilhado** (ex.: `packages/core` ou `packages/shared`) que os dois apps importam.

- **Vantagem:** UI otimizada para cada plataforma; lógica (login, checklist, orçamento, etc.) escrita uma vez.
- **Desvantagem:** ainda é preciso implementar cada tela duas vezes (uma em React, outra em React Native).

Resumo: **não** precisa fazer **tudo** duas vezes — só a parte de interface; a “cabeça” do app fica compartilhada.

---

### O que escolher?

| Se você quer… | Escolha |
|---------------|--------|
| MVP rápido, menos código, “app = site em um app” | **Opção 1** (Web + Capacitor) |
| Um único código para web e app, com cara de app em todo lugar | **Opção 2** (React Native + web) |
| Experiência web e mobile bem distintas, mas sem repetir regras/API | **Opção 3** (Dois apps + pacote shared) |

---

## O que foi feito (estrutura atual)

O **portal-cliente** é um **monorepo** com dois apps que compartilham o mesmo repositório:

| Pasta | Tecnologia | Uso |
|-------|------------|-----|
| **apps/web** | React + TypeScript + Vite | Site no navegador |
| **apps/mobile** | React Native + Expo | App Android e iOS |

Eles são **independentes**: cada um tem seu `package.json`, suas dependências e sua estrutura. Você pode evoluir a web e o mobile em paralelo (e no futuro compartilhar lógica em um pacote comum, se quiser).

---

## Como funciona a parte Web (React)

### Estrutura de pastas em `apps/web`

```
apps/web/
├── index.html          # Página única (SPA); o React monta em <div id="root">
├── vite.config.ts      # Config do Vite (build, alias @ → src)
├── tsconfig.json       # TypeScript
├── package.json
└── src/
    ├── main.tsx        # Entrada: renderiza <App /> no DOM
    ├── App.tsx         # Router e layout (header + rotas)
    ├── index.css       # Estilos globais
    ├── vite-env.d.ts   # Tipos do Vite
    └── pages/          # Uma pasta por “tela” (páginas)
        ├── Home.tsx
        └── Login.tsx
```

### Fluxo de uma tela

1. **main.tsx**  
   - Lê `index.html`, encontra o `<div id="root">` e monta o React nele, renderizando `<App />`.

2. **App.tsx**  
   - Usa **React Router** (`BrowserRouter`, `Routes`, `Route`).
   - Define o **layout** (cabeçalho “Casamento Perfeito” + área de conteúdo).
   - O conteúdo muda conforme a **URL**:
     - `/` → componente **Home**
     - `/login` → componente **Login**

3. **Cada tela**  
   - É um componente em `src/pages/` (por exemplo `Home.tsx`, `Login.tsx`).
   - Exportado como `export default function NomeDaTela()` e usado em `<Route path="..." element={<NomeDaTela />} />`.

### Alias `@/`

No `vite.config.ts` e no `tsconfig.json` está configurado:

- **`@/`** = **`src/`**

Assim você importa assim:

```ts
import Home from '@/pages/Home'
import Login from '@/pages/Login'
```

Em vez de `'../../pages/Home'`. Facilita mover arquivos sem quebrar imports.

---

## Como criar novas telas (Web)

### Passo 1: Criar o componente da tela

Crie um arquivo em **`apps/web/src/pages/`**, por exemplo **`Checklist.tsx`**:

```tsx
// apps/web/src/pages/Checklist.tsx
export default function Checklist() {
  return (
    <div>
      <h2>Checklist</h2>
      <p>Suas tarefas do casamento.</p>
    </div>
  )
}
```

### Passo 2: Registrar a rota no App.tsx

Em **`apps/web/src/App.tsx`**:

1. Importar o componente:

```ts
import Checklist from '@/pages/Checklist'
```

2. Adicionar uma `<Route>` dentro de `<Routes>`:

```tsx
<Route path="/checklist" element={<Checklist />} />
```

Exemplo completo (trecho):

```tsx
import { BrowserRouter, Routes, Route } from 'react-router-dom'
import Home from '@/pages/Home'
import Login from '@/pages/Login'
import Checklist from '@/pages/Checklist'

function App() {
  return (
    <BrowserRouter>
      <div className="app">
        <header><h1>Casamento Perfeito</h1></header>
        <main>
          <Routes>
            <Route path="/" element={<Home />} />
            <Route path="/login" element={<Login />} />
            <Route path="/checklist" element={<Checklist />} />
          </Routes>
        </main>
      </div>
    </BrowserRouter>
  )
}
```

Depois disso, acessar **http://localhost:3000/checklist** mostra a tela de Checklist.

### Resumo para qualquer nova tela

1. Criar **`apps/web/src/pages/NomeDaTela.tsx`** com `export default function NomeDaTela() { ... }`.
2. Em **App.tsx**: `import NomeDaTela from '@/pages/NomeDaTela'` e `<Route path="/caminho" element={<NomeDaTela />} />`.

---

## Navegação entre telas (links)

Use o componente **Link** do React Router para não recarregar a página:

```tsx
import { Link } from 'react-router-dom'

<Link to="/">Home</Link>
<Link to="/login">Login</Link>
<Link to="/checklist">Checklist</Link>
```

Você pode colocar esses links no header em **App.tsx** ou em um componente compartilhado (ex.: `Layout` ou `Nav`).

---

## Mobile (React Native + Expo)

O app em **apps/mobile** hoje tem um único **App.tsx** na raiz, sem rotas. Para adicionar telas no mobile você pode:

1. Instalar **React Navigation** (já há dependências no `package.json`: `@react-navigation/native`, `react-native-screens`, `react-native-safe-area-context`).
2. Criar componentes de tela em algo como **`apps/mobile/src/screens/`** (ou `screens/` na raiz do app).
3. Configurar um navigator (Stack ou Tab) no **App.tsx** e registrar cada tela.

A lógica é análoga à web: um “roteador” (navigator) + um componente por tela; a diferença é a API (navegação por stack/tabs em vez de URL).

---

## Comandos úteis

| Onde | Comando | O que faz |
|------|---------|-----------|
| Raiz do repo | `npm run web` | Sobe o dev server da **web** (Vite) em http://localhost:3000 |
| Raiz do repo | `npm run mobile` | Sobe o **Expo** (mobile); escanear QR code ou abrir emulador |
| Raiz do repo | `npm run build:web` | Gera build de produção da web em `apps/web/dist` |

Se quiser, no próximo passo podemos: (1) adicionar um menu de navegação no header da web com links para Home, Login e Checklist, ou (2) configurar o React Navigation no mobile e criar a primeira tela extra lá.
