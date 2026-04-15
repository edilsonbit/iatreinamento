# Instrucoes de Padrao para o GitHub Copilot

Este arquivo e lido automaticamente pelo GitHub Copilot em todo o repositorio.
Use-o para garantir que a IA sempre siga os padroes do time ao gerar codigo, commits e PRs.

---

## Padrao de Commits (Conventional Commits + Rastreabilidade)

Formato obrigatorio:
```
tipo(escopo): yyyymmdd_numerodaissue descricao-curta-em-ingles
```

Tipos aceitos:
- feat     → nova funcionalidade
- fix      → correcao de bug
- refactor → alteracao sem mudar comportamento externo
- test     → adicao ou correcao de testes
- docs     → alteracao de documentacao
- chore    → manutencao, dependencias ou tarefas auxiliares
- perf     → melhoria de performance

Exemplos corretos:
```
feat(auth): 20260415_1234 adicionar rotacao de token de refresh
fix(api): 20260415_1279 prevenir email nulo no cadastro
test(billing): 20260415_1301 adicionar cobertura para expiracao de desconto
refactor(users): 20260415_1340 extrair validacao de usuario para camada de servico
```

Regras:
- Mensagem sempre em portugues.
- Descricao em minusculo, sem ponto no final.
- Escopo reflete o modulo ou dominio alterado.
- Issue number obrigatorio para rastreabilidade.

---

## Padrao de Branches

Formato:
```
tipo/escopo-descricao-curta
```

Exemplos:
```
feat/payments-add-refund-endpoint
fix/users-handle-empty-display-name
chore/deps-update-node-version
```

---

## Padrao de Pull Request

Titulo: seguir o mesmo formato do commit principal da branch.

Descricao minima:
- **Contexto**: por que essa mudanca foi necessaria.
- **O que mudou**: lista tecnica das alteracoes.
- **Riscos**: possiveis impactos em outros modulos.
- **Evidencias**: testes rodados, screenshots ou logs.

Checklist obrigatorio antes de abrir:
- [ ] Regras de negocio validadas
- [ ] Testes automatizados atualizados
- [ ] Sem segredos ou dados sensiveis no codigo
- [ ] Backward compatibility verificada
- [ ] Logs e observabilidade considerados

---

## Padrao de Nomenclatura de Codigo

- Nomes orientados ao dominio, sem abreviacoes opacas.
- Metodos: verbo + contexto (`calculateInvoiceTotal`, `validateUserPermissions`).
- Evitar: `calc`, `check`, `processData`, `temp`, `data`, `value`.

---

## Padrao de Testes

- Todo novo comportamento deve ter pelo menos um teste de caminho feliz e um de erro.
- Nome do teste: `should_<comportamento>_when_<condicao>`.
- Manter cobertura acima do minimo definido pelo time.

---

## Avisos de Segurança

- Nunca incluir tokens, senhas ou chaves em codigo ou commits.
- Validar entradas em todas as bordas do sistema.
- Revisar dependencias adicionadas para vulnerabilidades conhecidas.
