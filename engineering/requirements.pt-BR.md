# Requisitos — gotham

Resumo acionável da [especificação inglesa](requirements.en.md), derivada do [fluxo público](../docs/architecture.pt-BR.md). O repositório descreve preparação editorial; não oferece envio autônomo, integração com tickets nem SLA medido. Módulos e validações são propostos.

A saída é um rascunho revisado com fatos rastreáveis e próximo passo sob responsabilidade definida. Enviar, reembolsar, alterar cadastro e concluir responsabilidade jurídica ficam fora do escopo. Relato comprova que houve uma declaração, não necessariamente o fato relatado; falta de evidência interna também não prova erro do cliente.

| ID | Comportamento obrigatório proposto |
| --- | --- |
| G01 | Registrar referência fictícia, canal, resumo atribuído e contatos prévios. Pedir esclarecimento sem inventar eventos/datas. |
| G02 | Classificar alegações como `reported`, `verified`, `disputed`, `unknown`. Verificada exige evidência revisada e papel verificador. |
| G03 | Vincular fontes e revisão às alegações. Fonte aprovada não torna tudo verdadeiro; contradição exige investigação. |
| G04 | Ler contatos anteriores e seus resultados. Não repetir canal ineficaz sem justificativa; oferecer alternativa com responsável. |
| G05 | Exigir um responsável antes da revisão. Promessa exige compromisso confirmado, responsável, prazo textual e evidência; sem isso, bloquear aprovação. |
| G06 | Vincular frases factuais às alegações e atribuir relatos não resolvidos. Empatia não pode afirmar culpa ou garantir resultado. |
| G07 | Aprovação humana da revisão exata do caso e rascunho; revisor diferente do autor. Revisão antiga ou bloqueio impede `approved`. |
| G08 | Aprovação não envia. Edição posterior invalida aprovação. Não chamar rascunho de enviado/resolvido sem evidência separada. |
| G09 | Exemplos e evidências técnicas somente fictícios. Logs sem corpos de mensagens; dado sensível bloqueia publicação. |

A interface deve separar relatos e constatações, mostrar tentativas anteriores, lacunas, responsável e compromissos junto do texto. O revisor vê texto e versões exatas; motivos de devolução incluem `MISSING_EVIDENCE`, `REPEATED_FAILED_CONTACT`, `UNCONFIRMED_COMMITMENT`, `STALE_REVIEW`. Pode haver acolhimento com fatos pendentes, explicitando incerteza sem prometer solução/prazo. Encerrar preparação não resolve o problema.

Antes de implementação real, definir fontes autorizadas, validade de evidência, acesso, escalonamento, retenção e casos sensíveis. Separação autor/revisor é decisão de projeto, não política operacional comprovada. Autoridade de compensação, canais e autorização de envio continuam indefinidos.


[Engineering index](index.pt-BR.md)
