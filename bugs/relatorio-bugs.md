# Relatório de Bugs — Módulo de Cursos

---

## BUG-01 · Cadastro permitido com todos os campos vazios

**Severidade:** Alta

**Descrição:**
O sistema permite o cadastro de um curso sem que nenhum campo seja preenchido, sem exibir nenhuma mensagem de erro ou validação.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Não preencher nenhum campo do formulário
3. Clicar no botão de cadastrar

**Resultado esperado:**
O sistema deve impedir o cadastro e exibir mensagens indicando os campos obrigatórios.

**Resultado obtido:**
O curso é cadastrado com sucesso mesmo sem nenhuma informação preenchida.

---

## BUG-02 · Cadastro permitido com apenas um campo preenchido

**Severidade:** Alta

**Descrição:**
O sistema aceita o cadastro de um curso mesmo quando apenas um dos campos é preenchido, ignorando a obrigatoriedade dos demais.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Preencher apenas um campo (ex: nome do curso)
3. Deixar os demais campos vazios
4. Clicar no botão de cadastrar

**Resultado esperado:**
O sistema deve invalidar o cadastro e indicar os campos obrigatórios restantes.

**Resultado obtido:**
O curso é cadastrado mesmo com a maioria dos campos vazios.

---

## BUG-03 · Informações de Instrutor e Endereço/Link EAD não são exibidas na listagem

**Severidade:** Média

**Descrição:**
Após o cadastro de um curso com todos os campos preenchidos, as informações de Instrutor e Endereço/Link EAD não aparecem na listagem de cursos.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Preencher todos os campos, incluindo Instrutor e Endereço/Link EAD
3. Cadastrar o curso
4. Verificar o curso na listagem

**Resultado esperado:**
Todos os dados cadastrados devem ser exibidos corretamente na listagem.

**Resultado obtido:**
Os campos de Instrutor e Endereço/Link EAD não são exibidos no card do curso na listagem.

---

## BUG-04 · Número de vagas negativo é aceito

**Severidade:** Alta

**Descrição:**
O sistema permite o cadastro de cursos com número de vagas negativo, sem nenhuma validação ou bloqueio.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir um valor negativo no campo de vagas (ex: -10)
3. Preencher os demais campos
4. Clicar em cadastrar

**Resultado esperado:**
O sistema deve impedir o cadastro e exibir mensagem solicitando um número positivo.

**Resultado obtido:**
O curso é cadastrado e exibido na listagem com o número de vagas negativo.

---

## BUG-05 · Exclusão de curso não funciona

**Severidade:** Alta

**Descrição:**
Ao tentar excluir um curso pela listagem, o sistema exibe uma notificação de sucesso, porém o curso continua aparecendo na listagem mesmo após atualizar a página.

**Passos para reproduzir:**
1. Acessar a listagem de cursos
2. Localizar um curso cadastrado
3. Clicar em "Excluir curso"
4. Confirmar a exclusão
5. Aguardar a notificação de sucesso
6. Atualizar a página

**Resultado esperado:**
O curso deve ser removido da listagem imediatamente e não deve reaparecer após atualização.

**Resultado obtido:**
O sistema exibe notificação de sucesso, mas o curso permanece na listagem após a atualização.

---

## BUG-06 · Cadastro de curso duplicado é permitido

**Severidade:** Média

**Descrição:**
O sistema permite cadastrar um curso com as mesmas informações de um curso já existente, sem nenhum aviso ou bloqueio.

**Passos para reproduzir:**
1. Cadastrar um curso com informações específicas
2. Acessar novamente o cadastro
3. Preencher os campos com as mesmas informações do curso já cadastrado
4. Clicar em cadastrar

**Resultado esperado:**
O sistema deve impedir o cadastro duplicado e informar que o curso já existe.

**Resultado obtido:**
O curso duplicado é cadastrado e exibido normalmente na listagem.

---

## BUG-07 · URL inválida é aceita no campo de imagem

**Severidade:** Média

**Descrição:**
O campo de URL da imagem de capa aceita qualquer texto, sem validar se é uma URL com formato válido ou se aponta para uma imagem.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir um valor inválido no campo de URL (ex: "abc")
3. Preencher os demais campos normalmente
4. Clicar em cadastrar

**Resultado esperado:**
O sistema deve validar o formato da URL antes de permitir o cadastro e exibir mensagem de erro caso inválida.

**Resultado obtido:**
O curso é cadastrado sem erro, porém nenhuma imagem é exibida no card.

---

## BUG-08 · Data de fim anterior à data de início é aceita

**Severidade:** Alta

**Descrição:**
O sistema permite cadastrar um curso com a data de término anterior à data de início, sem nenhuma validação de consistência entre os campos.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir uma data de início (ex: 01/06/2025)
3. Inserir uma data de fim anterior (ex: 01/01/2025)
4. Preencher os demais campos
5. Clicar em cadastrar

**Resultado esperado:**
O sistema deve impedir o cadastro e informar que a data de fim não pode ser anterior à data de início.

**Resultado obtido:**
O curso é cadastrado normalmente com datas inconsistentes.

---

## BUG-09 · Número de vagas com valor extremo quebra o layout

**Severidade:** Baixa

**Descrição:**
Ao inserir um número excessivamente grande no campo de vagas, o sistema aceita o valor e o card do curso na listagem fica deformado visualmente.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir um número muito grande no campo de vagas (ex: 10000000000000000000)
3. Preencher os demais campos
4. Clicar em cadastrar
5. Verificar o card do curso na listagem

**Resultado esperado:**
O sistema deve limitar o valor máximo permitido ou impedir valores excessivamente grandes.

**Resultado obtido:**
O curso é cadastrado e o card é exibido com layout deformado na listagem.

---

## BUG-10 · Número decimal é aceito no campo de vagas

**Severidade:** Média

**Descrição:**
O campo de número de vagas aceita valores decimais, que não fazem sentido para esse contexto, e os exibe na listagem sem validação.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir um valor decimal no campo de vagas (ex: 12.59)
3. Preencher os demais campos
4. Clicar em cadastrar

**Resultado esperado:**
O sistema deve invalidar o valor e exigir um número inteiro.

**Resultado obtido:**
O curso é cadastrado e exibido na listagem com o número decimal.

---

## BUG-11 · Datas inválidas ou absurdas são aceitas

**Severidade:** Média

**Descrição:**
O sistema aceita datas com anos completamente inválidos ou fora de qualquer contexto real, sem nenhuma validação de intervalo aceitável.

**Passos para reproduzir:**
1. Acessar a tela de cadastro de cursos
2. Inserir uma data com ano inválido nos campos de data (ex: ano 1011 ou 130111)
3. Preencher os demais campos
4. Clicar em cadastrar

**Resultado esperado:**
O sistema deve validar as datas inseridas e impedir valores fora de um intervalo aceitável.

**Resultado obtido:**
O curso é cadastrado e as datas absurdas são exibidas normalmente na listagem.
