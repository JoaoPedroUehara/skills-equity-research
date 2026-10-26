# Armadilhas dos dados

Leia na Fase 2. Registre no `PLANO.md` do projeto as que se aplicam, com o tratamento
escolhido. Ao descobrir uma armadilha nova numa tese, acrescente-a aqui na seção certa.

## Gerais (qualquer RI)

| Armadilha | Como tratar |
|---|---|
| Colar célula com fórmula cria vínculo com o arquivo de origem | Sempre **Página Inicial → Colar → Colar Especial → Valores** |
| Unidades misturadas entre blocos (R$ milhões na DRE, R$ mil no BP, R$ no dividendo por ação) | Manter a unidade da fonte no `Historico`, com coluna `Unidade`; converter só na `Analise` |
| Despesas com sinal negativo no RI | Escolher uma convenção, documentar e manter. Índices publicados costumam vir em módulo |
| Blocos que começam em datas diferentes (ex.: BP só a partir de 31/12/2020) | Colar a partir da coluna do primeiro período do bloco; conferir primeira e última coluna depois de colar |
| Dados acumulados no ano (3M, 6M, 9M, 12M) | Trimestre = acumulado − acumulado anterior, exceto no 1T |
| Reapresentação de trimestres passados | Na atualização, recolar o bloco inteiro, não só a coluna nova |
| Mesma linha com valores ligeiramente diferentes em duas abas do RI | Eleger uma aba como fonte (em geral a DRE), documentar e seguir |
| Rótulos do RI mudam de um release para o outro | Comparar rótulos antes de recolar; checagens de soma acusam inserções nos blocos que as têm |
| Índice com definição própria da empresa | Procurar a definição no rodapé ou glossário do RI antes de calcular |
| Média do PL no ROE/ROAE | Testar média simples (início e fim) e média dos trimestres; usar a que reproduz o número publicado e documentar |
| Fato não confirmado repetido de release antigo ou de imprensa | Verificar no RI atual antes de pôr no post |

## CVM Dados Abertos (DFP/ITR)

Arquivos grandes, com todas as companhias abertas; trate no Power Query, não no Excel puro.

1. **`ORDEM_EXERC`**: cada arquivo traz `ÚLTIMO` e `PENÚLTIMO`. Sem filtro, todo valor duplica.
2. **`VERSAO`**: empresas republicam. Manter só a maior versão por `(CD_CVM, DT_REFER)`.
3. **`ESCALA_MOEDA`**: `MIL` ou `UNIDADE`, varia entre empresas. Normalizar antes de comparar.
4. **Consolidado × individual**: usar o consolidado (`_con_`).
5. **ITR é acumulado no ano**: o ITR do 3T traz jan–set e jul–set. Isolar o trimestre por
   `DT_INI_EXERC`/`DT_FIM_EXERC`. É a armadilha que mais gera número errado com cara de certo.
6. **`CD_CONTA` é padronizado** (`3.01` receita, `3.05` EBIT): é o que torna a normalização possível.

## Setoriais

### Concessões e saneamento (ex.: Sabesp)
- **Receita de construção (IFRIC 12/ICPC 01):** margem perto de zero, infla a receita e
  achata a margem. Tratar à parte ou justificar a exclusão.
- **Mudança de controle (privatização):** série histórica cruza dois regimes; comparar
  antes e depois exige nota explícita.
- **Capex regulatório (metas de universalização):** vem do plano da empresa e do
  contrato, não de extrapolação histórica.

### Bancos de investimento e serviços financeiros (ex.: BR Partners)
- **Comp ratio e a régua:** trimestre, semestre, LTM e ano calendário dão números
  diferentes; a meta da gestão pode estar cumprida numa régua e não na outra. Declarar a régua.
- **Folha fixa × variável:** em geral não é aberta. É premissa declarada e sensibilizada.
- **Linhas agrupadas pela própria empresa** (ex.: IB + Mercado de Capitais): não tentar
  separar sem dado.
- **Volume de operações revisado retroativamente:** ler as notas da planilha.
- **Remuneração do capital pode ser negativa** em algum trimestre: não forçar para positivo.
