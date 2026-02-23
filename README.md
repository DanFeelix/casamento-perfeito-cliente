# Portal Cliente — Casamento Perfeito App

Portal do **casal** (cliente): aplicação Web (React) e Mobile (React Native) para Android e iOS.

Baseado no [documento de negócio](../../negocio_completo.md) e escopo MVP: cadastro, login, perfil do casamento, checklist, orçamento e sugestões com IA.

## Estrutura (monorepo)

- **apps/web** — React + TypeScript + Vite (web)
- **apps/mobile** — React Native + Expo (Android e iOS)

## Pré-requisitos

- Node.js 18+
- npm 9+ (ou yarn/pnpm)
- Para mobile: Android Studio e/ou Xcode (simuladores); ou Expo Go no celular

## Como rodar

```bash
# Instalar dependências (na raiz)
npm install

# Web
npm run web
# ou: cd apps/web && npm run dev

# Mobile (Expo) — use este (LAN). Não use mobile:tunnel; o tunnel costuma falhar.
npm run mobile
# ou: cd apps/mobile && npm run start
# Depois: escanear QR code com Expo Go (celular no mesmo Wi‑Fi) ou Pressionar 'a' (Android) / 'i' (iOS)
```

### Se o app não carregar no celular (Expo Go)

**Guia completo:** [apps/mobile/RODAR-NO-CELULAR.md](apps/mobile/RODAR-NO-CELULAR.md) — IP do PC, firewall, URL manual, emulador.

Resumo:
1. **Use a mesma rede Wi‑Fi:** PC e celular no mesmo Wi‑Fi.
2. **Firewall do Windows:** permita Node/JavaScript (ou a porta **8081**) no firewall. Em “Aplicativos permitidos”, inclua o executável do Node ou crie regra de entrada para a porta 8081 (TCP).
3. **URL manual no Expo Go:** no terminal, o Expo mostra algo como `exp://192.168.x.x:8081`. No Expo Go, toque em “Enter URL manually” e digite essa URL.
4. **Tunnel falhou?** O comando `npm run mobile:tunnel` usa ngrok e pode dar erro (“failed to start tunnel” / “remote gone away”). Nesse caso use o modo LAN acima. Em rede corporativa ou com restrições, o tunnel costuma falhar.
5. **Emulador no PC:** sem depender da rede: Android Studio (AVD) ou Xcode (simulador). Com o Expo rodando, pressione `a` (Android) ou `i` (iOS) no terminal para abrir no emulador.

### Tela azul no Expo Go (“voltar para home”)

1. **Atualize o Expo Go** no celular (App Store / Play Store) — o projeto usa SDK 54; o app precisa estar em dia.
2. **Limpe o cache e suba de novo:** na pasta `apps/mobile` rode `npx expo start --clear` e escaneie o QR de novo.
3. Foi adicionado **metro.config.js** para monorepo; se o erro continuar, feche o Expo no celular, pare o terminal (Ctrl+C), rode de novo `npm run mobile` na raiz e teste outra vez.

## Build

```bash
npm run build:web    # gera dist em apps/web
npm run build:mobile # expo export em apps/mobile
```

## Próximos passos (MVP)

- Telas: Login/Registro, Onboarding, Home, Checklist, Orçamento, Perfil
- Integração com API (backend compartilhado)
- Autenticação JWT

---

**Repositório independente** — subir este folder no GitHub como repositório separado.
