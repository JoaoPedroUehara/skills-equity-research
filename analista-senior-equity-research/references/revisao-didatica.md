# Protocolo da revisão didática

Leia no Modo C. Vale para tese, modelo, texto ou post.

## 1. Preparação

- Leia o `PLANO.md` do projeto: a pergunta da tese, as decisões travadas e a fase atual.
  Revise contra o que o projeto se propôs a fazer, não contra uma tese ideal.
- Leia o `caderno-de-erros.md` e anote as regras que já existem. Elas são a primeira
  coisa a checar.
- Se a revisão foi pedida pela `tese-equity` num portão, revise só o escopo do portão:
  Fase 4 (histórico e validação), Fase 6 (premissas) ou Fase 8 (texto e publicação).

## 2. Ele procura primeiro

Pergunte: "Antes de eu apontar qualquer coisa: onde você acha que está o ponto mais
fraco?". Anote a resposta. Cada erro que ele achou sozinho recebe a marca **achado pelo
aluno** no caderno.

## 3. Varredura por categoria

| Categoria | O que procurar |
|---|---|
| **Dados** | Fonte não primária, unidade ou sinal trocado, acumulado tratado como trimestre, vínculo externo, número que não bate com o release |
| **Contabilidade** | Não recorrente tratado como recorrente, definição de índice diferente da usada pela empresa, competência × caixa |
| **Modelagem** | Número digitado em fórmula, aba com dois papéis, checagem ausente, custo 100% proporcional à receita, referência quebrada |
| **Premissas** | Sem fonte datada, base de partida não justificada, cenários que mudam tudo ao mesmo tempo, premissa não observável apresentada como dado |
| **Valuation** | Método errado para o tipo de empresa, Ke sem componentes defendidos, pares mal escolhidos, data de cotação ausente |
| **Narrativa** | Pergunta ausente, como ganha / como perde / como se adapta sem ligação com números, régua da métrica não declarada, conclusão que os dados não sustentam |
| **Regulatório** | Linguagem de recomendação, preço-alvo, falta de disclaimer, sell-side redistribuído |
| **Comunicação** | Número central escondido, gráfico com duas mensagens, texto que exige o modelo ao lado |

## 4. Formato de cada achado

```markdown
### E-NNN · <categoria> · <🔴|🟠|🟡|⚪> · <dd/mm/aaaa>
- Onde: <arquivo, aba!célula ou trecho>
- O erro: <o que está errado, em uma frase>
- Por que é erro: <o conceito por trás>
- Como um analista sênior faria: <a prática de mercado>
- Correção sugerida: <o que o aluno deve mudar; não aplicar>
- Regra para as próximas teses: <regra curta, no imperativo>
- Origem: <tese / sessão> · achado pelo aluno: <sim | não> · cometido com confiança: <sim | não>
- Repetição de: <E-xxx ou "—">
- Revisar em: <dd/mm/aaaa>
- Status: <aberto | corrigido | consolidado>
```

## 5. Severidade

| Nível | Significado |
|---|---|
| 🔴 Bloqueia | Número errado, validação que não bate, linguagem de recomendação, fonte inexistente |
| 🟠 Grave | Premissa sem justificativa, número digitado dentro de fórmula, vínculo externo, régua não declarada |
| 🟡 Ajuste | Rótulo, unidade, formato, convenção de cor |
| ⚪ Detalhe | Estética, redação que não muda o sentido |

Erro repetido sobe um nível (⚪ → 🟡 → 🟠 → 🔴).

## 6. Fila de revisão (repetição espaçada)

- Achado novo: revisar em 2 dias.
- Revisão acertada: o intervalo dobra (2 → 4 → 8 → 16 dias). Acertou com 16 dias:
  status **consolidado**.
- Revisão errada: volta para 2 dias.
- A revisão é uma pergunta de 2 minutos sobre o conceito, aplicada a um caso novo, e não
  "lembra do erro E-007?".

## 7. Fechamento da revisão

- Apresente os achados do mais grave para o menos grave, com o que ele achou sozinho
  separado.
- Diga uma coisa que melhorou desde a última revisão, se houver evidência no caderno.
- Regra que aparece pela segunda vez: proponha levá-la para a `tese-equity`, dizendo em
  qual seção (regra inviolável, armadilha ou checklist). Edite só com o aval do aluno.
