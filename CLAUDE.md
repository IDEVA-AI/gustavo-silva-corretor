# Projeto: Site Gustavo Silva — Corretor de Imoveis

## Sobre o Projeto

Site/landing page para **Gustavo Silva**, corretor de imoveis (CRECI 30517), parceiro oficial **RIVA** e **Direcional**. Foco em captacao de leads qualificados via WhatsApp e catalogo de lancamentos imobiliarios no Distrito Federal.

**Regioes de atuacao:** Planaltina, Sobradinho, Taguatinga, Samambaia, Aguas Claras (DF)

## Stack

- HTML unico, self-contained, sem build step
- Tailwind CSS via CDN (config customizado com tokens do projeto)
- Google Fonts CDN: Inter (300-700) + JetBrains Mono (400-500)
- Vanilla JS (IntersectionObserver, carousel, menu mobile)
- Zero dependencias externas alem dos CDNs

## Estrutura de Arquivos

```
/site/index.html              ← SITE DE PRODUCAO (unico arquivo editavel)
/style-spec.html              ← DESIGN SYSTEM (referencia de tokens — NAO MEXER)
/index.html                   ← Template original ALEX.DESIGN (NAO MEXER)
/design-system.html           ← Design system original (NAO MEXER)
/studio-_-digital-architect/  ← Referencia Studio adaptada (NAO MEXER)
/contexto/briefing-Gustavo.md ← Briefing estrategico completo
/contexto/Empreendimentos/    ← PDFs dos 5 empreendimentos (72MB, maioria visual)
/assets/                      ← Imagens dos empreendimentos + fotos do Gustavo + template
```

**REGRA:** Alteracoes no site sao feitas em `/site/index.html`. Os demais arquivos sao referencia e nao devem ser editados.

## Design System (style-spec.html)

O style-spec define os tokens visuais. O site USA esses tokens mas com layout proprio de landing page (nao replica a estrutura do spec).

### Paleta de Cores

| Token | Hex | Uso |
|-------|-----|-----|
| `primary` | `#016EFF` | CTAs, links, destaques, hover |
| `primary-hover` | `#0058D1` | Hover de primary |
| `secondary` | `#5B75B7` | Labels, badges, icones |
| `secondary-hover` | `#486099` | Hover de secondary |
| `tertiary` | `#CF4B00` | Urgencia, promos, bullets marquee |
| `tertiary-hover` | `#A63C00` | Hover de tertiary |
| `neutral` | `#747781` | Texto secundario |
| `neutral-light` | `#9CA0AC` | Texto terciario, footer |
| `main` | `#EAEAE5` | Fundo principal |
| `whatsapp` | `#25D366` | Botao WhatsApp |
| `stone-900` | `#1c1917` | Texto principal, titulos |
| `stone-300` | `#d6d3d1` | Bordas |

### Animacoes

- **Reveal on scroll:** `.reveal`, `.reveal-left`, `.reveal-right`, `.reveal-scale` (IntersectionObserver, threshold 0.12)
- **Text reveal masked:** `.text-reveal-wrapper` + `.text-reveal-content` (hero titles)
- **Stagger delays:** `.delay-100` ate `.delay-700`
- **Marquee:** `.marquee-container` + `.marquee-content` (loop infinito 40s)
- **Carousel:** `.carousel-slide` com fade (5s interval)
- **Nav:** `.nav-load` com glass on scroll
- **Easing global:** `cubic-bezier(0.16, 1, 0.3, 1)`

### Icones

SVGs inline (Heroicons style). Sem Iconify, sem dependencia de CDN de icones.

## Tom de Comunicacao (Copy)

- **Consultivo**, nao agressivo — "ajudo a decidir", nao "compre agora"
- **Claro e seguro**, sem exageros nem termos tecnicos sem explicacao
- **Foco em beneficio**, nao so caracteristica ("ideal para familias" > "2 quartos")
- **Linguagem:** portugues brasileiro, informal mas profissional
- Tratar dores do publico: medo de financiamento, desconfianca de corretor, duvida sobre regiao

## Publico-Alvo

- Classe media (renda >= R$12k/mes)
- Familias (casal + 1 filho)
- Primeiro ou segundo imovel (apartamentos)
- Busca por qualidade de vida + seguranca

## Empreendimentos

| # | Nome | Localizacao | Construtora | Status | Imagem |
|---|------|-------------|-------------|--------|--------|
| 1 | Total Ville 12 | Planaltina | Direcional | Lancamento | `total-ville-12.png` |
| 2 | Alto da Alvorada | Sobradinho | RIVA | Lancamento | `alto-alvorada.png` |
| 3 | Reserva Parque Clube | Aguas Claras | RIVA | Lancamento Torre 6 | `reserva-parque-clube.png` |
| 4 | Singulare | Samambaia | RIVA | Lancamento | `singulare.png` |
| 5 | Lumi Tower | — | — | Premium | `lumi-fachada.jpeg` |

PDFs em `/contexto/Empreendimentos/` sao majoritariamente visuais (imagens). Apenas Total Ville 12 tem texto extraivel. Dados detalhados serao atualizados manualmente.

### Layout Accordion (desktop)

- **Row 1:** Total Ville 12 (2/3) + Alto da Alvorada (1/3) — accordion por hover
- **Row 2:** Reserva Parque (1/6) + Singulare (1/6) + Lumi Tower (2/3 default) — accordion por hover, Lumi comeca expandido

### Cores por empreendimento

| Empreendimento | Cor primaria | Cor secundaria |
|----------------|-------------|----------------|
| Total Ville 12 | `#C41E5C` | `#E8A723` |
| Alto da Alvorada | `#8B6834` | `#D4A95A` |
| Reserva Parque | `#2D8659` | `#7BC67E` |
| Singulare | `#2C3E6B` | `#8B6F4E` |
| Lumi Tower | `#016EFF` | `#00C2FF` |

## Placeholders Pendentes

| Item | Valor Atual | Onde |
|------|-------------|------|
| WhatsApp | `https://wa.me/55XXXXXXXXXXX` | Todos os CTAs + botao fixo |
| Instagram | `#` | Footer |
| Dados detalhados | Texto generico | Descricoes dos cards |

## Secoes do Site (ordem atual)

1. Header (transparente → glass on scroll)
2. Hero (fullscreen, carousel, stats, badges)
3. Marquee (dark, regioes + construtoras)
4. Proposta de Valor (texto + grid 4 diferenciais)
5. Empreendimentos (dark, accordion 2 rows com hover)
6. Sobre o Gustavo (foto + bio + gallery card stack + trust signals)
7. Regioes (cards com inversao de cor no hover)
8. Depoimento (citacao centralizada)
9. CTA Final (dark, WhatsApp verde + outline)
10. Footer (3 colunas, CRECI, WhatsApp + Instagram)
11. Botao fixo WhatsApp (bottom-right, pulse)

## Verificacao apos alteracoes

1. Abrir `site/index.html` no browser
2. Testar responsivo: 375px, 768px, 1280px
3. Conferir animacoes: nav, hero reveal, scroll reveal, marquee, carousel
4. Menu mobile abre/fecha
5. Todos os hover states
6. WhatsApp fixo visivel e funcional
7. Paleta coerente com style-spec
8. Tom consultivo no copy
