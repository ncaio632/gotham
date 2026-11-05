# Módulos e estados — gotham

Resumo da [versão inglesa](architecture.en.md). Os componentes propostos podem funcionar em um processo ou manualmente; não exigem provedor de modelo. Papéis não disparam trabalho em segundo plano.

| Módulo | Responsabilidade e limite |
| --- | --- |
| Entrada | Contexto atribuído e contatos; não verificar alegações automaticamente. |
| Livro de evidências | Fontes, revisão, vínculos e contradições; repetição não prova fato. |
| Coordenação | Responsável e compromissos confirmados; sem promessas sem dono. |
| Composição | Frases com referências, revisão do rascunho; não aprovar/enviar. |
| Aprovação | Decidir sobre versões exatas; não editar silenciosamente texto aprovado. |
| Auditoria | Transições/códigos seguros; sem texto privado ou identificadores pessoais. |

Fluxo: `intake → investigating → drafting → review_pending → approved`. Devolução vai a `revision_required`; lacuna factual retorna a `investigating`, lacuna de redação a `drafting`. Alterar caso ou texto aprovado invalida aprovação. `approved` significa preparação aprovada, sem envio/resolução. Pode-se permanecer investigando sem inventar prazo. Não existe estado `sent`.

Mudanças de contexto, alegações, evidências, responsável ou compromissos incrementam `case_revision`; editar o texto incrementa ambos `case_revision` e `draft_revision`. A decisão de revisão ou projeção de estado registra evento próprio sem alterar essas versões de conteúdo. A aprovação grava ambos e os compara atomicamente com o snapshot atual. Preservar decisões anteriores em futuro histórico interno sem sobrescrita; o exemplo público contém apenas estado fictício atual.

O [schema](../contracts/case-review.schema.json) é um snapshot proposto, mais estrito que o exemplo original; não é API compatível com tickets. Comandos limitados: `recordReport`, `reviewEvidence`, `assignOwner`, `recordCommitment`, `saveDraft`, `reviewDraft`. Não permitir escrita integral para autoaprovação.

Snapshots `intake` e `investigating` podem omitir `owner_role` e `draft`; estados de redação/revisão exigem ambos. A decisão começa `not_reviewed`.

Validação de domínio resolve referências, confirma suporte real da evidência, separa autor/revisor e compara versões. Referência não prova fidelidade da frase. Compromisso `confirmed` precisa de evidência revisada de acordo por responsável autorizado. `due_text` preserva a redação combinada na demonstração; automação de prazos exige modelo próprio de calendário/fuso.

Erros: `CONTEXT_INCOMPLETE`, `REFERENCE_MISSING`, `EVIDENCE_UNREVIEWED`, `COMMITMENT_UNCONFIRMED`, `SELF_REVIEW`, `STALE_REVIEW`. Conflito exige nova leitura; cache não restaura aprovação. Adaptadores de envio ficam fora do projeto.


[Engineering index](index.pt-BR.md)
