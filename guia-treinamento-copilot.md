# Guia de Treinamento: Desenvolvedor Assistido por IA com GitHub Copilot

## 1. Objetivo

Capacitar desenvolvedores a usar GitHub Copilot no GitHub e no VS Code para acelerar entrega de software sem perder qualidade, seguranca e padrao de engenharia.

Resultado esperado:
- Menor tempo de implementacao por tarefa.
- PRs mais claros e com melhor qualidade de revisao.
- Aumento de produtividade com rastreabilidade tecnica.

## 2. Publico-alvo

- Desenvolvedores junior, pleno e senior.
- Tech leads e reviewers.
- Times que ja usam GitHub e VS Code no fluxo diario.

## 3. Estrutura do treinamento

Sugestao de formato:
- Turma: 10 a 25 pessoas.
- Duracao: 6 horas (imersao) ou 10 horas (2 encontros).
- Metodo: 30% teoria + 70% pratica guiada.

Agenda sugerida (6h):
1. Mudanca de mindset: de code writer para code reviewer/tester (40 min)
2. Fundamentos do GitHub Copilot (30 min)
3. Copilot no VS Code: fluxo completo (80 min)
4. Copilot no GitHub: PR, review e issues (45 min)
5. Padroes de mercado: commit, branch, nomenclatura e PR (45 min)
6. Laboratorio pratico por squads (90 min)
7. Debrief com metricas e plano de adocao (30 min)

## 4. Setup minimo para a turma

Checklist tecnico:
- Conta GitHub com licenca Copilot ativa.
- VS Code atualizado.
- Extensoes:
  - GitHub Copilot
  - GitHub Copilot Chat
- Projeto de exemplo clonado localmente.
- Suite de testes executando localmente.

Checklist de governanca:
- Politica de dados e seguranca definida (o que pode ou nao pode ir para prompts).
- Definicao de ownership de revisao e aprovacao.

## 5. Conteudo detalhado por modulo

### Modulo A: Mindset e responsabilidades

Mensagem central:
- IA acelera escrita e exploracao de solucoes.
- Desenvolvedor continua dono de corretude, seguranca, performance e manutencao.

Pontos obrigatorios:
- Quando confiar e quando desconfiar da sugestao.
- Como evitar dependencia cega.
- Como validar regra de negocio e edge cases.

### Modulo B: Copilot no VS Code

Demonstracoes:
1. Gerar implementacao inicial a partir de requisitos.
2. Pedir refactor para melhorar legibilidade.
3. Gerar testes unitarios com cenarios felizes e de erro.
4. Pedir analise de risco de regressao.
5. Pedir explicacao de codigo legado.

Fluxo recomendado de trabalho no editor:
1. Abrir ticket e resumir objetivo no chat.
2. Pedir plano de implementacao em passos pequenos.
3. Implementar em commits pequenos.
4. Rodar testes locais a cada passo.
5. Pedir review automatizada no final.
6. Ajustar diff antes de abrir PR.

### Modulo C: Copilot no GitHub

Demonstracoes:
- Criar descricao de PR mais objetiva.
- Revisar diff com ajuda da IA para detectar riscos.
- Melhorar qualidade de discussoes em review.
- Resumir issue e quebrar em subtarefas tecnicas.

### Modulo D: Padroes de mercado

#### D.1 Conventional Commits

Padrao:
- feat: nova funcionalidade
- fix: correcao de bug
- refactor: alteracao sem mudar comportamento externo
- test: alteracao em testes
- docs: alteracao de documentacao
- chore: manutencao e tarefas auxiliares

Formato recomendado para rastreabilidade:
- tipo(escopo): yyyymmdd_numerodaissue descricao-curta

Exemplo de estrutura:
- feat(auth): 20260415_1234 add refresh token rotation

Exemplos:
- feat(auth): 20260415_1234 add refresh token rotation
- fix(api): 20260415_1279 prevent null email in signup payload
- test(billing): 20260415_1301 add coverage for discount expiration

#### D.2 Nomenclatura de branches

Sugestao:
- feat/<escopo>-<descricao>
- fix/<escopo>-<descricao>
- chore/<escopo>-<descricao>

Exemplos:
- feat/payments-add-refund-endpoint
- fix/users-handle-empty-display-name

#### D.3 Padrao para PR

Titulo:
- Seguir Conventional Commit principal.

Descricao minima:
- Contexto da mudanca.
- O que foi alterado.
- Riscos e impactos.
- Evidencias de testes.

Checklist:
- [ ] Regras de negocio revisadas
- [ ] Testes automatizados atualizados
- [ ] Sem segredos ou dados sensiveis
- [ ] Backward compatibility validada
- [ ] Logs e observabilidade considerados

#### D.4 Padrao de nomenclatura de codigo

Boas praticas:
- Nomes orientados a dominio, nao abreviacoes opacas.
- Metodos em formato verbo + contexto.
- Evitar nomes genericos como data, value, temp.

Exemplos:
- Bom: calculateInvoiceTotal
- Bom: validateUserPermissions
- Evitar: calc, check, processData

## 6. Engenharia de prompt para devs

Template de prompt padrao:

```text
Voce e um engenheiro de software senior.
Contexto: [stack, modulo, restricoes].
Objetivo: [resultado esperado].
Regras: [padrao de codigo, performance, seguranca, testes].
Saida: [codigo + testes + explicacao curta + riscos].
```

Boas praticas:
- Sempre incluir contexto tecnico real.
- Solicitar resposta incremental, nao monolitica.
- Pedir alternativas com trade-offs.
- Pedir casos de teste e riscos antes de finalizar.

## 7. Exercicio pratico em sala

Cenario sugerido:
- Entregar uma pequena feature de API com validacao, testes e PR.

Passos:
1. Squad recebe user story e criterios de aceite.
2. Usa Copilot para montar plano tecnico.
3. Implementa em pares com commits pequenos.
4. Gera testes e roda suite.
5. Abre PR com checklist completo.
6. Outro squad revisa e aprova com feedback.

Criterios de avaliacao:
- Qualidade do diff.
- Cobertura de testes.
- Clareza da PR.
- Aderencia aos padroes definidos.

## 7.1 Glossario rapido de nomenclaturas

- diff: diferenca entre o codigo antigo e o novo em um commit ou PR.
- commit: conjunto pequeno de alteracoes com mensagem descritiva e rastreavel.
- branch: linha isolada de trabalho para uma feature, bugfix ou tarefa tecnica.
- PR (Pull Request): solicitacao de revisao para integrar uma branch.
- review: avaliacao tecnica do PR para validar qualidade e risco.
- issue: item rastreavel no backlog (bug, melhoria ou tarefa).

## 8. Metricas para provar ganho de produtividade

Acompanhar por 30 a 60 dias:
- Lead time medio por tarefa.
- Tempo medio de review.
- Taxa de reabertura de bug.
- Taxa de retrabalho apos QA.
- Satisfacao do time com o novo fluxo.

Sugestao de meta inicial:
- Reduzir lead time em 15% a 25%.
- Reduzir tempo de review em 10% a 20%.

## 9. Riscos e mitigacoes

Risco: dependencia cega da IA.
- Mitigacao: checklist tecnico obrigatorio antes de merge.

Risco: vazamento de informacao sensivel em prompt.
- Mitigacao: politica clara de dados e revisao de seguranca.

Risco: queda de padrao arquitetural por sugestoes aleatorias.
- Mitigacao: templates de prompt com regras de arquitetura.

## 10. Plano de adocao apos treinamento

Semana 1:
- Ativar padroes minimos (commit, branch, PR).
- Definir champions por squad.

Semana 2:
- Rodar pair programming com IA em tarefas reais.

Semana 3:
- Medir primeiras metricas e ajustar processo.

Semana 4:
- Publicar playbook interno oficial.

## 11. Materiais de apoio para voce usar no dia

- Pagina de apresentacao: `apresentacao-treinamento-copilot.html`
- Este guia completo: `guia-treinamento-copilot.md`

Sugestao de conducao:
1. Comecar com casos reais do seu time.
2. Demonstrar erros comuns de uso do Copilot.
3. Mostrar o fluxo correto com revisao e testes.
4. Fechar com plano pratico de 30 dias.
