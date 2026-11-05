# Roteiro ponta a ponta — gotham

Resumo da [versão inglesa](runbook.en.md). Roteiro manual ou futuro harness local, sem aplicativo fornecido. Não importar mensagens, capturas ou registros reais.

1. Criar `SYN-CASE-A`: relato de status indefinido após duas tentativas sem sucesso. Registrar formulário sem resultado reconhecido e chat sem próximo responsável, inicialmente como relatos. Atribuir `support-owner` à investigação sem prometer solução.
2. Adicionar `SYN-EVIDENCE-A`, registro fictício revisado que comprova apenas “uma consulta de status foi registrada”. Verificar somente essa alegação; o problema amplo continua `reported`. Adicionar `SYN-EVIDENCE-B`, registro fictício revisado que comprova apenas a atribuição da próxima etapa a `support-owner` para análise interna, sem comprovar conclusão. Não incluir compromisso de prazo.
3. Registrar lacunas e revisão atual. Ler tentativas anteriores; não orientar repetição do mesmo caminho ineficaz. Redigir reconhecimento, fato limitado e incerteza. Exemplo fictício: “Você relatou duas tentativas sem sucesso. Uma consulta de status está registrada. A próxima etapa pendente está atribuída ao responsável de suporte para análise interna.” Vincular as frases às alegações. Não enviar.
4. Se o texto disser que um responsável fará uma ação, exigir compromisso confirmado e evidência; caso contrário, buscar confirmação internamente antes de aprovar.
5. Congelar `draft_revision`, passar a `review_pending` e entregar texto, evidências, histórico, responsável e versões exatas a revisor humano distinto. Revisar atribuição, suporte factual, empatia, canais ineficazes e promessas. Aprovar apenas sem bloqueios; `approved` não envia nem resolve.
6. Alterar alegação após aprovação: `revision_required`. Autor aprovando: `SELF_REVIEW`. Edição concorrente: `STALE_REVIEW`. Remover evidência de alegação verificada: schema rejeita. Evidência existente não revisada: domínio rejeita. Prazo sem acordo confirmado: bloquear aprovação mesmo com JSON válido.
7. Adicionar fonte conflitante: manter ambas, classificar como disputada/desconhecida e investigar. Repetir instrução ineficaz sem justificativa: `REPEATED_FAILED_CONTACT`.

Registrar IDs de requisito/teste, massa, revisões do caso/texto, esperado, observado, revisor e `not_run/pass/fail/blocked`. Interromper se surgir dado real, envio na aprovação ou fato sem suporte aprovado. Guardar achados sintéticos e retornar à investigação, sem adaptar evidência ao texto. Conclusão do roteiro não comprova resultado ao cliente, integração ou desempenho.


[Engineering index](index.pt-BR.md)
