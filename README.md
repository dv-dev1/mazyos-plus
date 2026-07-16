# MazyOS+

> O sistema operacional do seu negócio dentro do Claude Code — agora com
> régua de qualidade visual.

Você acaba de instalar o MazyOS+. Em alguns minutos, sua empresa vai ter
uma memória própria, uma identidade visual aplicada em tudo que o sistema
gerar, e 15 skills prontas pra fazer marketing, SEO, ads e operação
rodarem com você dirigindo.

E quando o assunto for interface — site de cliente, landing page, página
de captura — o sistema constrói com direção estética de verdade e confere
o resultado no browser antes de te mostrar.

Bora voar.

---

## Ligando o sistema

Dois caminhos. Escolhe o que combina contigo.

### Pelo Claude (mais rápido)

Abre o Claude Code em qualquer pasta e cola:

```
Clona o https://github.com/<seu-usuario>/mazyos-plus.git na pasta atual,
entra nela e roda o /instalar.
```

Ele clona, entra na pasta nova e dispara a entrevista de setup. Você só
responde.

### Pelo terminal (mais previsível)

```
git clone https://github.com/<seu-usuario>/mazyos-plus.git
cd mazyos-plus
code .
```

Na janela do VS Code que abrir: terminal integrado → `claude` → `/instalar`.

---

Quando o `/instalar` terminar, renomeia a pasta pro nome do teu negócio
(fecha o VS Code, renomeia no Explorer/Finder, abre de novo). A pasta não
fica como "mazyos-plus" — ela é o teu negócio agora.

O `/instalar` roda uma vez só. Te entrevista sobre o negócio, monta a
memória, liga as ferramentas de frontend e configura o sistema. Depois
disso, é só usar.

---

## O sistema

**Núcleo** — o jeito de operar o dia a dia
`/abrir` carrega o contexto antes de cada sessão de trabalho · `/salvar`
faz commit + push no GitHub · `/atualizar` varre o projeto e atualiza a
memória · `/novo-projeto` cria pasta isolada pra cada cliente ou
iniciativa · `/mapear-rotinas` descobre o que você repete e transforma em
skill personalizada.

**Conteúdo e SEO** — vitrine pública da empresa
`/carrossel` cria carrosséis 1080×1350 com identidade da marca (com ou sem
foto IA) · `/publicar-tema` pega um tema e entrega artigo de blog +
carrossel + 3 legendas amarradas · `/seo` roda fluxo completo de 8 passos
(demanda, concorrência, GMB, on-page, conteúdo, ads, monitoramento, GEO) ·
`/responder-avaliacoes` escreve respostas humanas pras reviews do Google ·
`/aprovar-post` publica blog + Instagram + Facebook num comando.

**Anúncios pagos** — onde o dinheiro entra
`/anuncio-google` monta a campanha inteira em CSV pronto pra importar no
Google Ads Editor · `/relatorio-ads` lê os exports de Google + Meta e
devolve relatório semanal com alertas e recomendações.

**Produção** — ferramentas do dia a dia
`/analisar-dados` lê CSV/XLSX/PDF e gera resumo executivo ·
`/email-profissional` rascunha email a partir de contexto livre.

---

## A régua visual

Essa é a diferença pro MazyOS original.

Qualquer interface que o sistema construir passa por dois passos
obrigatórios, sem você precisar pedir:

**Constrói com a skill `frontend-design`.** Direção estética deliberada,
tipografia com personalidade, um elemento de assinatura. Lê o
`identidade/design-guide.md` antes de decidir qualquer cor. Se você trouxer
referência (Pinterest, print de um site que curtiu), ela entra no brief — e
é ela que separa o resultado da cara de IA. Se você não trouxer, o sistema
pede.

**Confere com o `frontend-design-evaluator`.** Antes de te mostrar
qualquer coisa, o sistema sobe a página no browser de verdade, olha nos
três tamanhos (desktop, tablet, celular), interage com os hovers, e dá nota
de 0 a 10 em quatro critérios:

| Critério | Peso |
|---|---|
| Design Quality | 40% |
| Originality | 30% |
| Craft | 15% |
| Functionality | 15% |

Ele penaliza explicitamente padrão de "AI slop" — gradiente roxo, card
branco com sombra, hero centralizado, grid uniforme, "Get Started" como
único CTA. **Abaixo de 7 não sai.** O sistema aplica as melhorias e roda
de novo, até três vezes. Passou de 7, você recebe o trabalho junto com a
nota.

O ponto: quem construiu é o pior juiz do que construiu. O evaluator existe
pra corrigir esse viés antes do cliente ver.

---

## Ferramentas

O `/instalar` monta tudo. Se precisar refazer na mão:

```
/plugin marketplace add anthropics/claude-code
/plugin install frontend-design@claude-code-plugins
```

```bash
npx skills add microsoft/playwright-cli
```

O evaluator (`.claude/agents/frontend-design-evaluator.md`) já vem no repo.

---

## A tese

IA não é uma ferramenta que sua empresa usa. É o sistema operacional em que
ela roda.

A diferença não é velocidade. É capacidade nova — uma pessoa com IA
constrói o que antes exigia time inteiro. Cada processo crítico que hoje
roda em open loop (decide → executa → não mede → repete cego) vira closed
loop dentro do MazyOS+ (decide → executa → captura → realimenta → ajusta
sozinho).

O trabalho visual é o mesmo princípio. Gerar interface sem medir é open
loop — sai bonito às vezes, genérico na maioria, e você só descobre qual
foi quando o cliente reclama. O evaluator fecha o loop.

O sistema não substitui você. Vira parte da sua empresa.

---

## Como o MazyOS+ pensa

`_memoria/` é o cérebro. Tudo que importa do seu negócio mora aqui — quem é
a empresa, como ela fala, o que tá em foco essa semana. O Claude lê isso
antes de cada resposta. Quanto melhor a memória, melhor o sistema.

`identidade/` é o rosto. Cores, fontes, logo, padrão visual. Todo
carrossel, slide, site e peça que o sistema gera respeita isso — e a
identidade tem a palavra final, inclusive contra o gosto da skill de design.

`marketing/`, `saidas/` e `scripts/` são o resultado. O sistema produz,
versiona no GitHub, fica tudo seu.

---

## Origem

Construído em cima do [MazyOS](https://github.com/mazzeoia/mazyos), de
[@mazzeoia](https://github.com/mazzeoia). O núcleo — memória, identidade,
skills de marketing e o `/instalar` — é dele. O que foi somado aqui é a
régua visual: o `frontend-design-evaluator`, o encaixe com a skill de
design da Anthropic, e a obrigatoriedade dos dois no fluxo de interface.
