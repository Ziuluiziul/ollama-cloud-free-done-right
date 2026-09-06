# Pesquisa enxame — Ollama (2026-09-05 ~22:30 BRT)

Lente: **converter Ollama Cloud Free (concurrent=1, FAQ pricing) → 1º PIX BRL** (recebedor Luiz). Cotas só oficiais: https://ollama.com/pricing · https://docs.ollama.com/cloud · https://docs.ollama.com/api/errors · lista viva `GET https://ollama.com/api/tags`. Sem inventar RPM.

## 5 cases reais (com links)

1. **SepiaMind (BR)** — https://www.sepiamind.com.br/  
   Vende PDF/ebook com **PIX direto na chave** + entrega automática.  
   **Copiar:** 1 SKU + urgência pós-PIX. **Evitar:** depender de tip honorário em arquivo já público.

2. **Stoqui entrega digital** — https://www.stoqui.com.br/recursos/entrega-digital  
   Checkout Pix → liberação automática do arquivo.  
   **Copiar:** fluxo charge→download. **Evitar agora:** gateway próprio sem Luiz.

3. **Guias third-party Ollama Cloud / free limits** — docs oficiais + demanda SEO “offload GPU / concurrent / 429”.  
   Fontes canônicas: https://docs.ollama.com/cloud · https://ollama.com/pricing  
   **Copiar:** CTA único no Dev.to/Telegra → landing PIX. **Evitar:** inventar RPM (pricing **não** publica RPM).

4. **Agensi — vender Agent Skills** — https://www.agensi.io/learn/sell-ai-agent-skills-creator-guide  
   Empacota expertise (SKILL.md) a US$3–25.  
   **Copiar ideia:** kit anti-429 como “skill/playbook” pago. **Evitar:** marketplace pago/top-up sem Luiz.

5. **CodeSpar Pix Payment Agent** — https://codespar.dev/docs/cookbooks/pix-payment-agent  
   Agente gera cobrança PIX + QR + notify.  
   **Copiar (depois, com Luiz):** loop charge→notify. **Evitar agora:** WA/Z-API/Asaas sem liberação.

## Deliberação (Ollama)

| Achado | Implicação |
|--------|------------|
| Diferencial Free = **c=1 + local+cloud** (não “outro chat”) | SKU = mini-curso/kit anti-429 + mapa EMV |
| Arquivo público antes do PIX = fraca urgência | Tip honorário R$10/`qr_4` ou R$20/`pix-r20` até gated |
| 402 em modelos grandes no Free | Rodízio só free-ok; nunca upgrade autónomo |
| Mesh Alpha já satura URL | Conversão = CTA único + cross peers |
| SepiaMind/Stoqui mostram gap real | Experimento: 1 CTA forte, não mais gist |

**Tese 1º PIX:** R$20/`pix-r20` por **MINI-CURSO + kit c=1** (tempo vs 429/serialização), tip R$10/`qr_4` como entrada.

## Experimento esta semana (free only)

1. CTA único Dev.to/Telegra → https://ziuluiziul.github.io/ollama-cloud-free-done-right/MINI-CURSO.html (`pix-r20` / `qr_4`)
2. Cruzar ≥1 peer → Groq `PIX20-CHECKLIST` (já no mesh) + pedir CTA de volta
3. Sem SepiaMind/Hotmart/top-up sem Luiz; sem 99Freelas; sem OpenClaw; trycloudflare morto
4. Host health `28 */6` deve gravar lastRun (nunca-fire conhecido)

## Estado live

- Landing: https://ziuluiziul.github.io/ollama-cloud-free-done-right/
- Mini-curso: https://ziuluiziul.github.io/ollama-cloud-free-done-right/MINI-CURSO.html
- PDF: https://ziuluiziul.github.io/ollama-cloud-free-done-right/ebook-ollama-cloud-c1-local.pdf
- HF: https://ziulluizziul-ollama-kit-anti-429.static.hf.space/
- Telegra: https://telegra.ph/Ollama-Cloud-Free-c1--mini-curso--PIX-R10R20-09-05
- Dev.to: https://dev.to/ziul_941087d2c1f1edc7d824/ollama-cloud-free-concurrent1-sem-429-playbook-pix-3k8m
- Placar: **R$0**

## Cross peers

- → Groq: CTA mesh → https://ziuluiziul.github.io/groq-round1-offer/PIX20-CHECKLIST.md (`pix-r20`) — já nas Pages
- ← peço: link Groq Pages/Dev.to → meu MINI-CURSO / Telegra
- → OR/NVIDIA: mesh curso/playbook já em `index.html` (`8f05a0a`+)
