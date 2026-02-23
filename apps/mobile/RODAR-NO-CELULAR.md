# Rodar o app no celular (Expo Go)

Se o QR code não conecta ou dá tela azul, siga estes passos na ordem.

---

## 1. Mesmo Wi‑Fi

- Celular e PC **precisam estar no mesmo Wi‑Fi** (mesma rede).
- Não use dados móveis no celular; desative “dados móveis” para forçar Wi‑Fi.

---

## 2. Descobrir o IP do PC

No **PowerShell** ou **Prompt de comando** no Windows:

```powershell
ipconfig
```

Procure **Adaptador de rede sem fio Wi-Fi** (ou **Ethernet** se o PC estiver no cabo). Anote o **Endereço IPv4**, algo como `192.168.1.100` ou `192.168.0.50`.

---

## 3. Liberar a porta 8081 no firewall

O Metro (Expo) usa a porta **8081**. O Windows pode estar bloqueando.

1. Pressione **Win**, digite **firewall** e abra **Firewall do Windows Defender com Segurança Avançada**.
2. Clique em **Regras de Entrada** (lado esquerdo).
3. No lado direito, clique em **Nova Regra...**.
4. Escolha **Porta** → Avançar.
5. Marque **TCP**, em “Portas locais específicas” digite **8081** → Avançar.
6. Marque **Permitir a conexão** → Avançar.
7. Deixe as três opções marcadas (Domínio, Particular, Público) → Avançar.
8. Nome: por exemplo **Expo Metro 8081** → Concluir.

---

## 4. Subir o Expo com cache limpo

Na **pasta do repositório** (onde está o `package.json` raiz):

```bash
npm run mobile:clear
```

Ou, entrando na pasta do app:

```bash
cd apps/mobile
npx expo start --clear
```

Deixe o terminal aberto. Vai aparecer um **QR code** e uma URL tipo:

```
exp://192.168.1.100:8081
```

(O número será o **IPv4** do seu PC.)

---

## 5. Abrir no Expo Go pela URL

1. No **celular**, abra o app **Expo Go**.
2. Toque em **“Enter URL manually”** / **“Inserir URL manualmente”** (ou algo parecido na tela inicial).
3. Digite exatamente a URL que apareceu no terminal, por exemplo:
   ```
   exp://192.168.1.100:8081
   ```
   (use **o IP do seu PC** no lugar de 192.168.1.100).
4. Toque em **Conectar** / **Connect**.

O app deve carregar. Se aparecer “Connection refused” ou “Unable to connect”, o celular não está alcançando o PC — confira Wi‑Fi, IP e firewall.

---

## 6. Se ainda não funcionar: emulador no PC

Assim você não depende do celular nem da rede:

1. Instale o **Android Studio** e crie um **AVD** (emulador Android), ou use o **Xcode** no Mac para o simulador iOS.
2. Com o Expo rodando (`npm run mobile` ou `npm run mobile:clear`), no terminal pressione:
   - **`a`** para abrir no **emulador Android**
   - **`i`** para abrir no **simulador iOS** (só no Mac)

O app abre no emulador na mesma máquina.

---

## Resumo rápido

| Passo | O que fazer |
|-------|-------------|
| 1 | PC e celular no **mesmo Wi‑Fi** |
| 2 | `ipconfig` → anotar **IPv4** do PC |
| 3 | Firewall: permitir **TCP 8081** (entrada) |
| 4 | `npm run mobile:clear` e deixar rodando |
| 5 | No Expo Go: **Enter URL manually** → `exp://SEU_IP:8081` |
