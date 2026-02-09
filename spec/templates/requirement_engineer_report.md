# Reporte de Engenharia de Requisitos

## Identificacao
- Role: `requirement_engineer`
- Contexto: <CTX-XXX>
- Periodo/Execucao: <data ou janela>
- Report ID: <NN_requirement_engineer_report>
- Referencias: <spec/00_statement.yaml>

---

## Resumo Executivo
- **Objetivo**: <Resumir o entendimento do problema e da solução proposta>
- **Status**: <concluido|parcial|bloqueado>
- **Impacto**: <qual o impacto para o projeto?>

---

## Entendimento do Contexto

### Problema (Restatement)
> <Reformulação clara do problema em linguagem simples, mostrando causalidade: dado X, o usuário Y enfrenta Z, resultando em W.>

### Solução (Restatement)
> <Reformulação clara da solução proposta: o sistema deveria fazer X para que Y aconteça.>

### Domínio
- **Nome**: <Nome do domínio>
- **Bounded Contexts Identificados**:
  - `<context-id>`: <descrição breve>

### Premissas e Hipóteses
| ID | Premissa/Hipótese | Status | Fonte |
|----|-------------------|--------|-------|
| H1 | <premissa assumida> | <confirmada\|pendente\|refutada> | <statement\|entrevista\|inferido> |

---

## Requisitos Funcionais (FRs)

### Resumo
- **Total**: <N>
- **Must-Have**: <N>
- **Should-Have**: <N>
- **Could-Have**: <N>

### Principais FRs e Justificativas
| ID | Título | Prioridade | Justificativa (Por quê?) |
|----|--------|------------|--------------------------|
| FR-001 | <título> | <must\|should\|could> | <Por que esse requisito é necessário para resolver o problema?> |

---

## Requisitos Não-Funcionais (NFRs)

### Resumo
- **Total**: <N>
- **Categorias ISO 25010 cobertas**: <Security, Maintainability, Performance, ...>

### Principais NFRs e Justificativas
| ID | Categoria (ISO 25010) | Descrição | Prioridade | Justificativa (Por quê?) |
|----|----------------------|-----------|------------|--------------------------|
| NFR-001 | <Security> | <descrição> | <must\|should> | <Por que este NFR é crítico para o contexto?> |

---

## Requisitos Transacionais (TRs) — *se aplicável*

### Resumo
- **Total**: <N>

### Principais TRs e Justificativas
| ID | Transação | Criticidade | Justificativa (Por quê?) |
|----|-----------|-------------|--------------------------|
| TR-001 | <descrição da transação> | <critical\|high\|medium> | <Por que a consistência desta transação é importante?> |

---

## Modelo de Domínio (Resumo)

### Entidades Principais
| Entidade | Descrição | Eventos Associados |
|----------|-----------|-------------------|
| <User> | <descrição> | <UserRegistered, UserDeleted> |

### Eventos de Domínio
- `<EventName>`: <descrição breve e gatilho>

### Bounded Contexts
- `<context-id>`: <responsabilidade principal>

---

## Gaps, Riscos e Questões Abertas

### Gaps Identificados
- [ ] <Gap 1: requisito faltando ou incompleto>
- [ ] <Gap 2>

### Riscos
| Risco | Impacto | Probabilidade | Mitigação |
|-------|---------|---------------|-----------|
| <descrição do risco> | <alto\|médio\|baixo> | <alta\|média\|baixa> | <ação sugerida> |

### Questões Abertas
> Veja `spec/questions/requirement_engineer_open_questions.md` para a lista completa.

---

## Decisões Tomadas

| Decisão | Contexto | Alternativas Consideradas | Racional |
|---------|----------|---------------------------|----------|
| <decisão> | <por que era necessário decidir> | <opção A, opção B> | <por que escolhemos X> |

---

## Handoff Recomendado
- **Próximo Agente**: <software_architect|project_manager>
- **Condição de Pronto**:
  - [ ] Todos os FRs must-have classificados e rastreados
  - [ ] NFRs com prioridades definidas
  - [ ] Modelo de domínio com bounded contexts identificados
  - [ ] Questões críticas respondidas
- **Contexto/Observações**: <riscos, dependências, pontos de atenção para o próximo agente>

---

## Anexos
- **Artefatos Atualizados**:
  - [spec/functional_requirements.yaml](file://spec/functional_requirements.yaml)
  - [spec/non_functional_requirements.yaml](file://spec/non_functional_requirements.yaml)
  - [spec/transactional_requirements.yaml](file://spec/transactional_requirements.yaml)
  - [spec/domain_model.yaml](file://spec/domain_model.yaml)
- **Evidências**: <links para drafts, notas de entrevista, etc.>
