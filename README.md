# Skills de Equity Research para o Claude Code

Duas skills do [Claude Code](https://claude.com/claude-code) para quem está aprendendo
Equity Research na prática, com ações da B3:

| Skill | O que faz |
|---|---|
| [`tese-equity`](tese-equity/) | Conduz uma tese de investimento como estudo de caso, em dez fases: pergunta central, fonte primária no RI, modelo em Excel validado contra o release, como a empresa ganha, perde e se adapta, premissas em três cenários, sensibilidade, texto, post no LinkedIn e atualização trimestral. |
| [`analista-senior-equity-research`](analista-senior-equity-research/) | Um analista sênior que ensina: diagnóstico em dez blocos de hard skills, sessões de trilha, revisão didática das teses (erro → por quê → correção → regra) com caderno de erros e repetição espaçada, e treino de entrevista. |

As duas trabalham juntas. A `tese-equity` conduz o projeto e, nos portões das Fases 4
(validação), 6 (premissas) e 8 (texto), chama a `analista-senior-equity-research` para
revisar. Uma regra que aparece duas vezes no caderno de erros vira regra da
`tese-equity`, e assim o processo melhora a cada tese.

A filosofia é que **você constrói e o Claude orienta**. Ele especifica, pergunta,
questiona e revisa, mas não escreve o modelo nem o texto no seu lugar. É portfólio para
entrevista: se você não sabe explicar uma célula, ela não entra.

## Instalação

Precisa do Claude Code instalado. Clone o repositório e copie as duas pastas para a
pasta de skills do seu usuário:

**Windows (PowerShell)**
```powershell
git clone https://github.com/JoaoPedroUehara/skills-equity-research.git
Copy-Item -Recurse skills-equity-research\tese-equity, skills-equity-research\analista-senior-equity-research "$env:USERPROFILE\.claude\skills\"
```

**macOS / Linux**
```bash
git clone https://github.com/JoaoPedroUehara/skills-equity-research.git
mkdir -p ~/.claude/skills
cp -r skills-equity-research/tese-equity skills-equity-research/analista-senior-equity-research ~/.claude/skills/
```

Reinicie o Claude Code. Para conferir, digite `/` e procure as duas skills na lista.

## Primeiros passos

1. **Diagnóstico:** "analista sênior, quero começar a trilha de Equity Research". Na
   primeira sessão ele pergunta seu nome, seu objetivo e a tese em andamento, e aplica
   duas perguntas por bloco. Responda com o grau de confiança (sei / acho / não sei).
2. **Tese:** "nova tese da <empresa>". Na Fase 0 ele pergunta como é o seu Excel
   (versão, idioma e separador `;` ou `,`) para escrever as fórmulas no formato certo.
3. **Revisão:** "revisa minha tese" ou "onde eu errei".

## Onde ficam seus arquivos

As skills não guardam estado dentro delas. O progresso fica em pastas suas:

```
~/Projetos/
├── equity-research-mentoria/      trilha, caderno de erros e log das sessões
│   ├── trilha.md
│   ├── caderno-de-erros.md
│   └── sessoes/
└── NN-tese-<empresa>/             um projeto por tese, com PLANO.md e o modelo
```

São criadas na primeira vez que você usa cada skill. Para usar outro lugar, troque
`~/Projetos/` nos arquivos `SKILL.md` e em
`analista-senior-equity-research/references/modelos-estado.md`.

Se você versionar suas teses no GitHub, não suba relatórios de sell-side (em geral têm
cláusula de não redistribuição) nem livros em PDF.

## Aviso regulatório

As skills tratam toda tese como **estudo de caso educacional**, sem recomendação de
compra, venda ou manutenção e sem preço-alvo. Recomendação de valor mobiliário é
atividade regulada, exclusiva de analista credenciado (Resolução CVM nº 20/2021). O
disclaimer usado nas publicações está em
[`tese-equity/references/texto-tese.md`](tese-equity/references/texto-tese.md).

## Personalização

As skills são texto em Markdown, então dá para editar à vontade: acrescentar armadilhas
de um setor novo em `tese-equity/references/armadilhas-dados.md`, perguntas de
entrevista no bloco 10 da trilha ou outro setor no bloco 5. Reinicie o Claude Code
depois de editar.

Criadas por João Pedro Uehara. A estrutura segue o padrão de skills de Fabio Akita
([akitaonrails/my-skills](https://github.com/akitaonrails/my-skills)).
