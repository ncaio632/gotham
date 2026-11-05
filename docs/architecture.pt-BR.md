# Arquitetura

[README](../README.pt-BR.md)

## Fluxo de processamento

```text
Inbound report → facts versus allegations → context review → owner assignment → draft → human approval
```

## Invariantes

1. Distinguir o relato do cliente dos fatos verificados independentemente.
2. Consultar tentativas anteriores antes de sugerir novamente o mesmo canal.
3. Não prometer data de pagamento, resultado ou retorno sem responsável e compromisso confirmados.
4. Manter detalhes pessoais dos casos fora de exemplos públicos e registros técnicos.
5. A aprovação humana é um limite obrigatório para comunicação externa.

## Limite da implementação

Fluxo editorial e contratos de referência. Não se afirma a existência de envio autônomo, integração de chamados ou SLA medido.
