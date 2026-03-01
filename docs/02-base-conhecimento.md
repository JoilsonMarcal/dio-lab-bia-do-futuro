# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores, evitando respostas repetidas e mantendo continuidade no atendimento |
| `perfil_investidor.json` | JSON | Identificar perfil de risco, objetivos financeiros e preferências do cliente |
| `produtos_financeiros.json` | JSON | Sugerir produtos financeiros compatíveis com o perfil do investidor |
| `transacoes.csv` | CSV | Analisar padrão de gastos, recorrência de despesas e comportamento financeiro |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

[Os dados simulados foram adaptados para aumentar o realismo e a utilidade do agente, incluindo:

Normalização de categorias de gastos (ex: “Alimentação”, “Lazer”, “Serviços”)

Inclusão de datas, valores e descrições padronizadas nas transações

Expansão do perfil do investidor com campos como:

objetivo financeiro (curto, médio ou longo prazo)

tolerância a risco

horizonte de investimento

Enriquecimento dos produtos financeiros com:

nível de risco

liquidez

valor mínimo de aplicação]

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

[Os arquivos JSON e CSV são carregados no início da sessão do agente. Após a leitura, os dados relevantes são transformados em estruturas internas (listas e dicionários) e incorporados ao contexto do prompt.

Em cenários mais avançados, os dados podem ser consultados dinamicamente conforme a intenção do usuário]

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

[Os dados não são solicitados explicitamente pelo sistema ao usuário

Eles são utilizados como contexto implícito, permitindo que o agente:

personalize respostas

faça inferências sobre comportamento financeiro

gere recomendações alinhadas ao perfil]

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil do investidor: Moderado
- Objetivo financeiro: Médio prazo
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado – R$ 450 (Alimentação)
- 03/11: Streaming – R$ 55 (Lazer)
- 05/11: Energia elétrica – R$ 180 (Serviços)
- 08/11: Restaurante – R$ 120 (Alimentação)

Interações anteriores:
- Cliente demonstrou interesse em investimentos de baixo a médio risco
- Preferência por liquidez acima de 30 dias
...
```
