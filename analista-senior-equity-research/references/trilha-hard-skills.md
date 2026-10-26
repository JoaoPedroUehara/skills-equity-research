# Trilha de hard skills de Equity Research

Leia no Modo A (diagnóstico) e no Modo B (sessão da trilha). Dez blocos. Cada um traz os
tópicos, duas perguntas de diagnóstico, um exercício-âncora com dado real e o critério
de domínio.

## Níveis (iguais para todos os blocos)

| Nível | Significado |
|---|---|
| 0 | Não conhece o conceito ou erra com confiança |
| 1 | Reconhece e define, mas não aplica sem ajuda |
| 2 | Aplica num caso real com ajuda pontual |
| 3 | Aplica sozinho, explica o porquê e acha o próprio erro |

Bloco no nível 3 é revisitado só pela fila de revisão do caderno de erros.

---

## 1. Contabilidade para analistas

**Tópicos:** DRE, BP e DFC e como se ligam; regime de competência × caixa; CPC/IFRS no
Brasil; itens não recorrentes e EBITDA ajustado; capital de giro; IFRS 16
(arrendamentos); ágio e intangíveis; resultado financeiro; minoritários.

**Diagnóstico:**
1. A depreciação aumenta R$ 10. Siga o efeito pelas três demonstrações (alíquota de 34%).
2. Por que o lucro líquido de uma empresa pode crescer enquanto o caixa operacional cai?

**Exercício-âncora:** com o release mais recente de uma empresa em estudo, reconcilie o
lucro líquido com o fluxo de caixa operacional e explique as três maiores diferenças.

**Domínio:** liga as três demonstrações sem consulta e identifica um ajuste não
recorrente num release real.

## 2. Análise de demonstrações

**Tópicos:** margens; ROE, ROIC e ROA; DuPont; alavancagem (dívida líquida/EBITDA);
ciclo de caixa; qualidade do lucro (FCO ÷ LL); crescimento orgânico × aquisição; LTM e
anualização; comparar períodos iguais.

**Diagnóstico:**
1. ROE de 20% com alavancagem alta e ROE de 20% com alavancagem baixa: qual você prefere
   e por quê?
2. Qual a diferença entre ROE e ROIC, e quando cada um é a métrica certa?

**Exercício-âncora:** DuPont de três fatores de uma empresa em estudo para três anos;
explique qual fator moveu o ROE.

**Domínio:** escolhe a métrica certa para o setor e explica o que move cada uma.

## 3. Modelagem financeira

**Tópicos:** arquitetura (entrada → cálculo → saída); convenção de cores; projeção por
drivers; três demonstrações integradas; checagens; cenários e seletor; sensibilidade e
tabela de dados; circularidade (juros sobre caixa médio); atalhos do Excel; diferenças entre
versões (`PROCX` só no 365/2021; no 2019, `ÍNDICE` + `CORRESP`) e separador de argumentos
(`;` ou `,`, conforme a região do Windows). Convenções completas em `tese-equity/references/arquitetura-excel.md`.

**Diagnóstico:**
1. Por que número digitado dentro de fórmula é o primeiro erro que um revisor procura?
2. Como você projeta a despesa de pessoal de uma empresa com bônus atrelado à receita?

**Exercício-âncora:** projetar receita por driver (preço × volume ou saldo × taxa) de uma
empresa em estudo, com três cenários e checagens.

**Domínio:** monta um modelo que outra pessoa entende sem explicação e que não quebra ao
receber um trimestre novo.

## 4. Valuation

**Tópicos:** DCF (FCFF × FCFE); WACC e Ke; CAPM no Brasil (taxa livre de risco, prêmio de
mercado, beta, risco país, moeda nominal × real); perpetuidade e crescimento de longo
prazo; múltiplos (P/L, EV/EBITDA, P/VP, dividend yield); escolha de pares; DDM; soma das
partes; valuation de bancos (P/VP justo = (ROE − g) ÷ (Ke − g)).

**Diagnóstico:**
1. Taxa livre de risco 13%, beta 1,2, prêmio de mercado 5%: qual o Ke pelo CAPM? Mostre a conta.
2. Por que não se usa EV/EBITDA para avaliar um banco?

**Exercício-âncora:** P/VP justo de um banco em estudo pela fórmula de Gordon, comparado
com o P/VP de mercado; o que o mercado está precificando de ROE?

**Domínio:** escolhe o método pelo tipo de empresa e defende cada premissa da taxa de desconto.

## 5. Setoriais

Começar pelos setores das teses em andamento.

- **Bancos e serviços financeiros:** margem financeira, custo de crédito, índice de
  eficiência, Basileia, comp ratio, receitas de serviços, ROAE.
- **Utilities e concessões:** base de remuneração regulatória, WACC regulatório, revisão
  tarifária, IFRIC 12 (receita de construção), capex regulatório.
- **Commodities:** preço × câmbio × custo-caixa, ciclo, curva de custo.
- **Varejo e consumo:** vendas mesmas lojas, giro de estoque, capital de giro, crédito ao consumidor.

**Diagnóstico:**
1. Qual é o principal driver de receita do setor da tese em andamento, e como ele reage à Selic?
2. Cite uma métrica que só existe nesse setor e explique o que ela mede.

**Exercício-âncora:** a tabela "como ganha / como perde" da `tese-equity` (Fase 5) para
uma empresa de outro setor.

**Domínio:** lê o release de uma empresa do setor e aponta o que importa em 5 minutos.

## 6. Macro e mercado

**Tópicos:** Selic e Copom; Focus; curva de juros (DI futuro); inflação (IPCA, IGP-M nos
contratos); câmbio; como cada variável entra nas premissas; consenso de mercado; fluxo e
liquidez na B3.

**Diagnóstico:**
1. A curva de DI inclinou (juro longo subiu mais que o curto). Que tipo de ação sofre
   mais, e por quê?
2. Onde você busca a expectativa de Selic do mercado, e com que frequência ela é publicada?

**Exercício-âncora:** ligar três premissas da tese em andamento a uma variável macro, com
fonte e data.

**Domínio:** transforma uma notícia macro numa mudança de premissa, com o canal explicado.

## 7. Fontes e ferramentas

**Tópicos:** RI (release, planilha de séries, apresentação, teleconferência); CVM Dados
Abertos (DFP/ITR); B3; Banco Central (SGS, Focus); Excel avançado; Power Query; o que são
Bloomberg, Refinitiv, Economatica e Capital IQ (e as alternativas gratuitas); Python e
SQL como acelerador, não como pré-requisito.

**Diagnóstico:**
1. Você precisa de dez anos de DRE trimestral de uma empresa. De onde tira, e qual
   armadilha do ITR você trata?
2. Qual a diferença entre o release e as demonstrações financeiras auditadas, e quando
   cada um é a fonte certa?

**Exercício-âncora:** montar no Power Query a série de receita trimestral de uma empresa
a partir da CVM, isolando o trimestre do acumulado do ano.

**Domínio:** chega ao dado primário certo sem ajuda e documenta a fonte.

## 8. Comunicação de research

**Tópicos:** tese em uma página; earnings preview e earnings note; relatório de
iniciação; gráfico que conta uma coisa só; pitch de 2 minutos; perguntas para a
teleconferência de resultados; escrever para quem tem 30 segundos.

**Diagnóstico:**
1. Resuma a tese em andamento em três frases: o que o mercado pensa, o que você pensa e
   o que prova quem está certo.
2. Que pergunta você faria ao CFO na próxima teleconferência, e por quê?

**Exercício-âncora:** escrever a earnings note do último trimestre da empresa em estudo
em até uma página.

**Domínio:** o texto leva o leitor à conclusão sem precisar do modelo ao lado.

## 9. Ética e regulação na prática

**Tópicos:** Resolução CVM 20 (o que é recomendação, quem pode fazer); disclaimer;
informação privilegiada e período de silêncio; conflito de interesse; como publicar
estudo de caso sem cruzar a linha. A teoria cobrada no CNPI fica fora desta skill; aqui é a
aplicação no que o aluno publica.

**Diagnóstico:**
1. Que palavras transformam um post de estudo de caso em recomendação?
2. Uma pessoa da empresa conta um número antes do release. O que você faz com ele?

**Exercício-âncora:** revisar um post já escrito pela lista de linguagem proibida da
`tese-equity`.

**Domínio:** publica sem risco regulatório, sem precisar de checklist.

## 10. Entrevista

**Banco de perguntas** (usar no Modo D, uma por vez):
- Walk me through a DCF.
- Como as três demonstrações se ligam?
- A depreciação sobe R$ 10: o que acontece em cada demonstração?
- Por que o Ke de uma empresa brasileira é maior que o de uma americana do mesmo setor?
- Quando o P/L engana?
- Como você avalia um banco?
- Me venda uma ação em 2 minutos (pitch).
- Qual a sua tese mais fraca, e por quê?
- O que mudaria a sua visão sobre a <empresa da tese>?
- Um caso de modelagem: projetar a receita de uma empresa a partir de um release.

**Domínio:** responde com estrutura (conclusão primeiro, depois o porquê) e defende a
própria tese sob pressão sem recuar do que os dados mostram.
