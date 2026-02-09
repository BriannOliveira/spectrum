# Reporte de Arquitetura de Software

## Identificacao
- Role: `software_architect`
- Contexto: <CTX-XXX>
- Periodo/Execucao: <data ou janela>
- Report ID: <NN_software_architect_report>
- Referencias: <spec/domain_model.yaml, spec/non_functional_requirements.yaml>

---

## Resumo Executivo
- **Objetivo**: <O que foi arquitetado/decidido>
- **Status**: <concluido|parcial|bloqueado>
- **Impacto**: <Impacto nas decisões de implementação>

---

## Estratégia Arquitetural

### Visão Geral
> <Resumo da abordagem arquitetural escolhida e seu alinhamento com os requisitos de negócio.>

### Padrão Arquitetural
| Aspecto | Escolha | Justificativa |
|---------|---------|---------------|
| Padrão Principal | <Hexagonal/Clean/Layered/...> | <Por que este padrão atende os NFRs?> |
| Estilo de Comunicação | <Sync/Async/Hybrid> | <Trade-offs considerados> |
| Estilo de Persistência | <Relational/Document/Event Store> | <Alinhamento com modelo de domínio> |

### Bounded Contexts
| Context ID | Responsabilidade | Dependências | Estilo de Integração |
|------------|------------------|--------------|---------------------|
| <CTX-XXX> | <descrição> | <upstream/downstream> | <API/Events/Shared DB> |

---

## Architecture Decision Records (ADRs)

### ADR-001: <Título da Decisão>
| Campo | Conteúdo |
|-------|----------|
| **Status** | <proposed\|accepted\|deprecated\|superseded> |
| **Contexto** | <Qual problema ou necessidade motivou esta decisão?> |
| **Alternativas Consideradas** | <Opção A, Opção B, Opção C> |
| **Decisão** | <Qual opção foi escolhida?> |
| **Justificativa** | <Por que esta opção é a melhor para o contexto?> |
| **Trade-offs Aceitos** | <Custos, riscos ou limitações aceitas> |
| **Consequências** | <O que muda a partir desta decisão?> |
| **NFRs Relacionados** | <NFR-XXX, NFR-YYY> |

### ADR-002: <Título da Decisão>
| Campo | Conteúdo |
|-------|----------|
| **Status** | <proposed\|accepted\|deprecated\|superseded> |
| **Contexto** | <...> |
| **Alternativas Consideradas** | <...> |
| **Decisão** | <...> |
| **Justificativa** | <...> |
| **Trade-offs Aceitos** | <...> |
| **Consequências** | <...> |
| **NFRs Relacionados** | <...> |

> *Adicione mais ADRs conforme necessário.*

---

## Technology Stack (Resumo)

### Stack Principal
| Camada | Tecnologia | Justificativa |
|--------|------------|---------------|
| Linguagem | <TypeScript/Python/Go/...> | <Por que esta linguagem?> |
| Runtime | <Node.js/JVM/...> | <Alinhamento com NFRs> |
| Framework | <NestJS/FastAPI/Spring/...> | <Produtividade vs Controle> |
| Database | <PostgreSQL/MongoDB/...> | <Modelo de dados e consistência> |
| Messaging | <Kafka/RabbitMQ/none> | <Necessidade de async?> |
| Cache | <Redis/none> | <Padrões de acesso> |

### Observabilidade
| Aspecto | Ferramenta/Abordagem |
|---------|---------------------|
| Logging | <Structured JSON logs> |
| Tracing | <OpenTelemetry> |
| Metrics | <Prometheus/CloudWatch> |
| Alerting | <PagerDuty/OpsGenie/...> |

---

## Estrutura do Projeto

### Organização de Diretórios
```
<context-root>/
├── src/
│   ├── domain/           # Lógica de negócio pura
│   ├── application/      # Use cases / Services
│   ├── infrastructure/   # Adapters (DB, HTTP, Queues)
│   └── presentation/     # Controllers / Handlers
├── tests/
│   ├── unit/
│   ├── integration/
│   └── contract/
└── ...
```

### Responsabilidades por Camada
| Camada | Responsabilidade | Dependências Permitidas |
|--------|------------------|------------------------|
| Domain | <Entidades, Value Objects, Domain Events> | <Nenhuma externa> |
| Application | <Use Cases, Orchestration> | <Domain> |
| Infrastructure | <Persistence, External APIs> | <Application, Domain> |
| Presentation | <HTTP/gRPC handlers> | <Application> |

---

## Mapeamento NFR → Táticas

| NFR ID | Categoria (ISO 25010) | Tática Arquitetural | Implementação |
|--------|----------------------|---------------------|---------------|
| NFR-SEC-001 | Security | <AuthN/AuthZ> | <JWT + RBAC via middleware> |
| NFR-REL-001 | Reliability | <Circuit Breaker> | <Resilience4j / Polly> |
| NFR-MAINT-001 | Maintainability | <Hexagonal Architecture> | <Ports & Adapters> |
| NFR-PERF-001 | Performance | <Caching> | <Redis read-through> |

---

## Riscos e Mitigações

| Risco | Impacto | Probabilidade | Mitigação |
|-------|---------|---------------|-----------|
| <Vendor lock-in com cloud provider> | <alto> | <média> | <Abstrair infraestrutura via ports> |
| <Complexidade de eventos assíncronos> | <médio> | <alta> | <Event sourcing apenas onde necessário> |

---

## Dívidas Técnicas Conhecidas

| ID | Descrição | Impacto | Prioridade | Ticket/Ref |
|----|-----------|---------|------------|------------|
| DEBT-001 | <descrição> | <alto\|médio\|baixo> | <P1\|P2\|P3> | <link> |

---

## Handoff Recomendado
- **Próximo Agente**: <project_manager|backend_developer|frontend_developer>
- **Condição de Pronto**:
  - [ ] ADRs críticos revisados e aceitos
  - [ ] Technology stack definido por contexto
  - [ ] Estrutura de projeto documentada
  - [ ] NFRs mapeados para táticas
- **Contexto/Observações**: <riscos, dependências, pontos de atenção>

---

## Anexos
- **Artefatos Atualizados**:
  - [spec/domains/<context>/plan.yaml](file://spec/domains/<context>/plan.yaml)
  - [spec/domains/<context>/technology_stack.yaml](file://spec/domains/<context>/technology_stack.yaml)
  - [spec/domains/<context>/data_model.yaml](file://spec/domains/<context>/data_model.yaml)
- **Diagramas**: <links para diagramas C4, sequence diagrams, etc.>
