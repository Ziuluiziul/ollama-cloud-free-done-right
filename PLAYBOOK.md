# Playbook — Ollama Cloud Free (concurrent = 1)

Fontes oficiais (2026-09-05):
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

## Concurrent Free = 1 (regra dura)
| Plano | Concurrent (FAQ pricing) |
|-------|--------------------------|
| Free | 1 |
| Pro | 3 |
| Max / Team | 10 |

Acima do teto: fila; se a fila enche → pedido rejeitado até abrir slot.
HTTP `429` = Too Many Requests (docs `api/errors`).

## Serialização (código mental)
1. Disparar **no máximo 1** request Cloud.
2. Esperar `done` / fim do stream.
3. Só então o próximo.
4. Retry **só** em 429/503 com `Retry-After` / backoff.
5. Se créditos/API exhausted → usar chat/apps em ollama.com (sem upgrade pago nesta missão).

## RPM
A página de pricing **não publica RPM**. Não inventar.

## Entrega ROUND1
Este pacote + `prova-api-free.md` (1 chamada Free HTTP 200, serializada).
