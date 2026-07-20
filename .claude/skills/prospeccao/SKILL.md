---
name: prospeccao
description: >
  Gera a abordagem de prospecção sob medida para o cliente cujo site acabou de ser
  construído neste projeto. Lê todo o contexto do projeto (o que foi entregue, a marca,
  o briefing), entrevista o usuário sobre o que falta (seguidores, faturamento, público,
  contato), e cruza tudo pra devolver: a mensagem de abordagem certa, se deve ligar ou
  não, o melhor canal e a sequência de follow-up — tudo no tom do usuário.
  Use quando o usuário disser "prospectar", "como abordo esse cliente", "/prospeccao",
  "monta a abordagem", "terminei o site, e agora?", ou ao decidir contatar o dono da loja.
---

# /prospeccao — Abordagem sob medida (método "Site Pronto")

Esta skill roda **depois** que o site do cliente já foi construído neste projeto.
A premissa do negócio é forte: construir o site pronto de graça com a identidade
da loja e usar isso como isca de prospecção. O que faz a abordagem converter é
**contexto real do cliente + entrega certa** — não uma mensagem genérica.

A skill tem contexto completo do que foi feito (está dentro do projeto). O que
ela não sabe do cliente, ela pergunta. Aí cruza tudo e entrega a melhor abordagem.

## Dependências

- **Contexto do negócio (quem prospecta):** `_memoria/empresa.md`
- **Tom de voz:** `_memoria/preferencias.md`
- **Contexto do projeto/cliente:** os arquivos deste projeto (ver Passo 1)
- **Pipeline global:** `dados/leads.csv` na raiz (registrar o lead ao final)

---

## Regras de ouro (o método por trás)

1. **Nunca abrir se apresentando como desenvolvedor/vendedor.** Abrir com algo
   específico e real da loja.
2. **Nunca apontar defeito da loja de cara.** Enquadrar como presente/portfólio.
3. **Mostrar, não contar.** Vídeo do site > link cru.
4. **O próximo passo é do usuário, não do cliente.** Nunca "se fizer sentido me chama".
5. **Lead não morre no primeiro silêncio.** Até 4 toques.
6. **Volume antes de julgar.** Só concluir se o método funciona depois de 15-20 alvos.

---

## Workflow

### Passo 1 — Absorver o contexto do projeto (silencioso)

Antes de perguntar qualquer coisa, ler o que já existe neste projeto pra não
perguntar o que já se sabe:
- `briefing.md` (se existir) — o que o cliente é, o objetivo.
- `PRODUCT.md` / `DESIGN.md` (se existirem) — o que o site entrega, a marca.
- `CLAUDE.md` do projeto.
- Qualquer pasta de site/entrega — o que de fato foi construído.
- O link do site no ar (Vercel), se estiver anotado em algum lugar.

Formar um retrato: **quem é o cliente, o que o site resolve pra ele, qual o
diferencial visível.** Guardar isso pra usar na mensagem.

### Passo 2 — Entrevista (só o que falta)

Perguntar UMA coisa por vez, pulando o que já foi respondido pelo contexto do
Passo 1. As perguntas existem pra medir **assertividade e canal**:

**Sobre alcance e porte:**
1. "Quantos seguidores a loja tem no Instagram? (dá uma noção de quão ativos e
   quão fácil vão te ver na DM)"
2. "Eles são ativos? Postam com frequência, respondem comentários/DM?"

**Sobre dinheiro (calibra o pitch e a mensalidade):**
3. "Quanto você imagina cobrar nesse — setup + mensalidade? (mesmo que uma faixa)"
4. "Qual teu chute do movimento/faturamento deles? Loja cheia ou parada? (define
   se a mensalidade cabe no bolso deles)"

**Sobre acesso e decisão:**
5. "Você tem o WhatsApp/telefone comercial deles, ou só o Instagram?"
6. "Sabe quem decide? É o dono que atende a DM ou tem funcionário no meio?"

**Sobre o público deles:**
7. "Quem é o cliente típico da loja? (jovem, família, turista de praia...) — isso
   muda o argumento de por que um site ajuda"

Se vier resposta vaga, pedir concretude uma vez. Não insistir mais que isso.

### Passo 3 — Cruzar e decidir a abordagem

Com contexto (Passo 1) + respostas (Passo 2), decidir e explicar o porquê:

**a) Canal recomendado** — regra de decisão:
- Tem telefone/WhatsApp comercial → **DM primeiro, ligar no dia 2 se não responder.**
- Só Instagram, loja muito ativa (responde DM) → DM, ligar é opcional.
- Só Instagram, loja pouco ativa → DM tem baixa chance; sugerir achar o telefone
  (Google, fachada, delivery) antes de gastar o toque.
- Poucos seguidores + parada → alertar que o alvo pode não valer o esforço.

**b) Vale a pena?** — se faturamento aparente é baixo e a mensalidade não cabe,
dizer com honestidade: "esse pode não sustentar a mensalidade — quer seguir como
portfólio mesmo ou parte pra outro?"

**c) A mensagem de abordagem** — gerar preenchida com o detalhe REAL do cliente
(puxado do Passo 1), no tom de `_memoria/preferencias.md`:

> *"Oi, tudo bem? Aqui é o [nome]. [Curti muito / sou cliente do] **[produto/prato
> específico real]** e reparei que vocês não tinham um site. Como eu trabalho com
> isso, resolvi montar um do zero pra loja de vocês, com a cara da marca — só como
> um presente/portfólio mesmo. Gravei um vídeo rápido mostrando: **[vídeo]**. Se
> curtirem, a gente vê como deixar no ar. Sem compromisso nenhum. 🙂"*

Ajustar o argumento ao público (resposta 7): loja de turista → "pra quem chega na
cidade e procura no Google"; público jovem → "pra facilitar o pedido pelo celular".

**d) Roteiro de ligação** (se o canal for ligar):
> *"Oi, é do [loja]? Aqui é o [nome], mandei uma mensagem no Insta/Zap esses dias,
> não sei se viram. Rapidinho: montei um site pra loja de vocês, de graça, como
> portfólio meu. Queria saber pra quem eu mostro — é com você ou tem alguém que
> cuida dessa parte?"*

Objetivo da ligação: descobrir quem decide + autorização pra mostrar. Não vender.

### Passo 4 — Sequência de follow-up (datada)

| Toque | Quando | O quê |
|---|---|---|
| 1 | Dia 0 | Mensagem inicial |
| 2 | Dia 2 | Ligação (se tem telefone). Senão: 2ª msg curta "passando pra garantir que viu" |
| 3 | Dia 5 | Mandar um **detalhe novo** do site (ex: "botão de reserva no WhatsApp de vocês") |
| 4 | Dia 9 | Take-away honesto: "vou seguir com outros projetos, mas o site fica de pé por mais X dias" |

### Passo 5 — Registrar o lead

Adicionar/atualizar a linha do cliente em `dados/leads.csv` na raiz (alvo, tipo,
canal, tem_telefone, site_montado, datas dos toques, status, resposta,
próximo_passo, observações). Status: `novo`, `abordado`, `em_follow_up`,
`respondeu`, `negociando`, `fechado`, `esfriou`, `sem_resposta`, `perdido`.

### Passo 6 — Fechamento (quando houver interesse)

Não jogar preço de cara: (1) confirmar que gostou, (2) modelo em 1 frase — setup
pra subir no domínio deles + mensalidade de manutenção, (3) ancorar valor: o que
1 cliente novo por semana vale vs. a mensalidade.

---

## Modo "revisar pipeline"

Se pedir "quem eu recontato hoje": ler `dados/leads.csv`, calcular em que toque
cada lead está pela data do último contato, listar os vencidos com o próximo passo.
A cada 10 alvos, apontar o que os que responderam têm em comum e ajustar a
qualificação.

---

## Regras

- Não perguntar o que o contexto do projeto já responde (Passo 1 vem antes da entrevista).
- Tom sempre de `_memoria/preferencias.md` — nunca genérico/corporativo.
- Sempre citar algo específico e real da loja na abordagem.
- Ser honesto quando o alvo não vale o esforço — assertividade é dizer não também.
- Registrar tudo no `leads.csv` — o método só vira confiável se virar dado.
- Lembrar: julgar o método só depois de 15-20 alvos.
