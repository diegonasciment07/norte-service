# Design System — Norte Service
**Versão:** 1.0 · **Data:** 2026-05-23

---

## Identidade da Marca

**Posicionamento:** Serviço profissional de manutenção — confiável, ágil, premium.  
**Tom:** Sério e competente, mas acessível e direto.  
**Sentimento:** Segurança + modernidade + eficiência.

---

## Paleta de Cores

### Primárias
| Token | Hex | Uso |
|---|---|---|
| `--ns-black` | `#080C14` | Fundo principal, hero |
| `--ns-navy` | `#0D1B2A` | Seções escuras, header fixo |
| `--ns-navy-mid` | `#142234` | Cards, superfícies |
| `--ns-blue-deep` | `#1E3A5F` | Acentos secundários |

### Accent — Gold
| Token | Hex | Uso |
|---|---|---|
| `--ns-gold` | `#F5A623` | CTAs, destaques, ícones |
| `--ns-gold-light` | `#FFD166` | Hover states, gradientes |
| `--ns-gold-dark` | `#C8861A` | Text on light bg |

### Neutros
| Token | Hex | Uso |
|---|---|---|
| `--ns-white` | `#FFFFFF` | Texto sobre escuro |
| `--ns-off-white` | `#F8F7F4` | Fundo seções claras |
| `--ns-gray-300` | `#A8B0C0` | Texto secundário |
| `--ns-gray-500` | `#6B7585` | Placeholders, notas |

### Funcional
| Token | Hex | Uso |
|---|---|---|
| `--ns-whatsapp` | `#25D366` | Botão WhatsApp |
| `--ns-teal` | `#06D6A0` | Checkmarks, sucesso |
| `--ns-error` | `#EF4444` | Erros de formulário |

---

## Tipografia

### Fontes
- **Display / Títulos:** `Bebas Neue` (Google Fonts) — impacto, identidade
- **Body / Interface:** `Inter` (Google Fonts) — legibilidade, neutralidade

### Escala
| Classe | Tamanho | Uso |
|---|---|---|
| Hero | `clamp(3.5rem, 8vw, 7rem)` | Headline principal |
| Section title | `clamp(2.5rem, 5vw, 4rem)` | Títulos de seção |
| Card title | `1.375rem` | Títulos de cards |
| Body large | `1.0625rem` | Texto corrido |
| Body | `1rem` | Padrão |
| Caption | `0.875rem` | Legendas, labels |
| Tag | `0.75rem` | Badges, labels superiores |

### Regras
- Todos os títulos usam `Bebas Neue` com `letter-spacing: 0.02–0.08em`
- Line-height para títulos display: `0.95–1.0`
- Line-height para body: `1.6–1.7`
- Labels de seção: uppercase + `letter-spacing: 0.15em`

---

## Espaçamento (8pt Grid)

```
4px  · 8px  · 12px · 16px · 24px · 32px
40px · 48px · 64px · 80px · 96px · 128px
```

---

## Bordas e Raios

| Token | Valor | Uso |
|---|---|---|
| `--radius-sm` | `4px` | Badges pequenos |
| `--radius-md` | `8px` | Ícones, logo |
| `--radius-lg` | `16px` | Inputs, cards internos |
| `--radius-xl` | `24px` | Cards, modais |
| `--radius-2xl` | `32px` | Form card, seções |
| `--radius-full` | `9999px` | Botões pill, avatares |

---

## Sombras

| Token | Valor | Uso |
|---|---|---|
| `--shadow-sm` | `0 1px 3px rgba(0,0,0,0.12)` | Micro-elevação |
| `--shadow-md` | `0 4px 16px rgba(0,0,0,0.2)` | Cards |
| `--shadow-lg` | `0 8px 32px rgba(0,0,0,0.3)` | Modais |
| `--shadow-gold` | `0 4px 24px rgba(245,166,35,0.3)` | CTAs gold |
| `--shadow-gold-lg` | `0 8px 40px rgba(245,166,35,0.4)` | CTAs gold hover |

---

## Componentes

### Botões

| Variante | Fundo | Texto | Uso |
|---|---|---|---|
| `btn-gold` | `#F5A623` | Navy | CTA principal |
| `btn-outline` | Transparente | White | CTA secundário |
| `btn-whatsapp` | `#25D366` | White | WhatsApp |

**Tamanhos:** `btn-sm` (32px h) · padrão (48px h) · `btn-lg` (52px h)  
**Forma:** pill (`border-radius: 9999px`)  
**Peso:** `font-weight: 700`, `text-transform: uppercase`, `letter-spacing: 0.04em`

### Cards (Bento Grid)
- Fundo: `--ns-navy-mid`
- Borda: `1px solid rgba(255,255,255,0.06)`
- Hover: borda gold 40%, `translateY(-4px)`, scale da imagem +5%
- Efeito 3D magnetic no mousemove (GSAP)

### Feature Cards
- Borda esquerda animada na entrada (scaleY gold)
- Ícone rotaciona e muda para gold no hover
- Elevação suave no hover

### Formulário
- Input background: `--ns-navy-mid`
- Focus: borda gold + glow `rgba(245,166,35,0.1)`
- Select aparência personalizada

---

## Motion System

### Biblioteca: GSAP + ScrollTrigger

| Animação | Parâmetros | Uso |
|---|---|---|
| Reveal Up | `opacity:0 → 1, y:50 → 0, 0.8s, power3.out` | Texto, seções |
| Reveal Left | `opacity:0 → 1, x:-50 → 0, 0.8s, power3.out` | Colunas esquerdas |
| Reveal Right | `opacity:0 → 1, x:50 → 0, 0.8s, power3.out` | Colunas direitas |
| Reveal Scale | `opacity:0 → 1, scale:0.92 → 1, y:30 → 0, 0.7s` | Cards bento |
| Hero entrance | Timeline sequencial, delay 0.3s | Hero completo |
| Parallax | `yPercent: 20, scrub: true` | Imagem hero |
| Counter | `val: 0 → N, 2s, power2.out` | Números/stats |
| Magnetic hover | `rotateX/Y ±3°, perspective 1000` | Bento cards |

### Keyframes CSS
| Animação | Uso |
|---|---|
| `pulse-dot` | Badge dot piscando |
| `pulse-ring` | Anel do botão WhatsApp flutuante |
| `float` | Indicador de scroll |
| `line-reveal` | Sublinhado do highlight no hero |

---

## Layout

### Grid de Serviços — Bento
- Desktop: 3 colunas, cards "featured" ocupam 2 colunas
- Tablet: 2 colunas
- Mobile: 1 coluna

### Grid de Features
- Desktop: 2 colunas
- Mobile: 1 coluna

### Grid de Stats
- Desktop: 4 colunas na barra gold
- Mobile: 2 colunas

### CTA Section
- Desktop: 2 colunas (texto + form)
- Mobile: 1 coluna empilhada

---

## Roteamento por Cidade (Form)

O formulário detecta a cidade selecionada e redireciona para o WhatsApp correto:
- **Curitiba/PR e região:** `+55 41 99676-8324`
- **Florianópolis/SC e região:** `+55 48 99101-2627`

---

## Responsividade

| Breakpoint | Largura | Mudanças |
|---|---|---|
| Mobile | < 768px | Grids 1 coluna, header CTA oculto |
| Tablet | 768px–1024px | Grids 2 colunas, stats 2×2 |
| Desktop | > 1024px | Layout completo |
