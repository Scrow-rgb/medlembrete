# Requisitos do Sistema — MedLembrete

## 1. Descrição do Problema

Pacientes com tratamentos medicamentosos contínuos ou complexos frequentemente enfrentam dificuldades para lembrar horários, doses e durações corretas de cada medicamento. Essa falha na adesão ao tratamento pode resultar em piora do quadro clínico, hospitalizações e aumento dos custos em saúde.

O MedLembrete propõe uma solução web que centraliza o controle de medicamentos do usuário, oferecendo lembretes, histórico de administração e relatórios de adesão.

---

## 2. Requisitos Funcionais

Os requisitos funcionais estão organizados como histórias de usuário no formato: *Como [papel], quero [ação], para [benefício].*

| ID | História de Usuário | Prioridade |
|----|---------------------|------------|
| RF01 | Como usuário, quero me cadastrar no sistema informando nome, e-mail e senha, para ter acesso à minha conta. | Alta |
| RF02 | Como usuário, quero fazer login com e-mail e senha, para acessar meus dados de forma segura. | Alta |
| RF03 | Como usuário, quero cadastrar um medicamento informando nome, dose, unidade e observações, para registrá-lo no sistema. | Alta |
| RF04 | Como usuário, quero definir horários de administração para cada medicamento (ex.: 08h, 14h, 20h), para organizar minha rotina de tratamento. | Alta |
| RF05 | Como usuário, quero informar a data de início e fim do tratamento para cada medicamento, para controlar a duração correta do uso. | Alta |
| RF06 | Como usuário, quero visualizar a lista de todos os meus medicamentos ativos, para ter uma visão geral do meu tratamento. | Alta |
| RF07 | Como usuário, quero registrar que tomei um medicamento em um horário específico, para manter o histórico de administração atualizado. | Alta |
| RF08 | Como usuário, quero visualizar o histórico de administração de cada medicamento, para acompanhar minha adesão ao tratamento. | Média |
| RF09 | Como usuário, quero ver um painel com os medicamentos que devo tomar hoje e em quais horários, para me organizar durante o dia. | Alta |
| RF10 | Como usuário, quero editar as informações de um medicamento cadastrado, para corrigir dados ou ajustar o tratamento. | Média |
| RF11 | Como usuário, quero desativar ou excluir um medicamento quando o tratamento for encerrado, para manter minha lista organizada. | Média |
| RF12 | Como usuário, quero visualizar um relatório de adesão semanal (percentual de doses tomadas vs. previstas), para avaliar meu cumprimento do tratamento. | Média |
| RF13 | Como usuário, quero redefinir minha senha via e-mail, para recuperar o acesso em caso de esquecimento. | Baixa |

---

## 3. Requisitos Não Funcionais

| ID | Requisito | Categoria |
|----|-----------|-----------|
| RNF01 | O sistema deve responder às requisições em menos de 2 segundos em condições normais de uso. | Desempenho |
| RNF02 | As senhas dos usuários devem ser armazenadas com hash (bcrypt), nunca em texto puro. | Segurança |
| RNF03 | A autenticação deve utilizar tokens JWT com expiração de 24 horas. | Segurança |
| RNF04 | O sistema deve ser responsivo, funcionando adequadamente em navegadores desktop e mobile. | Usabilidade |
| RNF05 | O front-end deve ser compatível com os navegadores Chrome, Firefox e Edge nas versões mais recentes. | Portabilidade |
| RNF06 | O código-fonte deve ser versionado no GitHub com commits organizados por funcionalidade. | Manutenibilidade |
| RNF07 | A API back-end deve seguir os princípios REST, com endpoints bem definidos e retornos em JSON. | Arquitetura |
| RNF08 | O banco de dados deve utilizar PostgreSQL, com esquema normalizado. | Arquitetura |
| RNF09 | O sistema deve validar os dados de entrada no back-end, retornando mensagens de erro claras ao front-end. | Confiabilidade |
| RNF10 | O sistema deve estar disponível pelo menos 95% do tempo durante o período de avaliação. | Disponibilidade |

---

## 4. Restrições

- A solução deve ser um sistema web com front-end e back-end distintos.
- Não será desenvolvido um aplicativo nativo (iOS/Android).
- O envio de notificações push está fora do escopo deste trabalho; os lembretes serão visíveis apenas ao acessar o sistema.

---

## 5. Backlog do Produto (resumo)

Os itens abaixo correspondem às histórias de usuário acima, organizadas por sprint prevista:

**Sprint 1 (TP2):** RF01, RF02, RF03, RF04, RF05, RF06  
**Sprint 2 (TP3):** RF07, RF08, RF09, RF10  
**Sprint 3 (TP4):** RF11, RF12, RF13  
