# Prova ROUND1 — Ollama Cloud Free

- Quando: 2026-09-05 11:19 -03
- Host: `https://ollama.com/api/chat`
- Modelo: `gpt-oss:120b` (ID API Cloud; docs.ollama.com/cloud)
- Plano: Free — concurrent **1** (ollama.com/pricing FAQ)
- Chamadas em paralelo: **0** (serializado)
- HTTP: `200`
- x-request-id: `eb03f869-56ad-4c69-a840-aa32986ba4a4`
- Usage desta chamada: `{'prompt_eval_count': 130, 'eval_count': 422, 'done_reason': 'stop'}`
- Secrets: nenhum

## Resposta (truncada)

O Ollama Cloud oferece o modelo de linguagem como serviço hospedado na nuvem, enquanto a versão local executa o mesmo modelo em sua própria máquina ou infraestrutura, proporcionando controle total sobre recursos e dados. A camada Free costuma limitar a 1 requisição simultânea porque assim a provedora pode garantir estabilidade e evitar uso excessivo de recursos em ambientes compartilhados sem custo. Se a fila de solicitações ficar cheia, é recomendável aplicar back‑off exponencial, migrar para um plano pago com maior concorrência ou reduzir a taxa de requisições enviadas.
