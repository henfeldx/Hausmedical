# Prompt Final — Site Institucional/E-commerce da Hausmedical

Este arquivo contém o prompt completo, autossuficiente, para gerar o site da **Hausmedical**. Ele foi construído a partir da pesquisa em `pesquisa-concorrentes-hausmedical.md` (concorrentes de Manaus/AM e referências nacionais) e da identidade da marca.

Use este prompt como briefing para uma equipe de design/dev, um builder de IA ou uma ferramenta como v0, Lovable, Cursor, etc.

---

## PROMPT

Você é um time sênior de design e desenvolvimento web (UX/UI + front-end + SEO técnico). Sua missão é entregar o **site institucional e e-commerce B2B da Hausmedical**, uma empresa de móveis e equipamentos hospitalares sediada em Manaus/AM que atende clínicas, hospitais, home care e órgãos públicos em todo o Norte do Brasil, com potencial nacional.

O site precisa **superar todos os concorrentes locais** (Ortosena, NS Hospitalar, MEM Cirúrgica, AG Compani Hospitalar, Hosp Line, SSB) **e igualar os concorrentes nacionais** (Prado Hospitalar, BR Cirúrgica) em experiência de compra — mantendo o posicionamento local que só a Hausmedical pode oferecer.

---

### 1. Marca e identidade visual

**Nome:** Hausmedical
**Assinatura:** "Produtos Hospitalares"
**Logo:** cruz médica estilizada em azul + verde, seguida do nome "HAUSMEDICAL" em azul escuro e do subtítulo "PRODUTOS HOSPITALARES" em cinza. Use o SVG oficial em duas versões (colorida em fundo claro, branca em fundo escuro).

**Paleta oficial (usar como CSS custom properties):**

```css
:root {
  --color-primary:   #005691; /* Azul Hospitalar — headers, botões primários, links */
  --color-secondary: #8FBC8F; /* Verde Suave — destaques, sucesso, ícones */
  --color-neutral:   #D3D3D3; /* Cinza Frio — bordas, backgrounds sutis */
  --color-surface:   #FFFFFF; /* Branco Limpo — background principal */
  --color-ink:       #0F2740; /* Azul quase-preto para texto principal */
  --color-muted:     #5A6A7A; /* Cinza texto secundário */
}
```

Regras de uso:
- **Azul #005691** domina headers, CTAs primários, links, ícones institucionais.
- **Verde #8FBC8F** aparece em confirmações, badges "Anvisa", ícones de qualidade e como acento em imagens.
- **Cinza #D3D3D3** só em bordas, separadores, backgrounds sutis (nunca em texto).
- **Branco #FFFFFF** é o fundo padrão. Uso generoso de espaço em branco (hospitalar = limpo).
- Contraste mínimo **WCAG AA 4.5:1** em todo texto.

**Tipografia:**
- **Heebo** — títulos (H1, H2, H3), botões, números institucionais. Pesos 500/700/800.
- **Montserrat** — corpo de texto, parágrafos, labels, meta. Pesos 400/500/600.
- Carregar via `<link rel="preconnect">` do Google Fonts com `display=swap` e apenas os pesos usados.
- Escala tipográfica fluida com `clamp()` (ex.: `clamp(2rem, 4vw, 3.5rem)` para H1).

**Tom de comunicação:**
- Profissional, técnico, direto — sem jargão de marketing agressivo.
- Palavras-chave: precisão, confiança, cuidado, qualidade certificada, atendimento local.
- Nunca prometer o que não pode entregar; sempre citar norma, prazo, garantia.

---

### 2. Estrutura de páginas

1. **Home (/)**
2. **Catálogo/Produtos (/produtos)** com sub-rotas por categoria (`/produtos/camas-hospitalares`, `/produtos/carrinhos-de-emergencia`, etc.).
3. **Página de produto individual (/produtos/[slug])**.
4. **Segmentos/Especialidades (/segmentos)** com sub-rotas: `/segmentos/uti`, `/segmentos/centro-cirurgico`, `/segmentos/home-care`, `/segmentos/consultorio`, `/segmentos/enfermaria`.
5. **Sobre (/sobre)** — história, missão, valores, números, equipe, fábrica/estoque.
6. **Certificações e Qualidade (/qualidade)** — Anvisa, ISO 9001, ISO 13485, garantias.
7. **Serviços (/servicos)** — locação de equipamentos, manutenção preventiva/corretiva, consultoria de layout, montagem/entrega em Manaus.
8. **Blog/Conteúdo Técnico (/blog)** — pautas de SEO local e técnico.
9. **Orçamento / Contato (/orcamento)** — formulário + WhatsApp + telefone + endereço + mapa.
10. **Área do Cliente (/area-do-cliente)** — login, pedidos, notas fiscais, chamados, orçamentos salvos, agendamento de manutenção.
11. **FAQ (/faq)**
12. **Políticas** (`/politica-de-privacidade`, `/politica-de-trocas`, `/termos-de-uso`) — LGPD compliant.

---

### 3. Home — seções obrigatórias (na ordem)

1. **Hero** com headline forte ("Móveis e equipamentos hospitalares para quem não pode errar"), sub-headline mencionando Manaus e Norte do Brasil, CTA primário "Solicitar orçamento" (leva a `/orcamento`), CTA secundário "Ver catálogo". Imagem/vídeo curto de ambiente hospitalar real, não de banco de imagens genérico.
2. **Barra de confiança** com selos: Anvisa (com nº de registro), ISO 9001, ISO 13485, Reclame Aqui, Google Reviews. Todos clicáveis.
3. **Categorias em destaque** (grid de 8 cards): Camas Hospitalares, Macas, Carrinhos de Emergência, Armários e Gaveteiros, Mesas Cirúrgicas, Cadeiras de Rodas, Biombos, Suportes de Soro. Cada card com ícone + foto de produto + CTA.
4. **Segmentos atendidos** (UTI, Centro Cirúrgico, Home Care, Consultório, Enfermaria) — 5 cards clicáveis para as respectivas LPs.
5. **Diferenciais** (4 blocos com ícone + título curto + 1 linha): "Estoque em Manaus", "Montagem e entrega grátis no AM", "Assistência técnica própria", "Faturamento CNPJ e órgãos públicos".
6. **Prova social**: logos de hospitais/clínicas atendidos + 3 depoimentos com nome, cargo, instituição e foto.
7. **Cases/números** em contadores: anos de mercado, produtos entregues, cidades atendidas, clientes ativos.
8. **Blog em destaque** (3 posts mais recentes).
9. **CTA final** "Precisa equipar sua unidade? Fale com um especialista" com formulário curto (nome, telefone, e-mail, tipo de unidade) + botão WhatsApp.
10. **Footer** completo (ver seção 8).

---

### 4. Catálogo — funcionalidades obrigatórias

- **Menu de categorias sticky** à esquerda em desktop, drawer em mobile.
- **Filtros dinâmicos:** categoria, especialidade (UTI/Cirurgia/Home Care), material (aço inox, ferro pintado, ABS), peso suportado, motorização (manual/elétrica), norma Anvisa/RDC, faixa de preço "a partir de", em estoque em Manaus (sim/não), garantia (12/24/36 meses).
- **Ordenação:** relevância, mais vendidos, novidades, menor prazo de entrega.
- **Card do produto** com: foto principal, nome, código SKU, categoria, badge de certificação, prazo de entrega estimado para Manaus, CTA "Adicionar ao orçamento" (não "comprar" — B2B consultivo).
- **Cotação múltipla:** o cliente monta uma lista de itens no orçamento e envia tudo em 1 clique (form + WhatsApp + e-mail). Persistir carrinho em `localStorage` + na conta se logado.
- **Comparador de até 4 produtos** com tabela lado a lado (dimensões, peso, garantia, material, norma).
- **Busca com autocomplete** e correção de digitação; suporte a SKU, nome, sinônimos (ex.: "cama motorizada" ↔ "cama elétrica").
- **Paginação com scroll infinito** + fallback numérico para SEO.

**Página de produto individual:**
- Galeria com zoom + foto 360° quando disponível.
- Ficha técnica: dimensões, peso, capacidade, material, acabamento, motor, norma RDC aplicável, ANVISA nº, garantia, prazo.
- CTA duplo: "Adicionar ao orçamento" (primário) + "Consultar por WhatsApp" (secundário).
- Downloads: manual em PDF, certificado, ficha técnica.
- Produtos relacionados + produtos frequentemente comprados juntos.
- Perguntas e respostas do produto (Q&A moderado).
- Vídeo do produto quando existir.
- Schema.org `Product` + `Offer` + `AggregateRating` + `Breadcrumb` completos.

---

### 5. Fluxo de orçamento (o coração do B2B)

1. Cliente adiciona N produtos ao **carrinho de orçamento** (não é checkout de pagamento).
2. Em `/orcamento`, revisa itens, ajusta quantidades, adiciona observações.
3. Preenche: razão social, CNPJ, tipo de unidade (hospital privado, público, clínica, home care, consultório), cidade, contato, prazo desejado.
4. Ao enviar: (a) e-mail para vendas@hausmedical, (b) mensagem pré-formatada abre no WhatsApp com resumo, (c) confirmação na tela + PDF do pedido para download, (d) registro na área do cliente se logado.
5. Follow-up automático por e-mail em 24h com prazo de resposta.

---

### 6. Credibilidade e conformidade (o diferencial vs. concorrentes locais)

- Página `/qualidade` com **números de registro Anvisa clicáveis** que abrem a consulta pública oficial, ISO 9001 e ISO 13485 com PDF do certificado.
- Selo Reclame Aqui, Google Reviews (widget), LGPD compliance visível.
- Banner de cookies com opt-in granular (essenciais/analíticos/marketing).
- Página `/sobre` com **fotos reais** da equipe, do estoque em Manaus, da fábrica (se houver) — nunca banco de imagens.
- Números institucionais **preenchidos e datados** (evitar o erro da NS Hospitalar com "0 anos").
- **Cases**: mínimo 6 hospitais/clínicas com logo autorizado + relato curto.
- Certidões negativas (CND) disponíveis para download por CNPJ (importante em vendas públicas).

---

### 7. Conteúdo, SEO e performance

- **Blog** com categorias: Regulamentação (Anvisa/RDC), Guia de compra, Manutenção, Cases, Notícias do setor.
- Pautas locais obrigatórias na abertura: "Como equipar uma UTI no Amazonas", "Manutenção preventiva de cama motorizada em clima úmido", "Guia Anvisa para clínicas em Manaus", "Como comprar equipamento hospitalar por licitação em Manaus".
- **SEO técnico:** `sitemap.xml`, `robots.txt`, meta tags OpenGraph + Twitter Card, schema.org `LocalBusiness` no rodapé, `BreadcrumbList` em todo lugar, `Product`/`Offer`/`Review` no catálogo, `Article` no blog, canônicas corretas, URLs limpas em kebab-case, hreflang `pt-BR`.
- **Palavras-chave alvo:** "móveis hospitalares Manaus", "camas hospitalares Manaus", "equipamentos hospitalares Amazonas", "fornecedor hospitalar Norte", "cadeira de rodas Manaus", "carrinho de emergência Manaus" + variações long-tail no blog.
- **Google Business** integrado (mapa + horários + reviews na home e no `/contato`).
- **Performance:** Core Web Vitals verdes — LCP < 2.5s, INP < 200ms, CLS < 0.1. Imagens em WebP/AVIF com `srcset` + lazy loading nativo, fontes com `font-display: swap` e subset latin, JS crítico inline, resto com `defer`, CSS crítico inline < 14kb.
- Stack recomendada: Next.js 15 (App Router) + TypeScript, Tailwind CSS (com os tokens da paleta oficial), imagens via `next/image`, ISR para catálogo, edge cache para páginas estáticas, hospedagem Vercel/Netlify + CDN.

---

### 8. Footer

- Coluna 1 — Institucional: Sobre, Qualidade, Serviços, Blog, Trabalhe conosco.
- Coluna 2 — Catálogo: principais categorias.
- Coluna 3 — Segmentos: UTI, Centro Cirúrgico, Home Care, Consultório.
- Coluna 4 — Atendimento: WhatsApp com botão, telefone comercial, e-mail, horário, endereço em Manaus com link Google Maps, mapa mini incorporado.
- Barra inferior: CNPJ, razão social, selos Anvisa/ISO, ícones de redes sociais (Instagram, LinkedIn, YouTube), políticas, LGPD.
- Copyright + "Desenvolvido em Manaus".

---

### 9. Área do cliente (diferencial pós-venda)

- Login por e-mail/senha + Google.
- Dashboard: pedidos, orçamentos salvos, notas fiscais em PDF.
- **Chamados de assistência técnica** com abertura, acompanhamento e histórico (inspirado no "Meus Chamados" da NS Hospitalar, mas melhor).
- **Agendamento de manutenção preventiva** com calendário.
- Cadastro de múltiplos CNPJs sob a mesma conta (matriz + filiais).
- Recompra em 1 clique (pedidos anteriores).

---

### 10. Mobile-first e acessibilidade

- Todas as telas desenhadas primeiro em 375px de largura.
- Botão WhatsApp flutuante fixo mobile (canto inferior direito, contraste AA, aria-label descritivo).
- Menu hambúrguer com busca no topo.
- Sticky bar inferior no mobile: "Ver orçamento (N)" + "WhatsApp".
- **WCAG 2.1 AA:** foco visível, navegação por teclado 100%, `aria-*` correto, `alt` descritivo em toda imagem de produto, contraste AA mínimo, suporte a leitor de tela testado (NVDA/VoiceOver), `prefers-reduced-motion` respeitado.
- Suporte a dark mode opcional (não obrigatório na v1, mas deixar tokens preparados).

---

### 11. Integrações e stack de backend

- **CMS headless** para catálogo e blog (Sanity, Contentful, ou Payload) — permite equipe interna cadastrar produto sem dev.
- **CRM/Vendas:** integração com HubSpot ou Pipedrive via API para receber leads do formulário de orçamento.
- **WhatsApp Business API** (via Z-API, Twilio ou Meta Cloud API) para envio automático da cotação e follow-up.
- **E-mail transacional:** SendGrid ou Resend.
- **Analytics:** GA4 + Google Tag Manager + Meta Pixel + Hotjar para heatmaps.
- **Autenticação da área do cliente:** Clerk ou Auth.js com magic link + Google.
- **Pagamentos** (quando aplicável — v2): PIX + boleto + cartão via Pagar.me/Stripe/Mercado Pago. **v1 é orçamento consultivo, não checkout.**
- **Busca:** Algolia ou Meilisearch (com sinônimos configurados).

---

### 12. Entregáveis esperados

1. Design system em Figma com tokens da paleta oficial + biblioteca de componentes.
2. Protótipo navegável (desktop + mobile) de: Home, Catálogo, Produto, Segmento, Orçamento, Sobre, Contato.
3. Código-fonte em Next.js/TypeScript/Tailwind, versionado em Git, com README claro.
4. CMS configurado, com pelo menos 40 produtos reais cadastrados (móveis, macas, carrinhos, armários, mesas, cadeiras, biombos, suportes).
5. Blog com 6 artigos SEO iniciais publicados.
6. Deploy em produção com domínio próprio, HTTPS, CDN, Core Web Vitals verdes verificáveis no PageSpeed Insights.
7. Documentação de operação (como cadastrar produto, publicar post, exportar leads).
8. Painel de analytics configurado com metas: envio de orçamento, clique em WhatsApp, download de catálogo.

---

### 13. Métricas de sucesso na v1 (90 dias após go-live)

- 100+ orçamentos qualificados por mês.
- Taxa de conversão visita → orçamento ≥ 3%.
- 20% do tráfego vindo de busca orgânica com "Manaus" na query.
- Aparecer na 1ª página do Google para "móveis hospitalares Manaus" e "equipamentos hospitalares Amazonas".
- Core Web Vitals 100% verde no CrUX.
- NPS de atendimento ≥ 70.

---

### 14. Restrições e princípios

- **Nada de banco de imagens genérico** de médicos sorrindo. Toda foto deve ser de produto/instalação real da Hausmedical (ou fotografia sob demanda em Manaus).
- **Zero jargão vago** ("soluções inovadoras", "excelência", "compromisso"). Trocar por dados concretos (norma, prazo, garantia, número).
- **Zero placeholders em produção** — se um campo não está pronto, não publicar (evitar o erro da NS Hospitalar com "0 anos").
- **Zero dark patterns** — cliente hospitalar valoriza transparência; nada de contagem regressiva falsa, "somente hoje", pop-ups agressivos.
- **LGPD por padrão:** consentimento granular, política clara, canal de exclusão de dados fácil.
- **Acessibilidade não é opcional.**

---

## Checklist final antes do go-live

- [ ] Logo em SVG carregando corretamente em todas as páginas.
- [ ] Paleta oficial aplicada via tokens; nenhum hex hardcoded.
- [ ] Heebo + Montserrat carregando com `font-display: swap`.
- [ ] Catálogo com 40+ produtos e fichas técnicas completas.
- [ ] Formulário de orçamento envia por e-mail + WhatsApp + PDF.
- [ ] Área do cliente funcional (login, pedidos, chamados).
- [ ] Blog com 6 artigos publicados.
- [ ] Schema.org validado no Rich Results Test.
- [ ] PageSpeed ≥ 90 mobile e desktop.
- [ ] WCAG AA verificado com axe DevTools sem erros críticos.
- [ ] Selos Anvisa/ISO com links reais.
- [ ] Google Business, GA4, Meta Pixel, GTM configurados.
- [ ] Sitemap enviado ao Google Search Console.
- [ ] Backup automático diário do CMS.
- [ ] Política LGPD publicada com canal de contato do DPO.

---

**Resumo do posicionamento:** Hausmedical é o único fornecedor de móveis e equipamentos hospitalares em Manaus com **catálogo B2B navegável, orçamento consultivo em 1 clique, certificações Anvisa/ISO expostas, área do cliente com pós-venda técnico e experiência digital de nível nacional** — mantendo estoque, montagem, entrega e atendimento no Amazonas. O site deve provar isso em cada tela.
