# 📂 Projeto: Sistema de Chamados Internos (Scrum)

Este documento descreve o fluxo de trabalho, critérios de aceitação e processos de homologação utilizados no gerenciamento de um sistema de chamados internos, seguindo metodologia Scrum.

---

## ✅ Critérios de Aceitação (Definição de Pronto - DoD)

Cada tarefa/história será considerada **aceita** somente quando:

- [ ] Funcionalidade implementada conforme a descrição da história.
- [ ] Cobertura mínima de testes automatizados (unitários e/ou integração).
- [ ] Sem erros críticos ou bloqueadores nos testes manuais.
- [ ] Código revisado por outro desenvolvedor (Code Review).
- [ ] Homologação concluída com sucesso pela equipe de QA.
- [ ] Feedback do cliente/PO recebido e item marcado como “Done”.

---

## 🔁 Fluxo de Trabalho (Workflow Scrum)

| Etapa             | Responsável | Descrição                                                                 |
|-------------------|-------------|---------------------------------------------------------------------------|
| **Backlog**       | PO          | Histórias priorizadas e prontas para planejamento.                        |
| **To Do**         | DEV         | Selecionadas para a sprint atual.                                         |
| **In Progress**   | DEV         | Em desenvolvimento.                                                       |
| **Code Review**   | DEV         | PR criado e aguardando aprovação.                                         |
| **Ready for QA**  | DEV         | Build/teste finalizado, aguardando QA.                                    |
| **In QA**         | QA          | Em teste funcional.                                                       |
| **Reopened**      | QA/DEV      | Falha detectada; tarefa retorna ao DEV.                                   |
| **Done**          | QA/PO       | QA aprova e cliente valida.                                               |

---

## 🧪 Fluxo de Aceitação

```text
DEV IMPLEMENTA → ENVIA PARA QA → QA VALIDA → CLIENTE/PO ACEITA
```

### 1. DEV
- Implementa com base nos critérios da história.
- Executa testes locais e automatizados.
- Cria PR e envia para revisão.
- Após aprovação, move para `Ready for QA`.

### 2. QA
- Executa testes manuais e/ou automatizados.
- Se falhar, retorna como `Reopened`.
- Se passar, move para `Done`.

### 3. CLIENTE/PO
- Valida em Sprint Review ou ambiente de homologação.
- Se aprovado, considera a entrega finalizada.
- Se houver ajustes, nova história é criada.

---

## 📌 Exemplo de Critérios de Aceitação

> **User Story**: Como usuário, quero abrir um chamado para suporte técnico.

**Critérios de Aceitação:**
- [ ] Formulário com campos: título, descrição, prioridade, categoria.
- [ ] Validação de todos os campos obrigatórios.
- [ ] Chamado entra com status inicial “Aberto”.
- [ ] Mensagem de sucesso ao finalizar envio.
- [ ] Registro com data e ID únicos.
- [ ] Prioridade impacta ordenação da lista.
- [ ] QA pode testar em ambiente de staging.
- [ ] Cliente consegue visualizar em “Meus Chamados”.

---

## 📊 Diagrama de Estado (Workflow)

```
Backlog
   ↓
 To Do
   ↓
In Progress
   ↓
Code Review
   ↓
Ready for QA
   ↓
  In QA
   ↓     ↘
 Done   Reopened
           ↓
     In Progress
```

---

## 📁 Organização no Jira

- Projeto: `Sistema de Chamados Internos`
- Tipo de Projeto: Scrum
- Sprint: 2 semanas
- Tipos de Issue:
  - Story
  - Bug
  - Task
  - Sub-task
- Boards separados para DEV e QA (ou swimlanes por equipe)
- Permissões separadas por time
- Automatizações: mover status com base em PR, testes, etc.

---

## 🔚 Observações Finais

Este fluxo visa garantir qualidade contínua, entrega ágil e validação eficiente tanto técnica quanto do ponto de vista do usuário final.
