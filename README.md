# audit-saas-icp-fit

Skill para auditoria de produtos **SaaS / B2B** sob a ótica de **ICP, posicionamento, design, pricing, oferta, onboarding, prova e lacunas de GTM**.

> **Créditos / inspiração:** esta skill foi criada a partir do artigo **"Preço é filtro de ICP"**, publicado por **[@leomarciano](https://x.com/leomarciano)** no X/Twitter — [post original](https://x.com/leomarciano/status/2073144622465819001). A ideia central — enxergar preço não só como captura de valor, mas como **filtro de ICP** — sustenta toda a referência `references/pricing-as-icp.md` e o eixo 4 (Pricing) da auditoria.

Não é uma checklist de UX. É uma decisão de produto: a skill lê a superfície real (landing, pricing, onboarding, checkout, demo, prints) e diz **se o produto faz sentido como negócio, para quem ele fala e por que o preço/desenho está ou não selecionando o cliente certo**.

> Idioma de saída padrão: Português (PT-BR). Citações e comandos permanecem em inglês quando necessário.

---

## Quando usar

Use esta skill quando alguém perguntar (ou você quiser investigar) coisas como:

- "Esse produto SaaS faz sentido?"
- "Quem é o ICP real disso aqui?"
- "Esta landing/pricing fala com o comprador certo?"
- "Esse preço está chamando o cliente errado?"
- "Vale a pena aumentar o ticket?"
- "O plano starter está frouxo demais?"
- "Por que estou convertendo pouco?"
- "Esse design fala enterprise ou fala pro plano de R$ 29?"
- "Falta feature, falta prova, ou falta ICP?"

Invocável com `/audit-saas-icp-fit` em Codex/Codex CLI.

---

## Como a skill pensa

A auditoria é feita em **eixos**, não em "boas práticas":

1. **ICP e dor** — quem paga, ativa, fica, expande e não destrói margem.
2. **Promessa e posicionamento** — concreta, crível, comprável e selecionável.
3. **Design que comunica ICP** — o visual como sinal de mercado, não como estética.
4. **Pricing, planos e economia** — preço como filtro de ICP (ver `references/pricing-as-icp.md`).
5. **Produto e lacunas** — separar "falta feature" de "falta prova", "falta clareza" e "falta qualificação".

A saída sempre classifica o produto em uma (ou mais) dessas categorias:

| Cat | Diagnóstico |
|-----|-------------|
| **A** | Alinhado e vendável |
| **B** | Boa dor, comunicação fraca |
| **C** | ICP confuso |
| **D** | Pricing chama cliente errado |
| **E** | Operação não escala |
| **F** | Valor percebido insuficiente |

---

## Saída padrão

Quando você roda a skill, ela devolve uma estrutura fixa, adaptável ao contexto:

```text
# Auditoria de Produto, ICP, Design e Pricing

## 1. Veredito curto
## 2. O que o produto parece prometer
## 3. ICP e dor
## 4. Design e comunicação
## 5. Pricing e planos
## 6. Lacunas críticas
## 7. Recomendações priorizadas (agora / próximo / depois)
## 8. Experimento prático (7–20 dias ou 10–20 leads)
## 9. Frase brutalmente honesta
```

---

## Como usar (3 formas)

### 1. Via CLI Codex (recomendado)

```bash
# dentro do seu projeto SaaS
/audit-saas-icp-fit
# ou apontando uma referência:
/audit-saas-icp-fit https://seusite.com/pricing
```

### 2. Importando como skill local (Codex / Claude / Cursor)

Cole o conteúdo de `SKILL.md` (e o `agents/openai.yaml` se usar CLI OpenAI) na pasta de skills:

- Codex CLI: `~/.codex/skills/<nome>/SKILL.md`
- Claude / Cowork: cole como `SKILL.md` no diretório correspondente

### 3. Manualmente

Abra o `SKILL.md` e siga a seção **"Primeiro movimento"**. Se houver URL, inspecione a superfície real; se não houver, faça no máximo **6 perguntas**:

1. Qual produto e resultado prometido?
2. Qual ICP desejado?
3. Quem compra hoje?
4. Quais planos e preços atuais?
5. Self-serve, demo, consultiva ou founder selling?
6. O que mais dá suporte, churn, objeção ou retrabalho?

---

## Estrutura do repositório

```
.
├── SKILL.md                    # cérebro da skill (use este arquivo)
├── agents/
│   └── openai.yaml             # manifesto para Codex CLI / OpenAI Agent
└── references/
    └── pricing-as-icp.md       # deep-dive em preço como filtro de ICP
```

- **`SKILL.md`** — fonte de verdade. Tudo que a skill faz vem daqui.
- **`agents/openai.yaml`** — metadados para registro como agent (display name, short description, prompt default).
- **`references/pricing-as-icp.md`** — leitura complementar quando a pergunta envolver **preço, planos, desconto, ticket, churn, CAC, suporte, onboarding, payback, margem, expansão ou suspeita de ICP errado**.

---

## Princípios editoriais da skill

- Decisão de produto > opinião estética.
- Design, copy e preço devem **selecionar** o cliente certo, reduzir fricção e aumentar compromisso.
- Sem "depende" sem critério. Sem consultoria genérica.
- Frases úteis que a skill devolve quando aplica:
  - "Seu produto pode estar certo, mas a embalagem está selecionando o cliente errado."
  - "Preço baixo não reduz objeção. Muitas vezes só reduz compromisso."
  - "MRR que consome suporte demais é vaidade operacional."
  - "Se o founder precisa compensar manualmente a entrega, o preço está mentindo."

---

## Métricas que a skill costuma pedir

Sempre por **segmento / plano / canal**, nunca média geral:

- Conversão por ICP e canal
- Ativação e time-to-value
- Retenção e expansão por plano
- Logo churn e revenue churn
- CAC payback
- Suporte por R$ 1.000 de receita
- Desconto × ativação/renovação
- Tickets, calls e horas de onboarding por cliente
- WTP por segmento
- Objeções recorrentes
- NRR por coorte

---

## Licença

MIT — reutilize, adapte, redistribua. Mantenha a citação.

## Créditos

Conceito de **preço como filtro de ICP** inspirado no artigo **"Preço é filtro de ICP"** de [@leomarciano](https://x.com/leomarciano) — [post](https://x.com/leomarciano/status/2073144622465819001).

## Autor

Luciano Botelho — [@olucianobotelho](https://github.com/olucianobotelho)
