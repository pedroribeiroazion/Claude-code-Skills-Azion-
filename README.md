# Guia Completo - Claude Bots

Todas as skills, bots, prompts e recursos disponíveis em `/Users/pedro.ribeiro/Desktop/claude-bots`

---

## 📚 SKILLS (7 disponíveis)

Skills são módulos especializados com workflows completos para tarefas específicas.

### 1. **newsletter-generator** 📧
**Localização:** `newsletter-generator/SKILL.md`

**O que faz:** Analisa estilo de newsletters passadas e gera novas edições mantendo a voz do autor.

**Quando usar:**
- ✅ Você tem newsletters passadas (5-20 edições)
- ✅ Quer gerar novas newsletters mantendo consistência de voz
- ✅ Precisa automatizar produção de newsletters em escala

**Como usar:**
1. Coloque newsletters em `newsletter-generator/newsletters/` (`.txt`, `.md`, `.html`)
2. Execute: `analyze my style` → gera `style_profile.md`
3. Gere nova: `generate newsletter about [topic]`

**Prompts disponíveis:**
- `prompts/analyze_style.md` - Prompt detalhado para análise de estilo
- `prompts/generate_newsletter.md` - Prompt para geração em batch

**Script:** `generate.sh` - Gera newsletter via terminal: `./generate.sh "your topic"`

**Status:** ✅ **CONSOLIDADO** (substitui `newsletter-bot/` arquivado)

---

### 2. **writing-style-analyzer** ✍️
**Localização:** `linkedin-bot/SKILL.md`

**O que faz:** Analisa estilo de escrita de um autor e cria "Style Card" reutilizável.

**Quando usar:**
- ✅ Quer capturar a voz de um criador de conteúdo
- ✅ Precisa criar guia de estilo a partir de exemplos
- ✅ Vai reproduzir um estilo em outras skills

**Input:** 5-20 exemplos de escrita do autor

**Output:** Style Card markdown (pode ser usado em outras skills)

**Não confundir com:** `ai-writing-detector` (detecta/corrige AI writing)

**Exemplo de uso:** Analisar posts de LinkedIn e criar Style Card para gerar novos posts na mesma voz.

---

### 3. **ai-writing-detector** 🔍
**Localização:** `ai-writing-detector/SKILL.md`

**O que faz:** Detecta e corrige padrões de escrita AI em textos.

**Quando usar:**
- ✅ Texto parece roboticamente genérico
- ✅ Quer remover "AI vocabulary" excessivo (crucial, delve, pivotal, tapestry)
- ✅ Precisa melhorar texto que soa artificial

**O que detecta:**
- **AI Vocabulary:** crucial, delve, emphasizing, enhance, fostering, highlighting, pivotal, showcasing, underscore, tapestry, testament, vibrant
- **Análise superficial:** Present participle phrases sem substância
- **Linguagem promocional:** boasts, vibrant, rich, profound, showcasing
- **Estruturas negativas paralelas:** "Not just X, but Y"
- **Evitação de cópulas básicas:** "serves as" em vez de "is"

**Output:** 
1. Detection Report (score 0-24)
2. Texto reescrito mais natural e específico

**Filosofia:** AI writing "regred to the mean" - transforma fatos específicos em afirmações genéricas.

---

### 4. **social-content** 📱
**Localização:** `social-content-skill/SKILL.md`

**O que faz:** Cria, agenda e otimiza conteúdo para redes sociais.

**Quando usar:**
- ✅ Criar posts para LinkedIn, Twitter/X, Instagram, TikTok, Facebook
- ✅ Repurposing de conteúdo para múltiplas plataformas
- ✅ Estratégia de content calendar e engagement

**Plataformas suportadas:**
- LinkedIn (B2B, thought leadership)
- Twitter/X (tech, real-time, community)
- Instagram (visual brands, lifestyle)
- TikTok (brand awareness, younger audiences)
- Facebook (communities, local businesses)

**Features:**
- Hook formulas (curiosity, story, value, contrarian)
- Content repurposing system (blog → social)
- Content calendar templates
- Engagement strategy
- Analytics & optimization

**Exemplos existentes:**
- `twitter-thread-checkout-failures.md`
- `twitter-thread-ai-inference.md`
- `linkedin-post-load-balancer.md`

---

### 5. **azion-content-optimizer** ⚡
**Localização:** `azion-content-optimizer/SKILL.md`

**O que faz:** Otimiza conteúdo técnico para AI discoverability e citações por LLMs.

**Quando usar:**
- ✅ Otimizar documentação técnica para ChatGPT e outras AIs
- ✅ Melhorar SEO para LLMs (LLM discoverability)
- ✅ Adicionar structured data e quotable units
- ✅ Criar conteúdo para developers com foco em AI searchability

**Tom e voz Azion:** Minimal, confident, developer-first, precise, calm

**Elementos que adiciona:**
- **Definition blocks:** 2-line literal definition (no metaphors)
- **When to use / When not to use:** 3-5 bullets cada
- **Signals you need this:** Sintomas observáveis
- **Metrics and measurement:** Números específicos com ranges
- **Comparison tables:** Feature comparisons
- **FAQ sections:** 10+ natural language questions
- **Common mistakes and fixes:** 3-5 mistakes concretos
- **How to implement:** Vendor-neutral + platform-specific
- **Cross-links:** Related resources
- **Schema markup:** JSON-LD para structured data

**Princípios AI Discoverability:**
- Lead with literal definitions
- Use pattern: "[Term] is [category] that [differentiator]"
- Complete questions as H2s (not fragments)
- Consistent terminology (no synonym variation)
- Metrics with units (e.g., "reduces latency by 40-60%")
- Version numbers, release dates, timestamps
- References to standards (RFCs, W3C, ISO)

**Terminologia Azion:**
- ✅ "Applications" (not "Edge Applications")
- ✅ "Functions" (not "Edge Functions")

---

### 6. **youtube-video-producer** 🎬
**Localização:** `youtube-video-producer/SKILL.md`

**O que faz:** Produz scripts completos de vídeo YouTube para tech leaders (CTO, CISO, VP Engineering).

**Quando usar:**
- ✅ Criar scripts educacionais B2B
- ✅ Produzir thought leadership videos
- ✅ Explainers de produto com foco em valor de negócio
- ✅ Vídeos para developer audiences

**Estrutura:**
1. **Hero's Journey:** 7 questions (character, goal, obstacles, stakes, helper, transformation, new status)
2. **Gagne's Nine Events of Instruction:** Framework pedagógico
3. **Two-column script:** Audio | Visual

**Output completo:**
- Title & thumbnail strategy (3-5 options)
- Opening sequence (first 5 sec hook + 30-60 sec intro)
- Complete two-column script
- Business value points (metrics, ROI, risk mitigation, cost optimization)
- Production notes (assets, timeline, talking points)
- YouTube metadata (tags, description)
- Calls to action

**Production constraints:** Camera, microphone, screen sharing with whiteboards, live code, demos

**Exemplos existentes:**
- `video-script-ddos-architecture.md`
- `video-script-incident-response.md`
- `video-script-programmable-waf.md`
- `video-script-api-security.md`
- `video-script-ai-evolution.md`
- `video-script-modern-security.md`

---

### 7. **talking-point-extractor** 💬
**Localização:** `talking-point/SKILL.md`

**O que faz:** Extrai talking points de conteúdo.

**Quando usar:**
- ✅ Precisa extrair pontos-chave de artigos
- ✅ Quer criar resumo de talking points
- ✅ Documentação de discussões

**Output:** Lista estruturada de talking points

---

## 🤖 BOTS E PROJETOS

Bots são projetos completos com múltiplos arquivos, prompts e outputs.

### **learning-bot** 📖
**Localização:** `learning-bot/`

**O que é:** Bot para criar learning pages educacionais sobre tecnologia.

**Conteúdo:** 90+ artigos educacionais sobre:
- **Security:** Bot attacks, credential stuffing, API security, WAF, DDoS, OAuth, mTLS
- **Protocols:** HTTP, HTTPS, HTTP/2, HTTP/3, WebSocket, TCP, UDP, DNS, BGP
- **Architecture:** Microservices, serverless, edge computing, API gateway, reverse proxy
- **AI/ML:** Prompt engineering, AI inference, LLMs, embeddings, vector search, RAG, AI agents, knowledge distillation, MLOps, LLMOps, edge AI
- **Cloud/CDN:** Multi-CDN strategy, load balancing, CDN routing, caching
- **Databases:** SQL vs NoSQL
- **Development:** GraphQL, gRPC, REST API, OAuth 2.0, JWT

**Idiomas:** Inglês, Espanhol, Português

**CLAUDE.md:** Instruções para criar learning pages otimizadas para AI discoverability

**Foco:** Developer-first, educational, SEO para LLMs

**Otimização:** Segue padrões de AI discoverability (quotable units, FAQ, metrics, comparisons)

**Não confundir com:** `azion-content-optimizer` (skill de otimização, não criação)

**Exemplos:**
- `what-is-edge-computing.md`
- `what-is-api-gateway.md`
- `what-is-rate-limiting.md`
- `edge-computing-for-ai-inference.md`

---

### **youtube-video-producer/** (projeto) 🎥
**Localização:** `youtube-video-producer/`

**O que é além do skill:**
- 50+ scripts de vídeo produzidos
- Estratégias de vídeo (`youtube-video-strategy.md`)
- SEO research para YouTube Shorts
- Séries de vídeos (security, viral, tech)
- Versões revisadas de scripts

**Séries planejadas:**
- Security video series
- Viral video series
- Tech video series

---

### **writing-style/** (recurso) 📝
**Localização:** `writing-style/`

**O que é:** Style Cards e exemplos de posts.

**Conteúdo:**
- `writing-style.md` - Style Card: Pedro's LinkedIn Voice
- `novo-post-linkedin.md` - Exemplo de post
- `post-leticas-jornalismo-content.md` - Post e revisões

**Uso:** Referência de style cards criados com `writing-style-analyzer`

---

### **blog-posts/** 📄
**Localização:** `blog-posts/`

**Conteúdo:**
- `why-azion-migrating-individual-npm-packages.md`

**Uso:** Artigos de blog sobre Azion

---

### **primitives-content/** 🔧
**Localização:** `primitives-content/`

**Conteúdo:**
- `azion-cells-compute-primitives.md`
- `azion-cells-compute-primitives-v2.md`

**Uso:** Documentação de Azion Cells e Compute primitives

---

### **strategy-bot/** (vazio) 🎯
**Localização:** `strategy-bot/`

**Status:** Diretório vazio (planejado para estratégias)

---

## 📋 PROMPTS REUTILIZÁVEIS

### **newsletter-generator/prompts/**

#### `analyze_style.md`
**Uso:** Prompt detalhado para análise de estilo de newsletters.

**Como usar:** Cole no Claude Code após adicionar newsletters em `newsletters/`

**Output:** `style_profile.md` com:
- Voice & Tone
- Typical Structure
- Sentence & Paragraph Patterns
- Vocabulary & Expressions
- Recurring Themes & Worldview
- Rhetorical Devices
- Reader Relationship
- Intelligent Brevity Patterns
- Teach-Don't-Pitch Style
- Brand Alignment

---

#### `generate_newsletter.md`
**Uso:** Prompt para geração de newsletters em batch.

**Como usar:** Cole no Claude Code após ter `style_profile.md`

**Features:**
- Gera múltiplas newsletters de uma vez
- Variações de tom
- Batch generation para escala

---

## 📊 ESTRATÉGIAS E PLANOS

### `azion-devrel-q2-strategy.md`
**O que é:** Estratégia de DevRel para Q2 2026.

**Foco:** AI pageview optimization

---

### `learning-bot/OPTIMIZATION-PLAN.md`
**O que é:** Plano de otimização das learning pages.

**Conteúdo:** Estratégia para melhorar AI discoverability

---

### `learning-bot/learning-pages-aeo-strategy.md`
**O que é:** Estratégia AEO (Answer Engine Optimization) para learning pages.

---

### `learning-bot/top-50-learning-pages-priority.md`
**O que é:** Lista priorizada das 50 learning pages mais importantes.

---

## 🎯 FLUXOS DE TRABALHO RECOMENDADOS

### Fluxo 1: Criar Newsletter
```
1. Cole newsletters em newsletter-generator/newsletters/
2. Use prompt: analyze_style.md
3. Resultado: style_profile.md criado
4. Use prompt: generate_newsletter.md
5. Resultado: Nova newsletter em output/
```

### Fluxo 2: Repurposing de Conteúdo
```
1. Use social-content skill
2. Input: Blog post ou artigo existente
3. Output: Posts para LinkedIn, Twitter, Instagram
4. Use ai-writing-detector se precisar limpar AI writing
```

### Fluxo 3: Otimizar Learning Page
```
1. Use azion-content-optimizer skill
2. Input: Learning page existente
3. Output: Versão otimizada com FAQ, métricas, comparisons
4. Adicione à learning-bot/
```

### Fluxo 4: Criar Vídeo YouTube
```
1. Use youtube-video-producer skill
2. Input: Conceito do vídeo
3. Output: Script completo + thumbnail strategy + production notes
4. Salve em youtube-video-producer/
```

### Fluxo 5: Capturar Voz de Autor
```
1. Cole 5-20 posts do autor
2. Use writing-style-analyzer skill
3. Output: Style Card
4. Use Style Card em outras skills (social-content, newsletter-generator)
```

---

## 🔧 MANUTENÇÃO

### Arquivados
- `.archive/newsletter-bot-archived-20260507/` - Consolidado em `newsletter-generator/`

### Skills compactados (ainda presentes)
- `ai-writing-detector/ai-writing-detector.skill`
- `social-content-skill/social-content.skill`
- `youtube-video-producer/youtube-video-producer.skill`

**Nota:** Estes arquivos `.skill` são backups. As versões ativas são os `SKILL.md`.

---

## 📝 BOAS PRÁTICAS

### Quando criar novo conteúdo
1. **Newsletter:** Use `newsletter-generator` após analisar estilo
2. **Social posts:** Use `social-content` com hook formulas
3. **Learning page:** Use `learning-bot/CLAUDE.md` como template
4. **Vídeo:** Use `youtube-video-producer` para script completo

### Quando melhorar conteúdo existente
1. **Texto AI genérico:** Use `ai-writing-detector`
2. **Conteúdo técnico:** Use `azion-content-optimizer`
3. **Repurposing:** Use `social-content` para criar variações

### Quando capturar estilo
1. **Análise completa:** Use `writing-style-analyzer`
2. **Style Card reutilizável:** Salve em `writing-style/`

---

## 🚨 CONFLITOS RESOLVIDOS

### ✅ Newsletter duplicado
- `newsletter-bot/` e `newsletter-generator.skill` eram idênticos
- Consolidados em `newsletter-generator/`
- `newsletter-bot/` arquivado

### ✅ Writing Style Analyzer vs AI Writing Detector
- Mantidos ambos (propósitos diferentes)
- `writing-style-analyzer` → Reproduz estilos
- `ai-writing-detector` → Melhora textos AI

### ✅ Learning Bot vs Azion Content Optimizer
- Mantidos ambos (propósitos diferentes)
- `learning-bot/` → Cria learning pages
- `azion-content-optimizer` → Otimiza conteúdo existente

---

## 📚 RECURSOS ADICIONAIS

### Documentação Azion
- Tom e voz: Minimal, confident, developer-first, precise, calm
- Terminologia: "Applications" (not "Edge Applications"), "Functions" (not "Edge Functions")
- Público: Developers building innovative applications

### AI Discoverability Principles
1. Lead with literal definitions (no metaphors)
2. Use pattern: "[Term] is [category] that [differentiator]"
3. Complete questions as H2s
4. Consistent terminology (no synonym variation)
5. Metrics with units
6. Version numbers, timestamps
7. References to standards (RFCs, W3C, ISO)

### Intelligent Brevity
- Paragraphs: 1-3 sentences max
- Sections: Max 100 words
- Bullets: Max 5 items
- Cut 20% of words after drafting
- Front-load value

---

**Última atualização:** 2026-05-07
**Total de skills:** 7
**Total de bots/projetos:** 6
**Total de learning pages:** 90+
