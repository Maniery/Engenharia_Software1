# Lista de User Stories

Documento adaptado do **Modelo BSI - Doc 004 - Lista de User Stories** e estruturado conforme o processo easYProcess (YP).

## Histórico de revisões

| Data       | Versão  | Descrição                                     | Autor  |
| :--------- | :-----: | :-------------------------------------------: | :----: |
| 2025-09-17 | 0.0.1   | Criação do documento com User Stories         | Laety  |

---

### User Story US01 - Gerenciar Usuários

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador**, quero **cadastrar, editar, listar e remover usuários**, para que apenas contas válidas tenham acesso ao sistema e possamos gerir permissões. Um usuário possui: id, nome, email (login), tipo de usuário, data de nascimento, status, password e avatarURL. |
| **Requisitos envolvidos** | RF01, RF03 (se aplicável para visualizar local do usuário) |
| **Prioridade**            | Essencial                           |
| **Estimativa**            | 8 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 7 PF                                |
| **Analista**              | Pedro                             |
| **Desenvolvedor**         | Laety                             |
| **Revisor**               | Sueliton                          |
| **Testador**              | Felipe                            |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA01.01** | Cadastrar usuário com todos os campos válidos resulta em sucesso e usuário aparece na listagem. |
| **TA01.02** | Tentativa de cadastrar com e-mail já existente retorna erro e não cria conta. |
| **TA01.03** | Editar dados do usuário atualiza as informações exibidas. |
| **TA01.04** | Remover usuário faz com que não consiga mais autenticar com esse e-mail. |

---

### User Story US02 - Autenticar Usuários

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Usuário**, quero **logar no sistema usando e-mail e senha**, para acessar as funcionalidades permitidas ao meu tipo de usuário. O sistema deve validar credenciais, bloquear após tentativas excessivas e permitir recuperação de senha. |
| **Requisitos envolvidos** | RF02 |
| **Prioridade**            | Essencial                           |
| **Estimativa**            | 4 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 2 PF                                |
| **Analista**              | Laety                               |
| **Desenvolvedor**         | Felipe                              |
| **Revisor**               | Pedro                               |
| **Testador**              | Sueliton                            |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA02.01** | Login com credenciais válidas autentica o usuário. |
| **TA02.02** | Login com senha incorreta incrementa contador de tentativas e retorna mensagem adequada. |
| **TA02.03** | Recuperação de senha envia e-mail (simulado) com token de recuperação. |
| **TA02.04** | Após N tentativas falhas (configurável) conta é temporariamente bloqueada. |

---

### User Story US03 - Gerenciar Locais

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador**, quero **cadastrar, editar, listar e excluir locais** (prédios/anexos) para que chaves e setores sejam corretamente vinculados a locais físicos. |
| **Requisitos envolvidos** | RF03 |
| **Prioridade**            | Importante                           |
| **Estimativa**            | 6 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 2 PF                                |
| **Analista**              | Sueliton                            |
| **Desenvolvedor**         | Pedro                                |
| **Revisor**               | Felipe                               |
| **Testador**              | Laety                                |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA03.01** | Cadastrar local com dados obrigatórios aparece na lista. |
| **TA03.02** | Editar local altera dados mostrados em listagem e detalhes. |
| **TA03.03** | Excluir local remove vínculo com setores (ou impede se houver setores vinculados, conforme regra). |

---

### User Story US04 - Gerenciar Setores

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador**, quero **cadastrar, editar, listar e excluir setores** vinculados a locais, para organizar chaves por setores e facilitar busca/atribuição. |
| **Requisitos envolvidos** | RF04 |
| **Prioridade**            | Importante                           |
| **Estimativa**            | 6 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 2 PF                                |
| **Analista**              | Felipe                               |
| **Desenvolvedor**         | Laety                                |
| **Revisor**               | Pedro                                |
| **Testador**              | Sueliton                             |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA04.01** | Criar setor associado a um local e exibir na lista de setores. |
| **TA04.02** | Alterar nome ou local do setor persiste e reflete na UI. |
| **TA04.03** | Excluir setor só é permitido se não houver chaves vinculadas (ou então avisar e bloquear). |

---

### User Story US05 - Gerenciar Chaves

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador**, quero **cadastrar, editar, listar e excluir chaves**, definir seu setor e status (Disponível / Emprestada), para controlar o inventário físico de chaves. Cada chave tem id, descrição, localização, setor e status. |
| **Requisitos envolvidos** | RF05 |
| **Prioridade**            | Essencial                           |
| **Estimativa**            | 8 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 3 PF                                |
| **Analista**              | Pedro                                |
| **Desenvolvedor**         | Sueliton                             |
| **Revisor**               | Laety                                |
| **Testador**              | Felipe                               |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA05.01** | Cadastrar chave com setor vinculado aparece na listagem com status Disponível. |
| **TA05.02** | Alterar dados da chave (descrição/localização) atualiza registro. |
| **TA05.03** | Excluir chave só é permitido se não estiver emprestada. |
| **TA05.04** | Alterar status para Emprestada impede novo empréstimo até devolução. |

---

### User Story US06 - Registrar Empréstimo de Chave

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Porteiro (Operador)**, quero **registrar o empréstimo de uma chave para um usuário/funcionário**, informando data/hora e responsável, para que o sistema atualize o status da chave e gere um registro de movimentação. Deve incluir autenticação do operador (CU01 include). |
| **Requisitos envolvidos** | RF06, RF02 (autenticação do operador) |
| **Prioridade**            | Essencial                           |
| **Estimativa**            | 6 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 3 PF                                |
| **Analista**              | Laety                                |
| **Desenvolvedor**         | Pedro                                |
| **Revisor**               | Felipe                               |
| **Testador**              | Sueliton                             |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA06.01** | Ao registrar empréstimo com chave Disponível, o sistema cria Movimentação e marca chave como Emprestada. |
| **TA06.02** | Tentativa de empréstimo de chave Emprestada é rejeitada com mensagem explicativa. |
| **TA06.03** | Registro inclui usuário responsável, operador, data/hora corretos. |
| **TA06.04** | Operador precisa estar autenticado para registrar empréstimo. |

---

### User Story US07 - Registrar Devolução de Chave

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Porteiro (Operador)**, quero **registrar a devolução de uma chave emprestada**, atualizando o registro de movimentação e marcando a chave como Disponível; possibilitar observações sobre estado físico. |
| **Requisitos envolvidos** | RF07, RF02 (autenticação do operador) |
| **Prioridade**            | Essencial                           |
| **Estimativa**            | 6 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 3 PF                                |
| **Analista**              | Sueliton                             |
| **Desenvolvedor**         | Laety                                |
| **Revisor**               | Pedro                                |
| **Testador**              | Felipe                               |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA07.01** | Registrar devolução atualiza Movimentação (data/hora de devolução) e status da chave para Disponível. |
| **TA07.02** | Se houver dano, operador pode registrar observação no registro de vistoria/movimentação. |
| **TA07.03** | Operador precisa estar autenticado para registrar devolução. |

---

### User Story US08 - Consultar Histórico de Movimentações e Chaves Emprestadas

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador ou Porteiro**, quero **consultar o histórico de empréstimos e devoluções** e **listar chaves atualmente emprestadas**, com filtros por usuário, chave, data e setor, para auditoria e acompanhamento. |
| **Requisitos envolvidos** | RF08, RF09 |
| **Prioridade**            | Importante / Desejável (consulta detalhada) |
| **Estimativa**            | 4 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 2 PF                                |
| **Analista**              | Felipe                               |
| **Desenvolvedor**         | Sueliton                             |
| **Revisor**               | Laety                                |
| **Testador**              | Pedro                                |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA08.01** | Filtrar histórico por intervalo de datas e retornar registros correspondentes. |
| **TA08.02** | Listar chaves emprestadas retorna apenas chaves com status Emprestada e mostra responsável. |
| **TA08.03** | Exportar resultado (CSV/PDF) disponível para auditoria (se requerido). |

---

### User Story US09 - Gerar Relatórios de Movimentações

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Administrador**, quero **gerar relatórios de movimentações** (período, por setor, por chave, por usuário) e exportá-los (CSV/PDF), para análise e tomada de decisão. |
| **Requisitos envolvidos** | RF10, RF08 (uso de dados históricos) |
| **Prioridade**            | Desejável / Importante                |
| **Estimativa**            | 8 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 3 PF                                |
| **Analista**              | Laety                                |
| **Desenvolvedor**         | Sueliton                             |
| **Revisor**               | Pedro                                |
| **Testador**              | Felipe                               |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA09.01** | Gerar relatório por período retorna dados corretos e completos. |
| **TA09.02** | Exportar relatório em CSV e PDF gera arquivo com layout mínimo aceitável. |
| **TA09.03** | Filtros (setor, chave, usuário) funcionam conjuntamente. |

---

### User Story US10 - Buscar Chaves

|               |                                                                |
| ------------- | :------------------------------------------------------------- |
| **Descrição** | Como **Porteiro/Administrador**, quero **buscar chaves por nome/descrição ou setor**, para localizar rapidamente uma chave e ver seu status e histórico. A busca deve aceitar termos parciais. |
| **Requisitos envolvidos** | RF11 |
| **Prioridade**            | Importante                           |
| **Estimativa**            | 3 h                                 |
| **Tempo Gasto (real):**   | -                                   |
| **Tamanho Funcional**     | 1 PF                                |
| **Analista**              | Sueliton                             |
| **Desenvolvedor**         | Pedro                                |
| **Revisor**               | Felipe                               |
| **Testador**              | Laety                                |

**Testes de Aceitação (TA)**

| Código    | Descrição |
|-----------|-----------|
| **TA10.01** | Buscar por termo exato retorna chave correspondente. |
| **TA10.02** | Busca parcial (substring) retorna todas as chaves que contenham o termo. |
| **TA10.03** | Resultado mostra status (Disponível/Emprestada) e link para histórico. |

---

## Notas gerais

- **Critérios de priorização**: `Essencial` = entrega mínima viável para operações críticas; `Importante` = melhora significativa; `Desejável` = Nice-to-have.  
- **Estimativas** são iniciais; ajuste durante sprints/refinement.  
- **Testes de Aceitação (TA)** devem ser automatizados quando possível (scripts de integração/selenium ou testes de API).  
- Caso queira, eu transformo este Markdown em:  
  - um arquivo `.md` pronto para commit,  
  - um arquivo Word/PDF,  
  - ou em issues no GitHub (1 issue por User Story).  
