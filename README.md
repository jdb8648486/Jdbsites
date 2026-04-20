# PIXEL.LAB — Site de Agência Web

> Landing page dark/futurista para vender serviços de criação de sites. Pronto para usar, fácil de personalizar.

---

## Visão geral

Site de uma página (single-page) para agências e freelancers que vendem criação de sites. Design dark com estética retro-futurista, animações em CSS/JS puro e foco total em conversão pelo WhatsApp.

**Stack:** HTML · CSS · JavaScript vanilla · Tailwind CDN não utilizado (CSS próprio)  
**Dependências externas:** Google Fonts · Unsplash (imagens)  
**Hospedagem sugerida:** GitHub Pages · Netlify · Vercel (qualquer host de arquivo estático)

---

## Seções

| Seção | Descrição |
|---|---|
| **Hero** | Headline de impacto, CTAs e cards flutuantes com projetos |
| **Ticker** | Faixa de diferenciais em loop contínuo |
| **Problema** | Grid 2×2 comparando site genérico vs. site estratégico |
| **Portfólio** | Scroll horizontal com 6 cards por nicho |
| **Como Funciona** | Processo em 3 etapas com numeração grande |
| **Preços** | 3 planos · Essencial / Profissional / Empresarial |
| **Depoimentos** | 3 cards com foto, nome e resultado |
| **FAQ** | 5 perguntas com accordion animado |
| **CTA Final** | Banner de fechamento com botão WhatsApp |
| **Footer** | Links, contatos e copyright |

---

## Personalização

### 1. Nome da marca

Procure `PIXEL.LAB` no arquivo e substitua pelo seu nome. Aparece em 3 lugares:

```
nav → .nav-logo
footer → .footer-logo
title → <title>
```

### 2. WhatsApp

Todos os botões apontam para o número `5541989017944`. Substitua pelo seu em todos os links:

```
https://wa.me/SEUNUMERO?text=...
```

São **6 ocorrências** no arquivo. Use Ctrl+H para substituir todas de uma vez.

### 3. E-mail

Troque `jdbsites1@gmail.com` pelo seu e-mail. Aparece no footer e no botão de e-mail do CTA final.

### 4. Cores

Definidas como variáveis CSS no `:root`. Mude uma vez, muda em todo o site:

```css
:root {
  --black:  #04040c;   /* fundo da página */
  --blue:   #3b5bfc;   /* cor principal */
  --pink:   #ff2d78;   /* destaque secundário */
  --green:  #00f5a0;   /* confirmações / resultados */
  --white:  #f0f0ff;   /* texto principal */
  --gray:   #8888a8;   /* texto secundário */
}
```

### 5. Fontes

Atualmente usa **Syne** (títulos) + **DM Sans** (corpo), carregadas via Google Fonts. Para trocar, substitua o link no `<head>` e atualize as referências `font-family` no CSS.

### 6. Fotos do portfólio

Cada card usa uma URL do Unsplash. Para trocar por fotos reais dos seus projetos, substitua o atributo `src` de cada `<img class="p-card-img">`:

```html
<!-- antes -->
<img src="https://images.unsplash.com/photo-XXXXXX?w=640&h=360&fit=crop" ...>

<!-- depois -->
<img src="imagens/meu-projeto.jpg" ...>
```

### 7. Preços

Os valores estão em texto puro — sem JavaScript. Localize `R$ 1.000`, `R$ 2.500` e `R$ 5.000` e edite direto.

### 8. Estatísticas do hero

Os contadores animados leem o atributo `data-target`:

```html
<span class="stat-num" data-target="47">0</span>  <!-- projetos entregues -->
<span class="stat-num" data-target="7">0</span>   <!-- dias de entrega -->
<span class="stat-num" data-target="98">0</span>  <!-- % satisfeitos -->
```

Troque os valores de `data-target` pelos seus números reais.

---

## Funcionalidades JS

| Recurso | Como funciona |
|---|---|
| Cursor personalizado | Segue o mouse via `mousemove`. Desabilitado em mobile via `cursor:auto` |
| Reveal on scroll | `IntersectionObserver` adiciona `.visible` nos elementos `.reveal` |
| Contadores animados | `setInterval` incrementa o número até o `data-target` ao entrar na tela |
| FAQ accordion | Toggle da classe `.open` no item clicado, fecha os demais |
| Nav shrink | Listener no `scroll` reduz o padding da nav ao rolar |
| Smooth scroll | Override dos links `href="#ancora"` com `scrollTo()` e offset de 80px |
| Menu mobile | Toggle da classe `.open` no `#mobile-nav` |

---

## Hospedagem no GitHub Pages

```bash
# 1. Crie um repositório público no GitHub
# 2. Suba o arquivo
git init
git add vende_sites.html
git commit -m "primeiro commit"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/SEU_REPO.git
git push -u origin main

# 3. Vá em Settings → Pages → Source: main / root
# 4. Acesse: https://SEU_USUARIO.github.io/SEU_REPO/vende_sites.html
```

---

## Hospedagem na Netlify (arrasta e solta)

1. Acesse [netlify.com/drop](https://app.netlify.com/drop)
2. Arraste o arquivo `vende_sites.html` para a área indicada
3. Seu site fica no ar em segundos com URL gratuita

---

## Estrutura de arquivos sugerida

```
/
├── index.html          ← renomeie vende_sites.html para index.html
├── README.md
└── imagens/            ← pasta para fotos dos seus projetos reais
    ├── projeto-1.jpg
    ├── projeto-2.jpg
    └── ...
```

---

## Checklist antes de publicar

- [ ] Nome da marca substituído
- [ ] Número do WhatsApp atualizado (todas as 6 ocorrências)
- [ ] E-mail atualizado
- [ ] Fotos do portfólio trocadas pelos projetos reais
- [ ] Números dos contadores (`data-target`) atualizados
- [ ] Preços atualizados
- [ ] Depoimentos reais adicionados
- [ ] Testado no celular
- [ ] Testado no Chrome, Firefox e Safari
- [ ] Domínio personalizado configurado (opcional)

---

## Licença

Uso livre para fins comerciais. Não é necessário manter créditos.
