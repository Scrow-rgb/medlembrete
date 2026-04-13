# Planejamento do Projeto — MedLembrete

## Visão Geral das Sprints

O projeto segue o processo Scrum com sprints quinzenais. O planejamento é gerenciado via **GitHub Projects** (aba Projects deste repositório).

---

## Organização do GitHub Projects

O board possui as seguintes colunas:

| Coluna | Descrição |
|--------|-----------|
| **Project Backlog** | Todos os requisitos funcionais do projeto |
| **TODO** | Itens planejados para a sprint atual |
| **In Progress** | Itens em desenvolvimento |
| **Done** | Itens concluídos e entregues |

---

## Sprint 1 — TP2 (Fundação do sistema)

**Objetivo:** Estrutura do projeto, autenticação de usuários e cadastro básico de medicamentos.

| ID | História | Estimativa |
|----|----------|------------|
| RF01 | Cadastro de usuário | 3 pts |
| RF02 | Login de usuário | 2 pts |
| RF03 | Cadastrar medicamento | 3 pts |
| RF04 | Definir horários de administração | 3 pts |
| RF05 | Informar data de início/fim | 2 pts |
| RF06 | Visualizar lista de medicamentos ativos | 2 pts |

**Entregáveis esperados:**
- Banco de dados configurado com as tabelas `users`, `medications` e `schedules`
- API REST com endpoints de autenticação e CRUD de medicamentos
- Telas de cadastro, login e listagem de medicamentos

---

## Sprint 2 — TP3 (Núcleo funcional)

**Objetivo:** Registro de doses, painel diário e edição de medicamentos.

| ID | História | Estimativa |
|----|----------|------------|
| RF07 | Registrar administração de dose | 3 pts |
| RF08 | Visualizar histórico de administração | 2 pts |
| RF09 | Painel diário com status das doses | 4 pts |
| RF10 | Editar medicamento cadastrado | 2 pts |

**Entregáveis esperados:**
- Tabela `dose_records` no banco de dados
- Endpoint de registro de dose
- Painel principal com status de hoje
- Fluxo de edição de medicamentos

---

## Sprint 3 — TP4 (Complementos e qualidade)

**Objetivo:** Funcionalidades de encerramento de tratamento, relatório de adesão e recuperação de senha.

| ID | História | Estimativa |
|----|----------|------------|
| RF11 | Desativar/excluir medicamento | 2 pts |
| RF12 | Relatório de adesão semanal | 4 pts |
| RF13 | Redefinição de senha via e-mail | 3 pts |

**Entregáveis esperados:**
- Lógica de desativação mantendo histórico
- Cálculo de percentual de adesão por medicamento
- Integração com serviço de e-mail para reset de senha
- Testes de unidade e integração
- Documentação final do projeto

---

## Definição de "Pronto" (Definition of Done)

Um item é considerado concluído quando:

1. O código está implementado e commitado no repositório.
2. A funcionalidade está coberta por ao menos um teste.
3. O código foi revisado e não há erros óbvios.
4. A funcionalidade está acessível via interface ou API documentada.
5. O item foi movido para a coluna **Done** no GitHub Projects.
