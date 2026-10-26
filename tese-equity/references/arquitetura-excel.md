# Arquitetura do modelo em Excel

Leia na Fase 3. É o padrão consolidado num modelo real de banco de investimento (BR
Partners) e vale, com adaptações, para qualquer setor.

## Três princípios, em ordem de importância

1. **Cada aba tem um papel: entrada → cálculo → saída.** O leitor percorre da esquerda
   para a direita.
2. **Mesma coluna = mesmo período em todas as abas temporais.** `A` = indicador,
   `B` = unidade, e a partir de `C` os períodos, iguais em `Historico`, `Analise` e
   qualquer outra aba com tempo. Toda referência entre abas fica direta
   (`=Historico!C9`), sem camada de busca exposta ao leitor.
3. **Número digitado só nas abas de entrada** (`Historico` e `Premissas`). Convenção de
   mercado para a cor da fonte: **azul** = digitado, **preto** = fórmula, **verde** =
   referência a outra aba.

## Abas padrão

| # | Aba | Papel | Cor da guia |
|---|---|---|---|
| 0 | `Capa` | Título, pergunta da tese, índice das abas, legenda de cores, checagem geral, fonte, disclaimer | Azul-escuro |
| 1 | `Historico` | Números da fonte colados como valores; espelho fiel | Azul (entrada) |
| 2 | `Analise` | Índices, mix, crescimento, LTM, teste de validação | Cinza (cálculo) |
| 3 | `Premissas` | Três cenários com referência e justificativa por linha | Azul (entrada) |
| 4 | `Cenarios` | Demonstração projetada nos três cenários | Cinza (cálculo) |
| 5 | `Sensibilidade` | Número central da tese + tabela de dados | Verde (saída) |
| 6 | `Valuation` | Múltiplos, pares, ROE implícito ou DCF | Verde (saída) |

Adapte ao setor (ex.: uma aba `Capex` numa concessão), mas mantenha a ordem
entrada → cálculo → saída.

## Convenções

- **Excel da máquina do aluno**, registrado no `PLANO.md` (veja a seção abaixo).
- **Checagens visíveis:** cada soma relevante tem uma célula `OK`/`ERRO`, e a `Capa`
  resume todas numa checagem geral.
- **Formato de percentual:** `0.0%;(0.0%);"–"` (com a vírgula como decimal se a máquina
  for pt-BR: `0,0%;(0,0%);"–"`). Negativo entre parênteses, zero como traço.
- **Sem linhas de grade**, painéis congelados no primeiro dado, cabeçalhos e faixas de
  seção com o mesmo estilo em todas as abas.
- **Premissas:** colunas Premissa | Unidade | Pessimista | Base | Otimista | Referência
  | Justificativa. Onde Base e Otimista repetem o Pessimista, use fórmula (`=C14`) em fonte preta.
- **Pessoal na projeção:** parte fixa × (1 + crescimento da folha) + parte variável ×
  (receita projetada ÷ receita base). É essa linha que mostra a alavancagem operacional.
- **Tabela de dados:** Dados → Teste de Hipóteses → Tabela de Dados, com as entradas na
  mesma aba da tabela.

## Configuração do Excel

Pergunte na Fase 0 e registre no `PLANO.md`: **versão** (365, 2021, 2019...), **idioma
das funções** (português ou inglês) e **separadores**. O idioma do Excel define o nome
das funções e dos menus; a região do Windows define os separadores. Toda fórmula, código
de formato e caminho de menu que você escrever segue o que está registrado.

**Separadores:**

| Região do Windows | Argumentos | Decimal | Exemplo |
|---|---|---|---|
| Português (Brasil), o mais comum | `;` | `,` | `=SE(ABS(C41)>0,001;"ERRO";"OK")` |
| Inglês (EUA) | `,` | `.` | `=SE(ABS(C41)>0.001,"ERRO","OK")` |

Códigos de formato seguem o mesmo padrão: `#.##0,0;(#.##0,0);"–"` em pt-BR e
`#,##0.0;(#,##0.0);"–"` em en-US. Misturar os dois já gerou formato quebrado
(`#.##00`) num projeto real.

**Funções** (nome em português; em inglês entre parênteses):

| Uso | Funciona em todas | Só no 365/2021 |
|---|---|---|
| Busca | `ÍNDICE` + `CORRESP` (`INDEX` + `MATCH`), `PROCV` (`VLOOKUP`) | `PROCX` (`XLOOKUP`), `CORRESPX` (`XMATCH`) |
| Seletor de cenário | `ESCOLHER` (`CHOOSE`) ou `ÍNDICE` + `CORRESP` | — |
| Condição | `SE`, `SES`, `SEERRO`, `E`, `OU` | — |
| Soma e média condicionais | `SOMASES`, `MÉDIASES`, `CONT.SES` | — |
| Arredondar e módulo | `ARRED`, `ABS` | — |
| Matrizes | — | `FILTRO`, `CLASSIFICAR`, `ÚNICO`, `SEQUÊNCIA`, `LET`, `LAMBDA` |

Mesmo no 365, prefira `ÍNDICE` + `CORRESP` se o modelo for circular entre pessoas com
versões diferentes.

**Caminhos de menu usados no modelo** (Excel em português; guias: Arquivo, Página
Inicial, Inserir, Desenhar, Layout da Página, Fórmulas, Dados, Revisão, Exibir):

| Ação | Caminho |
|---|---|
| Colar só os valores | Página Inicial → Colar → Colar Especial → Valores |
| Formatação condicional | Página Inicial → Formatação Condicional |
| Formato de número personalizado | Página Inicial → Número → Mais Formatos de Número → Personalizado |
| Tabela de dados | Dados → Teste de Hipóteses → Tabela de Dados |
| Atingir meta | Dados → Teste de Hipóteses → Atingir Meta |
| Validação (lista suspensa do seletor) | Dados → Validação de Dados |
| Rastrear precedentes e dependentes | Fórmulas → Rastrear Precedentes / Rastrear Dependentes |
| Nomes de célula | Fórmulas → Gerenciador de Nomes |
| Congelar painéis | Exibir → Congelar Painéis |
| Ocultar linhas de grade | Exibir → desmarcar Linhas de Grade |
| Cor da guia | botão direito na guia → Cor da Guia |

## Especificação por aba

Para cada aba, um `LAYOUT_<ABA>.md` na pasta do projeto, com: grade (colunas, larguras,
formatos), tabela célula a célula (rótulo, fórmula, formato) e versão com data. O aluno
constrói a partir dele.

## Gravação direta no arquivo (só com pedido explícito)

Excel fechado; backup datado em `_backups/`; depois de gravar, reabrir e conferir que as
abas não tocadas continuam idênticas e que as checagens seguem `OK`.
