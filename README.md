# Aula ao vivo — Vícios

Página de inscrição da aula gratuita e ao vivo com João Chesca (07/12/2026, 19h30).
Domínio sugerido: https://aula-vicios.joaochesca.com.br/ (definido no arquivo `CNAME`; troque se for usar outro subdomínio, e atualize também `index.html`, `robots.txt` e `sitemap.xml`).

## Link do grupo de WhatsApp

Todos os 5 botões apontam para https://chat.whatsapp.com/JvW173m5JfaBCDAxRlEq2S?s=cl&p=i&iam=2
Para trocar o grupo, use Localizar e substituir em `index.html` (5 ocorrências; no HTML o `&` aparece como `&amp;`).

## Configurações já aplicadas

- Cor do módulo Vícios: `#1E63F3` (azul), com a moldura de contorno + dois pontos da capa do módulo.
- Meta Pixel: 1242073104404770 — dispara `PageView` ao abrir e `Lead` ao clicar em qualquer botão do grupo (com `content_category` indicando qual botão: topo, hero, aprender, professor, cta-final).
- Microsoft Clarity: ativo (ID y188sn6vbg, o mesmo da PV Behave).
- SEO: título, descrição, Open Graph, `og-image.jpg` (1200x630) e JSON-LD do tipo `Event` (gratuito, online).
- Os botões abrem o WhatsApp em nova aba, para o Pixel registrar o Lead antes de sair da página.

## Estrutura

```
/ (raiz do repositório)
├── CNAME              aula-vicios.joaochesca.com.br
├── .nojekyll
├── index.html
├── robots.txt / sitemap.xml / site.webmanifest
├── favicon.ico, favicon-*.png, apple-touch-icon.png, android-chrome-*.png
├── og-image.jpg       prévia no WhatsApp/Instagram
└── assets/
    ├── joao-chesca.webp
    ├── logo-behave-branco.webp
    └── simbolo-behave-branco.webp
```

## Publicação (GitHub Pages + Cloudflare)

1. Criar repositório **público** no GitHub (ex.: `aula-vicios`).
2. Add file → Upload files → arrastar **o conteúdo** desta pasta (não a pasta em si). O `.nojekyll` é oculto no Mac: `Cmd + Shift + .` no Finder para enxergá-lo.
3. Settings → Pages → Source: branch `main`, pasta `/ (root)` → Save.
4. Cloudflare → DNS do `joaochesca.com.br` → novo registro **CNAME**: nome `aula-vicios`, destino `SEU_USUARIO.github.io`, **DNS only (nuvem cinza)**.
5. GitHub → Settings → Pages → Custom domain: `aula-vicios.joaochesca.com.br` → aguardar "DNS check successful".
6. Marcar **Enforce HTTPS** quando liberar.
7. Validar: cadeado HTTPS, Meta Pixel Helper (PageView + Lead no clique), prévia colando o link no WhatsApp, sessão no Clarity.

Depois da aula, dá para trocar a página por um aviso de "aula encerrada" ou redirecionar para a PV da Behave.
