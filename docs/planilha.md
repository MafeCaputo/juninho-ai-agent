# Estrutura da planilha

O Juninho usa uma única planilha do Google Sheets como banco de dados. Crie uma planilha com as abas abaixo e, na **primeira linha** de cada aba, os cabeçalhos exatamente com estes nomes.

## Veiculos

| Coluna | Descrição |
|---|---|
| placa | Placa em maiúsculas (chave) |
| marca | |
| modelo | |
| ano | |
| cor | |
| renavam | |
| status | `disponível` ou `alugado` |
| observacoes | Opcional |
| cadastrado_em | Data dd/MM/yyyy |
| km_atual | Gravado pelo sistema de quilometragem |
| km_atualizado_em | Gravado pelo sistema |
| km_ultima_troca_oleo | Gravado pelo sistema |
| data_ultima_troca_oleo | Gravado pelo sistema |
| km_aviso_oleo | Gravado pelo sistema |

## Clientes

| Coluna | Descrição |
|---|---|
| cliente_documento | CPF, só números (chave) |
| cliente_nome | |
| nacionalidade | |
| profissao | |
| rg | |
| telefone | Só números, com DDD |
| endereco | Endereço completo |
| cadastrado_em | Data dd/MM/yyyy |

## Locacoes

| Coluna | Descrição |
|---|---|
| id_locacao | `LOC-ddMMyyHHmm` |
| placa | |
| cliente_nome | |
| cliente_telefone | |
| cliente_documento | CPF |
| data_inicio | |
| data_fim_prevista | Vencimento do contrato |
| valor_semanal | Valor do aluguel semanal |
| caucao | Caução paga pelo cliente |
| dia_vencimento | `segunda` ... `domingo` |
| status | `ativa` ou `finalizada` |
| contrato_url | Link do contrato gerado |
| km_inicio | Km na entrega do veículo |
| limite_km_mensal | Limite de km por mês |
| valor_km_excedente | R$ por km excedente |

## Pagamentos

| Coluna | Descrição |
|---|---|
| id_pagamento | `PAG-ddMMyyHHmm` |
| id_locacao | |
| cliente_nome | |
| placa | |
| data_pagamento | |
| valor | |
| forma_pagamento | `pix`, `ted`, `dinheiro` ou `cartão` |
| referencia | Semana ou vencimento a que se refere (opcional) |
| observacoes | |
| registrado_em | |

## Quilometragem

Histórico de leituras de km. É gravada só pelo sistema. Para ver as colunas exatas, abra o nó **Registrar leitura de km** no workflow.
