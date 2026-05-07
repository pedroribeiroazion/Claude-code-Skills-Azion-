# Resolução de Conflitos - Claude Bots

## Análise dos Conflitos

### 1. Newsletter Bot Duplicado (ALTO)

**Conflito:** `newsletter-bot/` e `newsletter-generator.skill` fazem IDÊNTICO

**Situação:**
- `newsletter-bot/` - Estrutura completa com README, CLAUDE.md, prompts/, generate.sh
- `newsletter-generator.skill` - Skill compactado com SKILL.md (765 linhas)
- Ambos analisam estilo e geram newsletters

**Resolução:**
- ✅ Manter `newsletter-generator.skill` (formato skill padrão)
- ✅ Extrair conhecimento de `newsletter-bot/` e mover para `newsletter-generator/`
- ✅ Arquivar `newsletter-bot/` após migração

---

### 2. Writing Style Analyzer vs AI Writing Detector (PARCIAL)

**Conflito:** Potencial sobreposição de análise de estilo

**Situação:**
- `writing-style-analyzer.skill` - Analisa estilo para REPRODUZIR
- `ai-writing-detector.skill` - Detecta padrões AI para CORRIGIR

**Resolução:**
- ✅ Manter AMBOS (propósitos diferentes)
- ✅ `writing-style-analyzer` → criar estilos para usar
- ✅ `ai-writing-detector` → melhorar textos existentes

---

### 3. Learning Bot vs Azion Content Optimizer (TEMÁTICA)

**Conflito:** Sobreposição temática de conteúdo educacional

**Situação:**
- `learning-bot/` - 90+ arquivos educacionais + prompt de rewrite
- `azion-content-optimizer.skill` - Skill de otimização para AI discoverability

**Resolução:**
- ✅ Manter AMBOS com propósitos distintos:
  - `learning-bot/` → Bot de criação de learning pages
  - `azion-content-optimizer.skill` → Skill de otimização de conteúdo existente

---

## Ações a Executar

1. **Extrair e descompactar skills compactados**
   - newsletter-generator.skill
   - writing-style-analyzer.skill
   - talking-point-extractor.skill

2. **Consolidar newsletter**
   - Mover README e estrutura de `newsletter-bot/` para `newsletter-generator/`
   - Arquivar `newsletter-bot/`

3. **Documentar diferenças**
   - Criar README.md explicando quando usar cada skill/bot

4. **Manter estrutura limpa**
   - Skills em formato .skill descompactado
   - Bots em pastas com README e CLAUDE.md