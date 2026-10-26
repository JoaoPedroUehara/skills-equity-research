# tese-equity

Skill do Claude Code que conduz uma tese de investimento sobre ação da B3, enquadrada como
estudo de caso, da pergunta central até a publicação e a atualização trimestral.

Nasceu de duas teses reais, BR Partners (BRBI11) e Sabesp (SBSP3), que aparecem ao longo
do texto como exemplos. A estrutura segue o padrão de skills de Fabio Akita
(github.com/akitaonrails/my-skills): descrição com gatilhos literais, regras invioláveis
antes dos passos, fases com critério de saída e portões, modelo de saída fixo e notas de
design.

## Conteúdo

- `SKILL.md`: o fluxo em dez fases (0 a 9) e as regras.
- `references/armadilhas-dados.md`: armadilhas gerais, da CVM e setoriais (Fase 2).
- `references/arquitetura-excel.md`: padrão de abas, cores e convenções do Excel, com a configuração de cada máquina (Fase 3).
- `references/texto-tese.md`: estrutura do estudo de caso, post, disclaimer e checklist (Fase 8).
- `references/modelo-plano.md`: modelo de `PLANO.md` para uma tese nova (Fase 1).

## Manutenção

Armadilha nova descoberta numa tese → acrescentar em `references/armadilhas-dados.md`.
Reinicie o Claude Code depois de editar a skill.
