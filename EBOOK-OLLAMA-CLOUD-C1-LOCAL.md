# Ebook — Ollama Cloud Free (c=1) + Local

**Recebedor PIX: LUIZ** · Tip R$10 = `qr_4` · Pages: https://ziuluiziul.github.io/ollama-cloud-free-done-right/

Fontes oficiais: [docs.ollama.com/cloud](https://docs.ollama.com/cloud) · [ollama.com/pricing](https://ollama.com/pricing) · [api/errors](https://docs.ollama.com/api/errors) · `GET https://ollama.com/api/tags`

## 1. Dois modos
| Modo | Onde corre | Limite típico |
|------|------------|----------------|
| **Local** | Teu hardware (`ollama run …`) | Capacidade do PC (VRAM/RAM) |
| **Cloud Free** | Servidores Ollama | **1 concurrent** (FAQ pricing) + créditos starter |

Cloud serve para modelos grandes sem GPU local. Local continua ilimitado no teu lado.

## 2. Regra dura Free = concurrent 1
- Plano Free: **1 pedido em simultâneo**.
- Pro=3 · Max/Team=10 (FAQ pricing).
- Acima do teto: fila; fila cheia → rejeição.
- HTTP **429** = Too Many Requests · **503** = transient.
- **RPM não publicado** na pricing — não inventar.

## 3. Serializar (anti-429)
1. No máximo **1** request Cloud em voo.
2. Esperar `done` / fim do stream.
3. Só então o próximo.
4. Retry **só** 429/503 com `Retry-After` / backoff.
5. Créditos/API exhausted → chat/apps em ollama.com.

## 4. Local + Cloud juntos
- Local: `ollama run <modelo>` no teu host.
- Cloud via CLI: sufixo `-cloud` (ex. `ollama run gpt-oss:120b-cloud`).
- API directa: `POST https://ollama.com/api/chat` com `OLLAMA_API_KEY`.
- Confirmar IDs vivos com `GET /api/tags` — nunca inventar nomes.

## 5. Checklist mínimo
- [ ] Key em https://ollama.com/settings/keys (nunca partilhar o secret)
- [ ] 1 request Cloud de cada vez
- [ ] Prova: 1× `POST /api/chat` HTTP 200 serializado
- [ ] Fallback web se exhausted

## 6. Pacotes PIX (EMV por valor)
| Pacote | Valor | Artefacto |
|--------|-------|-----------|
| Essencial (tip) | R$10 | `qr_4` |
| Starter | R$20 | `pix-r20` |
| Completo | R$50 | `qr_2` |
| Pro | R$100 | `qr_0` |

⚠️ `qr_0` ≠ R$20 · `qr_1` = R$200 · ver PIX-MAPA.md

## 7. Links
- Landing: https://ziuluiziul.github.io/ollama-cloud-free-done-right/
- Repo: https://github.com/Ziuluiziul/ollama-cloud-free-done-right
- Dev.to: https://dev.to/ziul_941087d2c1f1edc7d824/ollama-cloud-free-concurrent1-sem-429-playbook-pix-3k8m
- Hub: https://ziuluiziul.github.io/round1-cumulunimbus/
- 429 sheet: https://ziuluiziul.github.io/ollama-cloud-free-done-right/FREE-429-CONCURRENT1.md
