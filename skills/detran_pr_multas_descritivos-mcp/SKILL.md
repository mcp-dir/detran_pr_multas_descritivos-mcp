---
name: detran_pr_multas_descritivos-mcp
description: Skill da REST API do DETRAN PR: Multas (Descritivos) na MCP.AI: 1 endpoint em /api/detran_pr_multas_descritivos. DETRAN PR: Multas (Descritivos), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DETRAN PR: Multas (Descritivos) — REST API skill

Você tem acesso à **DETRAN PR: Multas (Descritivos)** REST API na MCP.AI.

> DETRAN PR: Multas (Descritivos), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/detran_pr_multas_descritivos
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/detran_pr_multas_descritivos/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"renavam":"...","pkcs12_cert":"...","pkcs12_pass":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/detran_pr_multas_descritivos/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `detran_pr_multas_descritivos_consultar`

DETRAN PR: Multas (Descritivos), consulta em fonte oficial. _(POST /api/detran_pr_multas_descritivos/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `renavam` | string | Sim | Parâmetro de consulta "renavam". |
| `pkcs12_cert` | string | Sim | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Sim | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_detran_pr_multas_descritivos` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
