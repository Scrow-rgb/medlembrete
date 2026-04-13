# MedLembrete 💊

> Sistema web de gerenciamento de medicamentos para apoio à adesão ao tratamento.

## ODS Abordado

**ODS 3 – Saúde e Bem-estar**

A não adesão ao tratamento medicamentoso é um dos principais problemas de saúde pública no Brasil e no mundo. Pacientes com doenças crônicas, idosos e pessoas com múltiplos medicamentos frequentemente se esquecem de tomar doses ou confundem horários, comprometendo a eficácia do tratamento. O MedLembrete busca mitigar esse problema por meio de uma solução digital acessível.

## Sobre o Projeto

O MedLembrete é um sistema web com front-end e back-end que permite ao usuário cadastrar seus medicamentos, definir horários e doses, acompanhar o histórico de administração e receber lembretes. A solução é voltada especialmente para pacientes com tratamentos contínuos ou complexos.

## Tipo de Solução

**Sistema web (front-end + back-end)**

A escolha se justifica pela necessidade de persistência de dados entre sessões, autenticação de usuários, lógica de negócio no servidor (cálculo de próximas doses, verificação de adesão) e possibilidade de acesso multiplataforma via navegador, sem necessidade de instalação.

## Estrutura do Repositório

```
medlembrete/
├── README.md
├── docs/
│   ├── requisitos.md
│   ├── casos-de-uso.md
│   └── diagramas/
│       └── caso-de-uso.png
├── src/
│   ├── frontend/
│   └── backend/
└── .github/
```

## Documentação

- [Requisitos Funcionais e Não Funcionais](docs/requisitos.md)
- [Diagrama e Descrição de Casos de Uso](docs/casos-de-uso.md)

## Planejamento

O planejamento das sprints é gerenciado via [GitHub Projects](../../projects).

## Tecnologias Previstas

| Camada | Tecnologia |
|--------|-----------|
| Front-end | React |
| Back-end | Node.js + Express |
| Banco de dados | PostgreSQL |
| Autenticação | JWT |

## Autor

Trabalho desenvolvido para a disciplina de Engenharia de Requisitos.
# medlembrete
