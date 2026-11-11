# Receita: Perfil de Comunicação de {{NOME}}

## O que vamos preparar

Um **perfil de comunicação** do criador — um documento que descreve o jeito dele de falar
(ganchos, retenção, storytelling, vocabulário) com tanta fidelidade que daria pra escrever
no tom de voz dele a partir da leitura.

## Como informar os ingredientes (via prompt)

Você passa os ingredientes na hora de pedir a receita, em linguagem natural. Não precisa
seguir formato rígido — só deixe claro **de quem** é o perfil. Exemplos de pedido:

- "Monte o perfil de comunicação da conta @michamenezes."
- "Faça o perfil do Micha Menezes (@michamenezes), salvando na pasta `michamenezes`."
- "Perfil de comunicação de @joaosilva, nome João Silva."

A partir do que foi dito, resolva os ingredientes assim:

- **Conta no Instagram** `{{CONTA}}` — o @ sem o arroba (ex: `michamenezes`). **Obrigatório.**
  Se não foi informado, **pergunte antes de começar**.
- **Nome do criador** `{{NOME}}` — ex: Micha Menezes. Se não foi informado, use o `@{{CONTA}}`
  como nome provisório.
- **Pasta do projeto** `{{PASTA}}` — onde os dados serão armazenados.
  **Se o nome da pasta não foi informado explicitamente, assuma `{{CONTA}}`** (o mesmo nome da conta).
- **Apelido curto** `{{SLUG}}` — usado pra nomear arquivos. Se não foi informado, use `{{PASTA}}`.

## Onde os dados são armazenados

Tudo fica dentro de **`projetos/{{PASTA}}/`**:

- `projetos/{{PASTA}}/dados/` — lista de vídeos, transcrições e os arquivos de análise.
- `projetos/{{PASTA}}/perfil-{{SLUG}}.md` — o perfil final.

Se a pasta `projetos/{{PASTA}}/` ainda não existir, crie-a (junto com a subpasta `dados/`).

## Equipamentos (ferramentas que fazem o trabalho braçal)

- **Coletor de lista de vídeos** → `resources/mcps/instagram-lista-videos-csv`
- **Baixador dos melhores vídeos** → `resources/mcps/instagram-top-videos-download`
- **Transcritor de vídeos** → `resources/mcps/video-transcricao`

## Técnicas (saberes que a IA domina)

- **Análise de ganchos** → `.claude/skills/ig-analise-ganchos`
- **Análise de retenção** → `.claude/skills/ig-analise-retencao`
- **Análise de storytelling** → `.claude/skills/ig-analise-storytelling`
- **Análise de vocabulário** → `.claude/skills/ig-analise-vocabulario`
- **Montagem do perfil de comunicação** → `.claude/skills/ig-perfil-comunicacao`

## Modo de preparo

### Etapa 0 — Prepare a pasta do projeto

- [ ] Resolva os ingredientes a partir do prompt (veja "Como informar os ingredientes").
- [ ] Garanta que `projetos/{{PASTA}}/dados/` exista (crie se necessário).

### Etapa 1 — Coleta de Dados

> Salve tudo em `projetos/{{PASTA}}/dados/`.

- [ ] Baixe a **lista de vídeos** da conta @{{CONTA}}. _(equipamento: Coletor de lista de vídeos)_
- [ ] Baixe os **10 melhores vídeos** da conta @{{CONTA}}. _(equipamento: Baixador dos melhores vídeos)_
- [ ] **Transcreva** todos os vídeos baixados. _(equipamento: Transcritor de vídeos)_

### Etapa 2 — Analise das Transcrições

> Trabalhe sempre dentro da pasta `projetos/{{PASTA}}/dados/`.

- [ ] Aplique a **análise de ganchos** → salve o resultado em `ig-analise-ganchos.md`. _(técnica: Análise de ganchos)_
- [ ] Aplique a **análise de retenção** → salve em `ig-analise-retencao.md`. _(técnica: Análise de retenção)_
- [ ] Aplique a **análise de storytelling** → salve em `ig-analise-storytelling.md`. _(técnica: Análise de storytelling)_
- [ ] Aplique a **análise de vocabulário** → salve em `ig-analise-vocabulario.md`. _(técnica: Análise de vocabulário)_

### Etapa 3 — Finalização (monte o prato)

- [ ] Com as quatro análises prontas, aplique a **montagem do perfil de comunicação** usando-as como base → salve em `projetos/{{PASTA}}/perfil-{{SLUG}}.md`. _(técnica: Montagem do perfil de comunicação)_

## Verificação Final

- [ ] Os dados foram salvos em `projetos/{{PASTA}}/` (a pasta assume o nome da conta quando não informada).
- [ ] Existem transcrições para os 10 vídeos baixados (nenhuma vazia ou só com ruído).
- [ ] Os quatro arquivos de análise existem e nenhum está vazio.
- [ ] O arquivo `perfil-{{SLUG}}.md` foi gerado.
- [ ] O perfil **cita exemplos concretos** tirados das transcrições (frases reais do criador), não descrições genéricas.
- [ ] O perfil cobre as **quatro dimensões**: ganchos, retenção, storytelling e vocabulário.
- [ ] Teste do palito: alguém que nunca viu o {{NOME}} conseguiria imitar o tom de voz dele lendo só o perfil.

## Resultado Final

O arquivo **`projetos/{{PASTA}}/perfil-{{SLUG}}.md`** — um perfil de comunicação pronto pra ser usado
como ingrediente em outras receitas (por exemplo, "gerar 10 roteiros no tom de voz de {{NOME}}").
