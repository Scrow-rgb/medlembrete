# Casos de Uso — MedLembrete

## 1. Atores

| Ator | Descrição |
|------|-----------|
| **Usuário** | Pessoa cadastrada no sistema que gerencia seus próprios medicamentos. |
| **Sistema** | O próprio MedLembrete, responsável por processar regras de negócio e persistir dados. |

---

## 2. Diagrama de Casos de Uso

> O diagrama está disponível em `diagramas/caso-de-uso.png`.

```
+----------------------------------------------------------+
|                     <<sistema>>                          |
|                     MedLembrete                          |
|                                                          |
|   +----------------+     +---------------------------+  |
|   | UC01           |     | UC02                      |  |
|   | Cadastrar-se   |     | Fazer login               |  |
|   +----------------+     +---------------------------+  |
|                                                          |
|   +----------------+     +---------------------------+  |
|   | UC03           |     | UC04                      |  |
|   | Cadastrar      |     | Definir horários de       |  |
|   | medicamento    |     | administração             |  |
|   +----------------+     +---------------------------+  |
|                                                          |
|   +----------------+     +---------------------------+  |
|   | UC05           |     | UC06                      |  |
|   | Visualizar     |     | Registrar administração   |  |
|   | painel diário  |     | de dose                   |  |
|   +----------------+     +---------------------------+  |
|                                                          |
|   +----------------+     +---------------------------+  |
|   | UC07           |     | UC08                      |  |
|   | Visualizar     |     | Editar/desativar          |  |
|   | histórico      |     | medicamento               |  |
|   +----------------+     +---------------------------+  |
|                                                          |
|   +----------------+                                    |
|   | UC09           |                                    |
|   | Visualizar     |                                    |
|   | relatório de   |                                    |
|   | adesão         |                                    |
|   +----------------+                                    |
|                                                          |
+----------------------------------------------------------+
          |
     [Usuário]
```

---

## 3. Descrição dos Casos de Uso

---

### UC01 — Cadastrar-se

**Ator principal:** Usuário  
**Pré-condição:** O usuário não possui conta no sistema.  
**Pós-condição:** O usuário tem uma conta criada e pode fazer login.

**Fluxo principal:**
1. O usuário acessa a página de cadastro.
2. O usuário informa nome completo, e-mail e senha.
3. O sistema valida os dados (e-mail único, senha com mínimo de 8 caracteres).
4. O sistema cria a conta e redireciona o usuário para a tela de login.

**Fluxo alternativo — e-mail já cadastrado:**
- No passo 3, o sistema exibe mensagem informando que o e-mail já está em uso.

---

### UC02 — Fazer login

**Ator principal:** Usuário  
**Pré-condição:** O usuário possui cadastro no sistema.  
**Pós-condição:** O usuário está autenticado e acessa o painel principal.

**Fluxo principal:**
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema emite um token JWT e redireciona para o painel.

**Fluxo alternativo — credenciais inválidas:**
- No passo 2, o sistema exibe mensagem de erro sem especificar qual campo está incorreto.

---

### UC03 — Cadastrar medicamento

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado.  
**Pós-condição:** O medicamento é salvo e aparece na lista do usuário.

**Fluxo principal:**
1. O usuário acessa a opção "Novo medicamento".
2. O usuário preenche: nome do medicamento, dose (ex.: 500 mg), unidade, data de início, data de término (opcional) e observações.
3. O sistema valida os campos obrigatórios.
4. O sistema salva o medicamento e exibe confirmação.

**Fluxo alternativo — campos obrigatórios vazios:**
- No passo 3, o sistema destaca os campos faltantes e não prossegue.

---

### UC04 — Definir horários de administração

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e possui ao menos um medicamento cadastrado.  
**Pós-condição:** Os horários ficam associados ao medicamento.

**Fluxo principal:**
1. O usuário seleciona um medicamento da lista.
2. O usuário adiciona um ou mais horários do dia (ex.: 08:00, 20:00).
3. O sistema salva os horários vinculados ao medicamento.

---

### UC05 — Visualizar painel diário

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e possui medicamentos com horários definidos.  
**Pós-condição:** Nenhuma alteração de estado.

**Fluxo principal:**
1. O usuário acessa o painel principal.
2. O sistema exibe os medicamentos com horários previstos para o dia atual.
3. Para cada item, o sistema indica se a dose já foi registrada ou está pendente.

---

### UC06 — Registrar administração de dose

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e há medicamentos com horários definidos.  
**Pós-condição:** O registro de administração é salvo no histórico.

**Fluxo principal:**
1. No painel diário, o usuário clica em "Tomar" em um medicamento pendente.
2. O sistema registra o horário atual e o medicamento.
3. O item é marcado como "administrado" no painel.

**Fluxo alternativo — registrar dose atrasada:**
- O usuário pode informar um horário diferente do atual ao registrar.

---

### UC07 — Visualizar histórico

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e possui registros de administração.  
**Pós-condição:** Nenhuma alteração de estado.

**Fluxo principal:**
1. O usuário acessa a seção de histórico de um medicamento.
2. O sistema exibe a lista de administrações com data e horário.

---

### UC08 — Editar ou desativar medicamento

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e possui ao menos um medicamento cadastrado.  
**Pós-condição:** O medicamento é atualizado ou desativado na lista.

**Fluxo principal (editar):**
1. O usuário seleciona um medicamento e escolhe "Editar".
2. O usuário altera os campos desejados.
3. O sistema salva as alterações.

**Fluxo alternativo (desativar):**
1. O usuário escolhe "Desativar" ou "Excluir".
2. O sistema solicita confirmação.
3. O medicamento é removido da lista ativa (mantido no histórico).

---

### UC09 — Visualizar relatório de adesão

**Ator principal:** Usuário  
**Pré-condição:** O usuário está autenticado e possui histórico de administrações.  
**Pós-condição:** Nenhuma alteração de estado.

**Fluxo principal:**
1. O usuário acessa a seção "Relatório".
2. O sistema calcula o percentual de doses tomadas versus doses previstas nos últimos 7 dias.
3. O sistema exibe o resultado por medicamento e o total geral.
