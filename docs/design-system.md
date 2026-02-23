# 📘 Casamento Perfeito App — Design System & Knowledge Base

**Documento de Especificações Visuais para Desenvolvimento com IA**

---

## 1. Visão geral do projeto

### 1.1 Sobre o produto

**Casamento Perfeito App** é uma plataforma mobile e web para organização de casamentos, com foco em casais cristãos que buscam planejamento com propósito, simplicidade e elegância.

### 1.2 Objetivo do design

Criar uma experiência visual que:

- **Reduza ansiedade** → Interface limpa e organizada  
- **Facilite decisões** → Hierarquia clara de informações  
- **Transmita confiança** → Estética profissional e acolhedora  
- **Celebre o momento** → Elementos emocionais sutis  

### 1.3 Público-alvo

- Casais cristãos, primeira vez casando  
- Pouco conhecimento sobre organização de casamentos  
- Buscam orientação e simplicidade  
- Valorizam propósito e significado  

---

## 2. Paleta de cores

### 2.1 Cores principais

| Nome             | Hex Code  | RGB                 | Uso principal                          |
|------------------|-----------|---------------------|----------------------------------------|
| **Sage Green**   | `#8FA89B` | rgb(143, 168, 155)  | Ações primárias, progresso, confirmações |
| **Champagne Beige** | `#F5E9DA` | rgb(245, 233, 218) | Cards, inputs, destaques suaves        |
| **Soft Gold**    | `#C8A96A` | rgb(200, 169, 106)  | IA, premium, elementos especiais      |
| **Charcoal**     | `#2E2E2E` | rgb(46, 46, 46)     | Texto principal                        |
| **Off-White**    | `#FAFAFA` | rgb(250, 250, 250)  | Background principal                   |

### 2.2 Justificativa das cores

#### Sage Green (#8FA89B) — Cor de ação

- Verde representa crescimento, harmonia e novos começos  
- Tom “sálvia” é sofisticado, não infantil  
- Transmite calma e confiança para decisões importantes  
- Contraste adequado com fundo claro para acessibilidade  

**Onde usar:**  
✅ Botões de ação primária (Continuar, Salvar, Confirmar)  
✅ Progress bars e indicadores de progresso  
✅ Estados selecionados em cards e opções  
✅ Ícones ativos na navegação  
✅ Links de destaque  

**Onde NÃO usar:**  
❌ Textos longos (baixo contraste)  
❌ Alertas de erro  
❌ Elementos decorativos excessivos  

#### Champagne Beige (#F5E9DA) — Cor de superfície

- Bege champagne evoca elegância e celebração  
- Mais quente que branco puro, cria acolhimento  
- Referência sutil a casamentos tradicionais  
- Não compete com conteúdo, serve de base  

**Onde usar:**  
✅ Background de cards e containers  
✅ Campos de input (estado padrão)  
✅ Áreas de destaque suave  
✅ Headers de seções  
✅ Progress bar track (fundo)  

**Onde NÃO usar:**  
❌ Texto (invisível no fundo)  
❌ Botões de ação (baixo contraste)  
❌ Ícones pequenos  

#### Soft Gold (#C8A96A) — Cor de destaque especial

- Dourado simboliza valor, celebração e momentos especiais  
- Tom suave evita ostentação excessiva  
- Cria hierarquia para elementos premium/especiais  
- Associação com alianças de casamento  

**Onde usar:**  
✅ Elementos de IA e funcionalidades inteligentes  
✅ Badges premium e planos pagos  
✅ Ilustrações decorativas (anéis, detalhes)  
✅ Estados especiais e celebratórios  
✅ Ícone de sparkle/magia  

**Onde NÃO usar:**  
❌ Botões de ação comum  
❌ Texto de leitura  
❌ Elementos frequentes (perde impacto)  

#### Charcoal (#2E2E2E) — Cor de texto

- Mais suave que preto puro (#000000)  
- Reduz fadiga visual em leitura prolongada  
- Sofisticado e moderno  
- Excelente legibilidade em fundos claros  

**Onde usar:**  
✅ Todo texto principal (títulos, parágrafos)  
✅ Ícones de interface  
✅ Labels e placeholders  
✅ Navegação  

**Variações de opacidade:**  
- 100% → Títulos e texto principal  
- 80% → Texto secundário  
- 60% → Placeholders e hints  
- 40% → Texto desabilitado  

#### Off-White (#FAFAFA) — Cor de background

- Mais suave que branco puro (#FFFFFF)  
- Reduz brilho e cansaço visual  
- Cria sensação de papel/material natural  
- Base neutra para todos os elementos  

**Onde usar:**  
✅ Background principal de todas as telas  
✅ Áreas de respiro visual  
✅ Separação entre seções  

### 2.3 Cores de estado

| Estado       | Cor           | Hex        | Uso                          |
|-------------|---------------|------------|------------------------------|
| **Sucesso** | Sage Green    | `#8FA89B`  | Confirmações, tarefas concluídas |
| **Erro**    | Coral Suave   | `#E07A5F`  | Validações, alertas críticos |
| **Aviso**   | Amber Suave   | `#E9C46A`  | Notificações, atenção        |
| **Info**    | Blue Suave    | `#7BA7BC`  | Dicas, informações neutras |
| **Desabilitado** | Charcoal 40% | `#2E2E2E66` | Elementos inativos       |

---

## 3. Tipografia

### 3.1 Famílias de fonte

**Títulos — Serif elegante**  
- Fonte primária: **Playfair Display**  
- Alternativas: Cormorant Garamond, Libre Baskerville, Lora  

*Por que Serif para títulos?*  
Transmite elegância e tradição, associação com convites de casamento, contraste com texto sans-serif, hierarquia visual clara.

**Texto — Sans-serif moderna**  
- Fonte primária: **Inter**  
- Alternativas: Poppins, Nunito, Open Sans  

*Por que Sans-serif para texto?*  
Alta legibilidade em telas, aparência moderna e limpa, boa renderização em todos os tamanhos, múltiplos pesos disponíveis.

### 3.2 Escala tipográfica

| Elemento        | Fonte    | Tamanho | Peso | Line height | Uso                    |
|----------------|----------|---------|------|-------------|------------------------|
| **H1 - Display** | Playfair | 32px    | 700  | 1.2         | Títulos de tela únicos |
| **H2 - Title**   | Playfair | 24px    | 600  | 1.3         | Perguntas do onboarding |
| **H3 - Subtitle** | Inter   | 20px    | 600  | 1.4         | Subtítulos de seção    |
| **Body Large**   | Inter   | 18px    | 400  | 1.5         | Texto de destaque      |
| **Body**         | Inter   | 16px    | 400  | 1.5         | Texto principal       |
| **Body Small**   | Inter   | 14px    | 400  | 1.5         | Texto secundário       |
| **Caption**      | Inter   | 12px    | 400  | 1.4         | Labels, hints          |
| **Button**       | Inter   | 16px    | 600  | 1.0         | Texto de botões        |

### 3.3 Regras de uso

**Títulos (Playfair Display):**  
- Sempre em Charcoal (#2E2E2E)  
- Centralizado em telas de onboarding  
- Alinhado à esquerda em dashboards  
- Máximo 2 linhas por título  

**Texto (Inter):**  
- Corpo em Charcoal (#2E2E2E)  
- Secundário em Charcoal 80%  
- Placeholder em Charcoal 60%  
- Parágrafos: máximo 65 caracteres por linha  

---

## 4. Espaçamento e grid

### 4.1 Sistema de espaçamento (base 8px)

| Token       | Valor | Uso                         |
|------------|-------|-----------------------------|
| `space-xs` | 4px   | Espaços mínimos internos    |
| `space-sm` | 8px   | Entre ícone e texto         |
| `space-md` | 16px  | Entre elementos relacionados |
| `space-lg` | 24px  | Entre seções               |
| `space-xl` | 32px  | Margens de tela             |
| `space-2xl`| 48px  | Separação de blocos         |

### 4.2 Layout de tela mobile

```
┌─────────────────────────────────┐
│         STATUS BAR              │  ← Sistema (não controlamos)
├─────────────────────────────────┤
│  ← [back]    PROGRESS BAR       │  ← 56px altura (Safe Area)
│         ▓▓▓▓▓▓░░░░░░░░          │  ← Progress: 4px altura
├─────────────────────────────────┤
│                                 │
│  ┌─────────────────────────┐    │  ← Margem: 24px (lateral)
│  │   TÍTULO DA PERGUNTA    │    │  ← Y fixo: 120px do topo
│  │   (Playfair 24px)       │    │
│  └─────────────────────────┘    │
│                                 │  ← Espaço: 32px
│  ┌─────────────────────────┐    │
│  │    ÁREA DE CONTEÚDO     │    │  ← Flex grow (variável)
│  │    (Cards, Inputs)      │    │
│  └─────────────────────────┘    │
│                                 │  ← Espaço: 24px
│       "Ainda não sei"           │  ← Link secundário (opcional)
│                                 │  ← Espaço: 16px
│  ┌─────────────────────────┐    │
│  │       CONTINUAR         │    │  ← Botão primário
│  └─────────────────────────┘    │  ← Margem bottom: 34px (Safe Area)
└─────────────────────────────────┘
```

### 4.3 Especificações de margem

```css
/* Mobile */
--margin-horizontal: 24px;
--margin-top: 16px;
--margin-bottom: 34px; /* Safe area iOS */

/* Tablet */
--margin-horizontal: 48px;
--content-max-width: 600px;

/* Desktop */
--margin-horizontal: 64px;
--content-max-width: 1200px;
--sidebar-width: 280px;
```

---

## 5. Componentes UI

### 5.1 Botões

#### Botão primário

*Uso:* Ação principal da tela (Continuar, Salvar, Confirmar)

- **Background:** Sage Green (#8FA89B)  
- **Texto:** White (#FFFFFF)  
- **Fonte:** Inter 16px SemiBold  
- **Altura:** 56px  
- **Border radius:** 28px (full rounded)  
- **Largura:** 100% (full width) ou auto com padding 24px horizontal  
- **Sombra:** none (design flat)  

**Estados:**  
- Default: #8FA89B  
- Hover: #7A9589 (10% darker)  
- Pressed: #6B8678 (20% darker)  
- Disabled: #8FA89B com 50% opacity  

#### Botão secundário

*Uso:* Ações alternativas, cancelar, voltar

- **Background:** Transparent  
- **Borda:** 1.5px solid Sage Green (#8FA89B)  
- **Texto:** Sage Green (#8FA89B)  
- **Fonte:** Inter 16px SemiBold  
- **Altura:** 56px  
- **Border radius:** 28px  

**Estados:**  
- Default: Border #8FA89B  
- Hover: Background #8FA89B com 10% opacity  
- Pressed: Background #8FA89B com 20% opacity  

#### Botão texto (link)

*Uso:* “Ainda não sei”, “Pular”, links inline

- **Background:** none  
- **Texto:** Charcoal 60% (#2E2E2E99)  
- **Fonte:** Inter 14px Regular  
- **Underline:** none (aparece no hover)  
- **Padding:** 8px vertical  

**Estados:**  
- Default: #2E2E2E99  
- Hover: #2E2E2E + underline  
- Pressed: #2E2E2E  

### 5.2 Cards de seleção

#### Selection card (vertical)

*Uso:* Opções de cerimônia, orçamento, nível de ajuda

- **Background:** Champagne Beige (#F5E9DA)  
- **Border:** 2px solid transparent  
- **Border radius:** 16px  
- **Padding:** 20px  
- **Gap entre cards:** 12px  
- **Largura:** 100%  

**Conteúdo:**  
- Ícone: 24px, Sage Green (#8FA89B), alinhado à esquerda  
- Texto: Inter 16px Medium, Charcoal (#2E2E2E)  
- Subtexto (opcional): Inter 14px Regular, Charcoal 70%  

**Estados:**  
- Default: Background #F5E9DA, Border transparent  
- Hover: Border #8FA89B 50% opacity  
- Selected: Border #8FA89B solid, Background #F5E9DA  
- Disabled: Opacity 50%  

#### Selection card (grid 2×2)

*Uso:* Estilos de casamento, quantidade de convidados

- Mesmo estilo do card vertical  
- **Largura:** calc(50% - 6px)  
- **Gap:** 12px  
- **Altura:** 80px (fixa)  
- Texto centralizado  

### 5.3 Inputs

#### Text input

*Uso:* Nome, email, campos de texto livre

- **Background:** Champagne Beige (#F5E9DA)  
- **Border:** 1.5px solid transparent  
- **Border radius:** 12px  
- **Altura:** 56px  
- **Padding:** 16px horizontal  
- **Fonte:** Inter 16px Regular  

**Placeholder:** Charcoal 50% (#2E2E2E80)  

**Ícone (opcional):** 20px, Charcoal 60%, 16px da borda esquerda  

**Estados:**  
- Default: Border transparent  
- Focus: Border Sage Green (#8FA89B)  
- Error: Border Coral (#E07A5F)  
- Filled: Border transparent, texto Charcoal  

### 5.4 Progress bar

*Uso:* Indicador de progresso no onboarding

- **Track (fundo):** Champagne Beige (#F5E9DA)  
- **Fill (progresso):** Sage Green (#8FA89B)  
- **Altura:** 4px  
- **Border radius:** 2px  
- **Largura:** 100% da tela  
- **Posição:** Topo da tela, abaixo da status bar  

**Comportamento:** Animação ease-out 300ms | 10 etapas = 10% por etapa  

### 5.5 Color swatches

*Uso:* Seleção de cores do casamento

- **Formato:** Círculo  
- **Tamanho:** 48px diâmetro  
- **Border:** 2px solid transparent (default) | 3px solid Sage Green quando selecionado  
- **Gap entre swatches:** 16px  
- **Label:** Inter 12px, Charcoal, centralizado abaixo  

**Cores disponíveis:** Rosa #F4C2C2 | Azul #A8C5D6 | Verde #8FA89B | Dourado #C8A96A | Neutros #F5E9DA  

---

## 6. Iconografia

### 6.1 Estilo dos ícones

- **Estilo:** Line icons (outline)  
- **Stroke width:** 2px (consistente)  
- **Corners:** Rounded  
- **Tamanho base:** 24px  
- **Cor padrão:** Sage Green (#8FA89B)  
- **Cor navegação:** Charcoal (#2E2E2E)  
- **Cor especial IA:** Soft Gold (#C8A96A)  

### 6.2 Biblioteca de ícones

| Categoria  | Ícone          | Arquivo             | Cor            |
|-----------|----------------|---------------------|----------------|
| Navegação | Voltar         | icon-back.png       | Charcoal       |
| Navegação | Home           | icon-home.png       | Sage/Charcoal  |
| Navegação | Perfil         | icon-profile.png    | Sage/Charcoal  |
| Navegação | Configurações  | icon-settings.png   | Sage/Charcoal  |
| Ações     | Check          | icon-check.png      | Sage Green     |
| Ações     | Coração        | icon-heart.png      | Sage Green     |
| Casamento | Anéis          | icon-rings.png      | Sage/Gold      |
| Casamento | Calendário     | icon-calendar.png   | Sage Green     |
| Casamento | Igreja         | icon-church.png     | Sage Green     |
| Casamento | Documento      | icon-document.png   | Sage Green     |
| Casamento | Convidados     | icon-guests.png     | Sage Green     |
| Casamento | Presente       | icon-gift.png       | Sage Green     |
| Casamento | Bolo           | icon-cake.png       | Sage Green     |
| Casamento | Flor           | icon-flower.png     | Sage Green     |
| Casamento | Local          | icon-location.png   | Sage Green     |
| Funcional | Carteira       | icon-wallet.png     | Sage Green     |
| Funcional | Checklist      | icon-checklist.png | Sage Green     |
| Funcional | Câmera         | icon-camera.png     | Sage Green     |
| Funcional | Música         | icon-music.png      | Sage Green     |
| Funcional | Chat           | icon-chat.png       | Sage Green     |
| Funcional | Notificação    | icon-notification.png | Sage Green  |
| Especial  | IA Sparkle     | icon-ai-sparkle.png | Soft Gold      |
| Especial  | Estrela        | icon-star.png       | Sage/Gold      |
| Especial  | Paleta         | icon-palette.png    | Sage Green     |

### 6.3 Regras de uso de ícones

**Tamanhos:**  
- 16px → Ícones inline com texto  
- 20px → Ícones em inputs  
- 24px → Ícones em cards e listas  
- 32px → Ícones de destaque  
- 48px → Ícones de ilustração  

**Cores:**  
- Interface geral → Sage Green (#8FA89B)  
- Navegação inativa → Charcoal 60%  
- Navegação ativa → Sage Green (#8FA89B)  
- Elementos de IA → Soft Gold (#C8A96A)  
- Estados de erro → Coral (#E07A5F)  

---

## 7. Padrões de tela

### 7.1 Template onboarding (padrão fixo)

Toda tela de onboarding **deve** seguir:

1. **Header (fixo)** — Progress bar no topo; botão voltar (exceto tela 1)  
2. **Question (posição fixa)** — Y: 120px do topo; centralizado; Playfair Display 24px  
3. **Content (flexível)** — Área variável; centralizado verticalmente  
4. **Footer (fixo)** — Link “Ainda não sei” (quando aplicável); botão “Continuar”; safe area respeitada  

### 7.2 Tipos de input por tela

| Tela   | Tipo de input   | Componente                |
|--------|-----------------|---------------------------|
| 01 Boas-vindas | CTA único   | Botão primário            |
| 02 Nomes       | Texto       | 2× Text Input             |
| 03 Data        | Seleção     | Date Picker Card          |
| 04 Cerimônia   | Seleção única | 3× Selection Card vertical |
| 05 Convidados  | Seleção única | 4× Selection Card grid 2×2 |
| 06 Orçamento   | Seleção única | 4× Selection Card vertical |
| 07 Estilo      | Seleção única | 4× Selection Card grid 2×2 |
| 08 Cores       | Multi-seleção | 5× Color Swatch + Card IA |
| 09 Ajuda       | Seleção única | 4× Selection Card vertical |
| 10 Confirmação | Display    | Summary Card + CTA         |

---

## 8. Animações e transições

### 8.1 Padrões de animação

```css
--transition-fast: 150ms ease-out;
--transition-normal: 300ms ease-out;
--transition-slow: 500ms ease-out;
```

- Hover em botões: transition-fast  
- Mudança de estado: transition-normal  
- Transição de tela: transition-slow  
- Progress bar: transition-normal  

### 8.2 Transições de tela

**Onboarding:**  
- Entrada: Slide from right + fade in  
- Saída: Slide to left + fade out  
- Duração: 300ms | Easing: ease-out  

**Navegação geral:**  
- Push: Slide horizontal  
- Modal: Slide up + overlay fade  
- Tab switch: Fade crossover  

---

## 9. Acessibilidade

### 9.1 Contraste de cores

| Combinação              | Ratio   | Status            |
|-------------------------|--------|-------------------|
| Charcoal em Off-white   | 12.5:1 | ✅ AAA            |
| Sage Green em Off-white | 3.2:1  | ✅ AA (large text) |
| White em Sage Green     | 4.1:1  | ✅ AA             |
| Soft Gold em Off-white  | 2.8:1  | ⚠️ Apenas decorativo |

### 9.2 Tamanhos mínimos

- Touch target mínimo: 44×44px  
- Texto mínimo legível: 12px  
- Ícones mínimos: 16px  
- Espaço entre elementos tocáveis: 8px  

---

## 10. Prompts de geração

### 10.1 Prompt base para telas de onboarding

```
Mobile app onboarding screen [N] of 10 for 'Casamento Perfeito' wedding app.
iPhone 14 mockup with FIXED LAYOUT PATTERN:

Top has thin linear progress bar ([N*10]% filled sage green #8FA89B on
champagne beige #F5E9DA track), back arrow left.

Title '[PERGUNTA]' in serif 24px centered at fixed Y position.

Content area shows [TIPO DE COMPONENTE]: [DESCRIÇÃO DOS ELEMENTOS].
[Cards/inputs] have champagne beige #F5E9DA background, rounded corners,
sage green border when selected.

Below content: 'Ainda não sei' text link muted charcoal centered.
Fixed bottom: 'Continuar' button full-width sage green #8FA89B.
Background: off-white #FAFAFA. 24px margins. Professional UI.
```

### 10.2 Prompt base para ícones

```
Minimalist line icon of [OBJETO] on completely transparent background.
Single color sage green (#8FA89B) outline style, 2px consistent stroke
weight, no fill. Clean geometric [FORMA] shape with [DETALHES].
Simple, modern, scalable vector-style icon suitable for mobile app UI.
Perfectly centered in square canvas. No shadows, no gradients,
no background - pure transparent PNG style.
Professional app icon design, 64x64px style rendering.
```

---

## 11. Checklist de implementação

Para cada nova tela, verificar:

- [ ] Background é Off-white (#FAFAFA)  
- [ ] Margens laterais são 24px  
- [ ] Título usa Playfair Display 24px  
- [ ] Texto usa Inter nos pesos corretos  
- [ ] Botão primário é Sage Green (#8FA89B)  
- [ ] Cards usam Champagne Beige (#F5E9DA)  
- [ ] Estados de seleção têm borda Sage Green  
- [ ] Espaçamentos seguem múltiplos de 8px  
- [ ] Safe areas respeitadas (top e bottom)  
- [ ] Touch targets mínimo 44px  
- [ ] Elementos de IA usam Soft Gold (#C8A96A)  

---

## 12. Estrutura de arquivos

```
casamento-perfeito-app/
├── assets/
│   ├── icons/
│   │   ├── icon-rings.png
│   │   ├── icon-calendar.png
│   │   ├── icon-church.png
│   │   ├── icon-document.png
│   │   ├── icon-guests.png
│   │   ├── icon-wallet.png
│   │   ├── icon-palette.png
│   │   ├── icon-star.png
│   │   ├── icon-ai-sparkle.png
│   │   ├── icon-heart.png
│   │   ├── icon-check.png
│   │   ├── icon-back.png
│   │   ├── icon-checklist.png
│   │   ├── icon-home.png
│   │   ├── icon-profile.png
│   │   ├── icon-gift.png
│   │   ├── icon-camera.png
│   │   ├── icon-music.png
│   │   ├── icon-flower.png
│   │   ├── icon-cake.png
│   │   ├── icon-location.png
│   │   ├── icon-chat.png
│   │   ├── icon-settings.png
│   │   └── icon-notification.png
│   └── screens/
│       ├── onboarding/
│       │   ├── onboarding-01-welcome.png
│       │   ├── onboarding-02-names.png
│       │   ├── onboarding-03-date.png
│       │   ├── onboarding-04-ceremony.png
│       │   ├── onboarding-05-guests.png
│       │   ├── onboarding-06-budget.png
│       │   ├── onboarding-07-style.png
│       │   ├── onboarding-08-colors.png
│       │   ├── onboarding-09-help.png
│       │   └── onboarding-10-confirmation.png
│       └── template-layout.png
└── docs/
    └── design-system.md
```

---

## 13. Variáveis CSS / tokens

```css
:root {
  /* Cores */
  --color-primary: #8FA89B;
  --color-primary-dark: #7A9589;
  --color-primary-darker: #6B8678;
  --color-secondary: #F5E9DA;
  --color-accent: #C8A96A;
  --color-text: #2E2E2E;
  --color-text-secondary: rgba(46, 46, 46, 0.8);
  --color-text-muted: rgba(46, 46, 46, 0.6);
  --color-text-disabled: rgba(46, 46, 46, 0.4);
  --color-background: #FAFAFA;
  --color-error: #E07A5F;
  --color-warning: #E9C46A;
  --color-info: #7BA7BC;

  /* Tipografia */
  --font-display: 'Playfair Display', serif;
  --font-body: 'Inter', sans-serif;

  /* Tamanhos de fonte */
  --text-h1: 32px;
  --text-h2: 24px;
  --text-h3: 20px;
  --text-body-lg: 18px;
  --text-body: 16px;
  --text-body-sm: 14px;
  --text-caption: 12px;

  /* Espaçamentos */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;

  /* Border radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-full: 9999px;

  /* Transições */
  --transition-fast: 150ms ease-out;
  --transition-normal: 300ms ease-out;
  --transition-slow: 500ms ease-out;

  /* Sombras */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.07);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
}
```

---

*Documento criado para: **Casamento Perfeito App**  
Versão: 1.0 | Data: Fevereiro 2025*

Este documento serve como base de conhecimento para qualquer IA ou desenvolvedor que precise criar novas telas ou componentes para o Casamento Perfeito App, mantendo consistência visual em todo o produto.
