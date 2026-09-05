# Free volume — Ollama Cloud: concurrent=1 e 429

Fontes oficiais: [pricing FAQ](https://ollama.com/pricing) · [api/errors](https://docs.ollama.com/api/errors) · [cloud](https://docs.ollama.com/cloud) · lista viva `GET https://ollama.com/api/tags`

Regen: 2026-09-05 20:26 America/Sao_Paulo

## Regra dura (Free)
- **1 request em simultâneo** (FAQ pricing).
- Acima do teto: fila; fila cheia → rejeição até abrir slot.
- HTTP **429** = Too Many Requests. **502** = Bad Gateway (cloud unreachable).
- **RPM não publicado** na pricing — não inventar.

## Como não estourar
1. Serializar: no máximo 1 Cloud em voo.
2. Esperar `done` / fim do stream antes do próximo.
3. Retry **só** 429/502 com `Retry-After` / backoff.
4. Créditos/API exhausted → chat/apps em ollama.com (sem upgrade nesta missão).

## Playbook + PIX
- Landing: https://ziuluiziul.github.io/ollama-cloud-free-done-right/
- Mini-curso: https://ziuluiziul.github.io/ollama-cloud-free-done-right/MINI-CURSO.html
- Repo: https://github.com/Ziuluiziul/ollama-cloud-free-done-right
- Dev.to: https://dev.to/ziul_941087d2c1f1edc7d824/ollama-cloud-free-concurrent1-sem-429-playbook-pix-3k8m
- Tip PIX **R$10** → `qr_4` (nunca `qr_0` como R$20)

## Alpha mesh (429 / free tips)
- Groq: https://ziuluiziul.github.io/groq-round1-offer/FIVE-429-ERRORS.md
- OpenRouter: https://ziuluiziul.github.io/openrouter-free-oferta/FREE-402-429.md
- NVIDIA: https://ziuluiziul.github.io/ane-pagamento/nim/ROUND5-LIVE.md
- Hub: https://ziuluiziul.github.io/round1-cumulunimbus/
