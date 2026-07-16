# Skills de terceiros embutidas

As skills de design vêm **dentro do repo**, versionadas. Você clona e elas
funcionam — sem `npx`, sem rede, sem comando nenhum.

Isso é uma decisão consciente, com um custo: elas **não atualizam sozinhas**.
Este arquivo existe pra que ninguém precise adivinhar de onde elas vieram nem
como atualizar.

---

## O que está embutido

| Skill | Papel | Origem | Licença |
|---|---|---|---|
| `impeccable/` | constrói interface | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Apache-2.0 |
| `design-taste-frontend/` | régua anti-cara-de-IA | [leonxlnx/taste-skill](https://github.com/leonxlnx/taste-skill) | MIT |

**Versão embutida:**

- `impeccable` — commit `8259c28209b92792005cec14dad573df39f68eaf` (2026-07-14),
  copiado de `.claude/skills/impeccable/` do repo de origem
- `design-taste-frontend` — commit `7b3782a65f89eb53ab67af4ac40b689704e5a876`
  (2026-07-16), copiado de `skills/taste-skill/SKILL.md` do repo de origem

**Modificações:** nenhuma. Os arquivos são cópia literal da origem. Se algum
dia forem modificados, registrar aqui — a Apache-2.0 exige sinalizar alteração.

As licenças originais estão em `impeccable/LICENSE` e
`design-taste-frontend/LICENSE`. Não remover.

---

## Por que a variante `.claude/`, e não o `npx skills add`

O repo da `impeccable` publica uma variante por agente (`.claude/`, `.agents/`,
`.cursor/`, ...). O `npx skills add` instala a variante **`.agents/`**, que é a
genérica. Ela não é a melhor pra cá:

| | `.agents/` (o que o `npx` instala) | `.claude/` (o que está embutido) |
|---|---|---|
| Frontmatter | sem | `user-invocable: true` + `allowed-tools` |
| Invocação | `$impeccable craft` | `/impeccable craft` |
| Texto | "**GPT** is capable of extraordinary work" | "**Claude** is capable of extraordinary work" |
| Correções de modelo | seção "**Codex**-specific defects" | sem seção de modelo |
| Caminho dos scripts | `.agents/skills/impeccable/scripts/` | `.claude/skills/impeccable/scripts/` |

Embutir a variante `.claude/` entrega a versão certa pro agente certo.

**Bônus:** o `npx skills add` cria symlink com caminho **absoluto**. Renomear
ou mover a pasta do projeto quebra o link e a skill some sem dar erro. Skill
embutida é arquivo de verdade — sobrevive a rename, move, zip e clone.

---

## Como atualizar

Não existe comando mágico. É cópia manual, e é rápido:

```bash
# 1. Pegar a origem num diretório temporário
git clone --depth 1 https://github.com/pbakaus/impeccable /tmp/impeccable
git clone --depth 1 https://github.com/leonxlnx/taste-skill /tmp/taste-skill

# 2. Substituir (o -delete tira arquivo que sumiu na origem)
rsync -a --delete /tmp/impeccable/.claude/skills/impeccable/ .claude/skills/impeccable/
cp /tmp/impeccable/LICENSE .claude/skills/impeccable/LICENSE
cp /tmp/taste-skill/skills/taste-skill/SKILL.md .claude/skills/design-taste-frontend/SKILL.md

# 3. Anotar os commits novos neste arquivo
git -C /tmp/impeccable log -1 --format="%H (%ad)" --date=short
git -C /tmp/taste-skill log -1 --format="%H (%ad)" --date=short
```

Depois de atualizar, **conferir se o caminho dos scripts continua o mesmo**:

```bash
grep -o "node [^ ]*scripts/context.mjs" .claude/skills/impeccable/SKILL.md
```

Tem que responder `.claude/skills/impeccable/scripts/context.mjs`. Se apontar
pra `.agents/`, você copiou a variante errada.

Teste rápido de que a skill está viva:

```bash
node .claude/skills/impeccable/scripts/context.mjs
```

Num projeto sem `PRODUCT.md` ele responde `NO_PRODUCT_MD` — isso é sucesso,
significa que o script rodou.

**Quando atualizar:** sem pressa. Skill de design não tem CVE. Uma olhada a
cada poucos meses, ou quando a origem anunciar algo que interessa.

---

## O que NÃO está embutido

O `playwright-cli` continua vindo pelo `npx skills add` (Fase 3.5 do
`/instalar`). Ele baixa binário de browser — isso não cabe num repo git.
