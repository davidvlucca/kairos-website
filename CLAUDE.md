# Kairos — Projeto

## Visão Geral
Landing page de vendas + página de briefing para o serviço **Kairos** de David Lucca.
Kairos cria sites/landing pages rápidos para pequenos negócios, entregues em 72h.

## URLs
- **Produção:** https://kairos-sell.vercel.app
- **Briefing:** https://kairos-sell.vercel.app/briefing
- **GitHub:** https://github.com/davidvlucca/kairos-website

## Stack
- Astro 6 + Tailwind v4
- Deploy: Vercel (auto-deploy do branch `main`)
- Forms: Web3Forms → email para o proprietário
- Sem framework JS — vanilla scripts inline em cada componente

## Env Vars (Vercel + .env local)
- `PUBLIC_WHATSAPP_NUMBER` = 351968038514
- `PUBLIC_WEB3FORMS_KEY` = 27c0d8d8-9be5-45cc-a491-f3594ae056fe

## Estrutura de Ficheiros
```
src/
  pages/
    index.astro        — landing page principal
    briefing.astro     — formulário de briefing para clientes
  components/
    Nav.astro          — navbar fixa com hamburger mobile
    Hero.astro         — secção hero com parallax
    HowItWorks.astro   — 3 passos do processo
    KairosInterlude.astro
    Pricing.astro      — cards de planos + add-ons
    Requirements.astro — o que o cliente precisa de fornecer
    Portfolio.astro    — trabalhos (Celso Barber + placeholder)
    FAQ.astro          — accordion de perguntas frequentes
    ContactForm.astro  — formulário de contacto (Web3Forms)
    FinalCTA.astro
    Footer.astro
  styles/
    global.css         — tokens, glass cards, botões, form inputs
  layouts/
    Layout.astro       — html base com Inter font
```

## Planos e Preços
| Plano | Preço | Inclui |
|---|---|---|
| Essencial | €197 | Landing page 1 página, design responsivo, formulário, entrega 72h, 1 revisão |
| Completo | €447 | Website 3–5 páginas, automações n8n, 3 revisões |

**Pagamento:** 50% na contratação · 50% na aprovação final

**Revisões adicionais:** €50/alteração ou €20/hora

## Opcionais (Add-ons)
| Opcional | Preço | Detalhe |
|---|---|---|
| Logo Pack | +€100 | Logo + paleta de cores + tipografia. Sem ilustração, mascote ou monograma. Parceiro: Marcus Castro (Brand Designer) |
| Fotografia Profissional | +€50 | Sessão em estúdio Cascais, até 30min, até 4 fotos tratadas |

## Parceiros
- **Marcus Castro** — Brand Designer (Logo Pack). Pai do David, ajudou a criar o briefing inicial.
- **Fotógrafo em Cascais** — sessão fotográfica (parceria)

## Design System
- Background: `#080808`
- Cards: glassmorphism (`.glass`) — `rgba(255,255,255,0.04)` + blur
- Accent: branco puro `#ffffff`
- Font: Inter (Google Fonts)
- Botões: `.btn-primary` (branco sólido) e `.btn-ghost` (outline)
- Sem emojis nos componentes (exceto info boxes no briefing)

## Briefing (/briefing)
Formulário para clientes preencherem após contratar. 6 secções:
1. **Sobre ti** — nome, email, WhatsApp (dropdown país), plano de interesse
2. **O negócio** — marca, área, descrição, serviços, línguas do site (PT/EN/ES)
3. **Presença digital** — site existente, domínio, alojamento
4. **Identidade & conteúdo** — logo (formatos), fotos, add-ons opcionais
5. **Informações para o site** — contactos públicos, redes sociais
6. **FAQ & notas** — opcional

Condições de pagamento mostradas antes do botão de envio.
Dropdown de país com 43 países, Portugal por defeito, com search.

## Convenções de Código
- Styles inline com `style=""` para one-offs; CSS scoped por componente para padrões reutilizáveis
- Scripts vanilla no final de cada componente com `document.addEventListener('DOMContentLoaded', ...)`
- Sem comentários desnecessários
- Sem TypeScript externo — tipos inline nos scripts Astro quando necessário
