# Como rodar a sua cópia do Juninho

## Pré-requisitos

- Uma instância do **n8n** (self-hosted ou n8n Cloud)
- Um servidor com **[WAHA](https://waha.devlike.pro/)** conectado a um número de WhatsApp (o original roda em uma VM na Oracle Cloud)
- Conta Google (Sheets, Drive e Docs)
- Chave de API da **Anthropic** (agente e leitura de documentos)
- Chave de API da **OpenAI** (transcrição de áudio)

## Passo a passo

1. **Crie a planilha** seguindo [planilha.md](planilha.md).
2. **Crie o modelo de contrato** no Google Docs, usando os marcadores que o nó *Preencher contrato* substitui (abra o nó para ver a lista).
3. **Importe o workflow:** no n8n, vá em *Workflows → Import from File* e escolha `workflow/juninho.json`.
4. **Conecte as credenciais** em cada nó que mostrar um aviso: Google Sheets, Google Drive, Google Docs, Anthropic, OpenAI e WAHA (header `X-Api-Key`).
5. **Troque os marcadores:**
   - `SEU_SERVIDOR_WAHA` → endereço do seu servidor WAHA
   - `SEU_ID_GOOGLE_1`, `_2`, `_3` → IDs da sua planilha, do modelo de contrato e da pasta no Drive (o ID fica na URL do arquivo)
   - `TROQUE-POR-UM-CAMINHO-ALEATORIO` → um caminho difícil de adivinhar para o webhook
   - Números `55009...` → os números autorizados a usar o bot (nó *Extrair Dados da Mensagem* e nós de código de avisos)
6. **Aponte o WAHA para o n8n:** configure o webhook do WAHA (evento `message.any`) para a *Production URL* do nó *Entrada WhatsApp (WAHA)*.
7. **Ative o workflow** e mande "Juninho" no WhatsApp.
