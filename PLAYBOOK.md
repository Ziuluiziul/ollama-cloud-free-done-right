# Playbook — Ollama Cloud Free (concurrent = 1)

Fontes oficiais (lido 2026-09-05 20:26 America/Sao_Paulo):
- https://docs.ollama.com/cloud
- https://ollama.com/pricing (FAQ «How many requests can I run at once?»)
- https://docs.ollama.com/api/errors
- Lista viva: `GET https://ollama.com/api/tags`

## O que é
Ollama Cloud corre modelos grandes nos servidores Ollama; local corre no teu hardware. Local = ilimitado no teu PC. Cloud Free = starter credits + **1 pedido em simultâneo**.

## IDs
- API directa `https://ollama.com/api/chat`: ex. `gpt-oss:120b` (com `OLLAMA_API_KEY`)
- CLI local cloud: sufixo `-cloud` (ex. `ollama run gpt-oss:120b-cloud`)
- Confirmar IDs vivos com `GET /api/tags` (não inventar)
- Modelos Cloud podem ser aposentados (tabela em docs.ollama.com/cloud) — confirmar IDs vivos.

## Concurrent Free = 1 (regra dura)
| Plano | Concurrent (FAQ pricing) |
|-------|--------------------------|
| Free | 1 |
| Pro | 3 |
| Max / Team | 10 |

Acima do teto: fila; se a fila enche → pedido rejeitado até abrir slot.

## Erros (docs api/errors)
- `429` = Too Many Requests
- `502` = Bad Gateway (cloud model unreachable)
- Retry **só** 429/502 com `Retry-After` / backoff (não martelar 400/404/500)

## Serialização (código mental)
1. Disparar **no máximo 1** request Cloud.
2. Esperar `done` / fim do stream.
3. Só então o próximo.
4. Retry **só** em 429/502.
5. Se créditos/API exhausted → usar chat/apps em ollama.com (sem upgrade pago nesta missão).

## RPM
A página de pricing **não publica RPM**. Não inventar.

## Entrega
Este pacote + ebook PDF/HTML + mini-curso + `prova-api-free.md` (1 chamada Free HTTP 200, serializada).
PIX tip R$10 = `qr_4` · R$20 = `pix-r20`.
