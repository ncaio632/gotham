# Backlog e rastreabilidade — gotham

Resumo acionável da [versão inglesa](delivery-validation.en.md). Verificações de produto estão **planejadas, não executadas**.

| Ordem | Trabalho e aceitação |
| --- | --- |
| B1 | Definir vocabulário, papéis, regras de revisão e limites de fontes fictícias. |
| B2 após B1 | Entrada e evidências preservam atribuição/histórico, resolvem referências e conservam contradições; nenhuma verificação sem suporte revisado. |
| B3 após B2 | Responsável obrigatório e distinção entre compromisso proposto/confirmado; bloquear prazos e promessas sem autorização. |
| B4 após B3 | Texto com referências por afirmação, incerteza e histórico de canais; devoluções acionáveis. |
| B5 após B4 | Revisão humana de versões exatas, comparação atômica, sem autoaprovação e sem envio; edição invalida aprovação. |
| B6 após B5 | Roteiro executado, evidência sintética e revisão editorial independente; lacunas explícitas. |

Não adicionar adaptador de envio para concluir B5. Futuro envio exige contrato e autorização próprios.

| Requisito | Verificação planejada |
| --- | --- |
| G01 | Contexto ausente pede esclarecimento; relato/histórico mantém atribuição. |
| G02 | Sem evidência/verificador, não marcar verified. |
| G03 | Fonte ausente/não revisada/conflitante bloqueia afirmação e preserva contradição. |
| G04 | Repetir canal falho sem justificativa devolve texto. |
| G05 | Sem responsável ou promessa apenas proposta, bloquear revisão/aprovação. |
| G06 | Exagero factual ou culpa implícita exige correção humana. |
| G07 | Autoaprovação/versões antigas/edição concorrente não aprovam. |
| G08 | Editar texto aprovado invalida aprovação; zero envio e nenhuma resolução inferida. |
| G09 | Exemplos fictícios e logs sem corpo privado. |

Validar [schema](../contracts/case-review.schema.json) com Draft 2020-12. [Válido](../examples/review.valid.json) demonstra forma e aprovação de versões iguais por papéis distintos. [Inválido estrutural](../examples/review.invalid-schema.json) remove `claims[1].evidence_refs` de alegação verificada. [Inválido semântico](../examples/review.invalid-semantic.json) passa estrutura, mas exige `SELF_REVIEW` e `STALE_REVIEW`: revisor é autor e revisão aprovada é antiga.

Schema não verifica verdade, autoridade do responsável, igualdade entre versões ou tom. Domínio resolve referências, compromissos e revisão; pessoa verifica fidelidade e linguagem. Cada evidência futura deve ter IDs, revisões de implementação/massa/caso/texto, ambiente, esperado/observado, revisor e `not_run/pass/fail/blocked`. Aprovação da documentação não prova qualidade do atendimento, satisfação, prazo ou prontidão produtiva. Operação real exige acesso, retenção, escalonamento e fronteira de envio aprovados.


[Engineering index](index.pt-BR.md)
