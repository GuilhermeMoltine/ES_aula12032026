### UC01 — Realizar Login

### Ator Principal
Usuário

### Objetivo
Permitir que o usuário acesse o sistema.

### Pré-condições
- Usuário deve possuir cadastro ativo.

### Pós-condições
- Sessão iniciada com sucesso.

### Fluxo Principal
1. O usuário informa e-mail e senha.
2. O sistema valida as credenciais.
3. O sistema autentica o usuário e redireciona para a tela inicial.

### Fluxos Alternativos
A1 — Senha incorreta:
O sistema exibe mensagem de erro.

A2 — Conta bloqueada:
O sistema impede o login e instrui o usuário a recuperar o acesso.

### RF Relacionados
-RF01

### RNF Relacionados
-RNF02, RNF04

### RN Relacionadas
-RN06

-------------------------------------------------------------------------------------------------

### UC02 — Cadastrar Aluno

### Ator Principal
Recepcionista

### Objetivo
Registrar um novo aluno no sistema, coletando suas informações pessoais e de plano.

### Pré-condições
-Recepcionista logado no sistema.

### Pós-condições
-Aluno cadastrado com sucesso.
-Plano associado ao aluno.

### Fluxo Principal
1. A recepcionista acessa a tela de cadastro de alunos.
2. A recepcionista preenche os dados pessoais do aluno (nome, CPF, contato, endereço).
3. A recepcionista seleciona o plano desejado para o aluno.
4. O sistema valida os dados e o plano.
5. O sistema registra o novo aluno.

### Fluxos Alternativos
A1 — Dados incompletos:
O sistema exibe mensagem de erro e solicita o preenchimento de todos os campos obrigatórios.

A2 — CPF já cadastrado:
O sistema informa que o CPF já existe e impede o cadastro.

### RF Relacionados
RF01

### RNF Relacionados
RNF02, RNF04

### RN Relacionadas
RN06

-------------------------------------------------------------------------------------------------

### UC03 — Gerenciar Planos (Criar/Editar/Ativar/Desativar)

### Ator Principal
Gerente

### Objetivo
Permitir ao gerente administrar os tipos de planos oferecidos pela academia.

### Pré-condições
-Gerente logado no sistema.

### Pós-condições
Plano criado, editado, ativado ou desativado com sucesso.

### Fluxo Principal
1. O gerente acessa a tela de gerenciamento de planos.
2. O gerente seleciona a opção desejada (criar novo plano, editar plano existente, ativar/desativar plano).
3. Para criar/editar: o gerente informa/modifica os detalhes do plano (nome, descrição, valor, modalidade).
4. O sistema valida as informações.
5. O sistema atualiza o status do plano ou cria um novo.

### Fluxos Alternativos
A1 — Dados inválidos:
O sistema exibe mensagem de erro e solicita correção.

A2 — Plano em uso:
Se tentar desativar um plano com alunos ativos, o sistema avisa e pede confirmação ou sugere migração de alunos.

### RF Relacionados
RF02

### RNF Relacionados
RNF02, RNF04

### RN Relacionadas
RN06

-------------------------------------------------------------------------------------------------

### UC04 — Registrar Pagamento (Recepção)

### Ator Principal
Recepcionista

### Objetivo
Registrar um pagamento de mensalidade realizado presencialmente.

### Pré-condições
-Recepcionista logado no sistema.
-Aluno identificado.

### Pós-condições
-Pagamento registrado com sucesso.
-Status de regularidade do aluno atualizado.

### Fluxo Principal
1. A recepcionista busca o aluno no sistema.
2. A recepcionista seleciona a opção de registrar pagamento.
3. A recepcionista informa o valor pago e o método de pagamento (dinheiro, cartão, PIX).
4. O sistema valida o valor e o método.
5. O sistema registra o pagamento e atualiza a regularidade do aluno.

### Fluxos Alternativos
A1 — Valor incorreto:
O sistema avisa que o valor não corresponde ao total da mensalidade e impede o registro (RN04).

A2 — Aluno não encontrado:
O sistema exibe mensagem de erro.

### RF Relacionados
RF03

### RNF Relacionados
RNF02, RNF04

### RN Relacionadas
RN04, RN07




### UC05 — Gerar Boleto/Cartão (Pagamento Online)

### Ator Principal
Aluno

### Objetivo
Permitir ao aluno gerar opções de pagamento online para sua mensalidade.

### Pré-condições
-Aluno logado no sistema.
-Mensalidade pendente.

### Pós-condições
-Boleto gerado ou link para pagamento com cartão disponibilizado.

### Fluxo Principal
1. O aluno acessa a área de pagamentos.
2. O sistema exibe a mensalidade pendente.
3. O aluno seleciona a opção de gerar boleto ou pagar com cartão.
4. O sistema gera o boleto (PDF) ou redireciona para a plataforma de pagamento com cartão.

### Fluxos Alternativos
A1 — Nenhuma mensalidade pendente:
O sistema informa que não há mensalidades a serem pagas.

### RF Relacionados
RF03

### RNF Relacionados
RNF02, RNF04

### RN Relacionadas
Nenhuma




### UC06 — Verificar Regularidade do Aluno

### Ator Principal
Sistema (Automático)

### Objetivo
Verificar se a mensalidade do aluno está em dia para permitir o acesso à academia.

### Pré-condições
-Aluno tenta acessar a catraca.

### Pós-condições
-Status de regularidade do aluno verificado.
-Acesso liberado ou bloqueado.

### Fluxo Principal
1. O aluno apresenta o RFID na catraca.
2. O sistema da catraca envia a identificação do aluno para o sistema FitPass.
3. O sistema FitPass consulta a regularidade do aluno.
4. Se o aluno estiver regular, o sistema envia comando para liberar a catraca.
5. Se o aluno estiver irregular, o sistema envia comando para bloquear a catraca.

### Fluxos Alternativos
A1 — Aluno inadimplente:
O sistema bloqueia a catraca e exibe mensagem de "Acesso Negado" (RN01).

A2 — RFID inválido:
O sistema informa que o RFID é inválido e bloqueia a catraca.

### RF Relacionados
-RF04, RF05

### RNF Relacionados
-RNF01, RNF03, RNF06

### RN Relacionadas
-RN01




### UC07 — Agendar Aula

Ator Principal

Aluno

Objetivo

Permitir ao aluno reservar uma vaga em uma aula disponível.

Pré-condições

•
Aluno logado no sistema.

•
Aluno regular.

Pós-condições

•
Vaga na aula reservada com sucesso.

•
Notificação de agendamento enviada.

Fluxo Principal

1.
O aluno acessa a área de agendamento de aulas.

2.
O sistema exibe as aulas disponíveis (horários, instrutores, vagas).

3.
O aluno seleciona a aula desejada.

4.
O sistema verifica a disponibilidade de vagas.

5.
O sistema reserva a vaga para o aluno.

6.
O sistema envia uma notificação de confirmação ao aluno.

Fluxos Alternativos

•
A1 — Vagas esgotadas:
O sistema informa que não há mais vagas para a aula selecionada (RN02).

•
A2 — Aluno irregular:
O sistema impede o agendamento e informa que o aluno está irregular.

RF Relacionados

•
RF06, RF10

RNF Relacionados

•
RNF01, RNF04

RN Relacionadas

•
RN02




UC08 — Cancelar Agendamento de Aula

Ator Principal

Aluno

Objetivo

Permitir ao aluno cancelar uma reserva de aula.

Pré-condições

•
Aluno logado no sistema.

•
Agendamento de aula existente.

Pós-condições

•
Agendamento cancelado.

•
Vaga liberada.

Fluxo Principal

1.
O aluno acessa a área de meus agendamentos.

2.
O sistema exibe os agendamentos futuros do aluno.

3.
O aluno seleciona o agendamento a ser cancelado.

4.
O sistema verifica se o cancelamento está dentro do prazo permitido (RN03).

5.
O sistema cancela o agendamento e libera a vaga.

Fluxos Alternativos

•
A1 — Prazo de cancelamento expirado:
O sistema informa que o cancelamento não é mais possível (RN03).

RF Relacionados

•
RF06

RNF Relacionados

•
RNF04

RN Relacionadas

•
RN03




UC09 — Registrar Presença em Aula

Ator Principal

Instrutor

Objetivo

Permitir ao instrutor registrar a presença dos alunos em uma aula.

Pré-condições

•
Instrutor logado no sistema.

•
Aula em andamento ou recém-finalizada.

Pós-condições

•
Presença dos alunos registrada.

Fluxo Principal

1.
O instrutor acessa a lista de suas aulas.

2.
O instrutor seleciona a aula desejada.

3.
O sistema exibe a lista de alunos agendados para a aula.

4.
O instrutor marca a presença de cada aluno.

5.
O sistema registra as presenças.

Fluxos Alternativos

•
A1 — Aluno não agendado:
O sistema avisa que o aluno não estava agendado para a aula, mas permite registrar presença como exceção (opcional).

RF Relacionados

•
RF07

RNF Relacionados

•
RNF04

RN Relacionadas

•
Nenhuma




UC10 — Registrar Avaliação Física

Ator Principal

Instrutor

Objetivo

Permitir ao instrutor registrar os dados de uma avaliação física de um aluno.

Pré-condições

•
Instrutor logado no sistema.

•
Aluno ativo e regular.

Pós-condições

•
Avaliação física registrada.

•
Notificação de avaliação física liberada enviada ao aluno.

Fluxo Principal

1.
O instrutor busca o aluno no sistema.

2.
O instrutor acessa a opção de registrar avaliação física.

3.
O sistema verifica a regularidade do aluno (RN05).

4.
O instrutor preenche os dados da avaliação (peso, IMC, percentual de gordura, medidas).

5.
O instrutor pode anexar arquivos (fotos, exames).

6.
O sistema registra a avaliação e envia notificação ao aluno.

Fluxos Alternativos

•
A1 — Aluno irregular:
O sistema impede o registro da avaliação e informa que o aluno está irregular (RN05).

•
A2 — Dados incompletos:
O sistema exibe mensagem de erro e solicita o preenchimento de campos obrigatórios.

RF Relacionados

•
RF08, RF10

RNF Relacionados

•
RNF02, RNF04

RN Relacionadas

•
RN05




UC11 — Visualizar Avaliação Física

Ator Principal

Aluno

Objetivo

Permitir ao aluno visualizar suas avaliações físicas registradas.

Pré-condições

•
Aluno logado no sistema.

•
Avaliação física registrada.

Pós-condições

•
Avaliação física exibida ao aluno.

Fluxo Principal

1.
O aluno acessa a área de avaliações físicas.

2.
O sistema exibe a lista de avaliações físicas realizadas.

3.
O aluno seleciona uma avaliação para visualizar os detalhes.

4.
O sistema exibe os dados da avaliação e os arquivos anexados.

Fluxos Alternativos

•
A1 — Nenhuma avaliação encontrada:
O sistema informa que não há avaliações físicas registradas para o aluno.

RF Relacionados

•
RF08

RNF Relacionados

•
RNF04

RN Relacionadas

•
Nenhuma




UC12 — Emitir Relatório de Inadimplência

Ator Principal

Gerente

Objetivo

Gerar um relatório de alunos com mensalidades em atraso.

Pré-condições

•
Gerente logado no sistema.

Pós-condições

•
Relatório de inadimplência gerado e exibido.

Fluxo Principal

1.
O gerente acessa a área de relatórios.

2.
O gerente seleciona a opção "Relatório de Inadimplência".

3.
O sistema processa os dados e gera o relatório.

4.
O relatório é exibido na tela, com opção de exportação.

Fluxos Alternativos

•
A1 — Nenhum aluno inadimplente:
O sistema informa que não há alunos inadimplentes no período.

RF Relacionados

•
RF09

RNF Relacionados

•
RNF01, RNF03, RNF04

RN Relacionadas

•
RN06




UC13 — Emitir Relatório de Alunos Ativos

Ator Principal

Gerente

Objetivo

Gerar um relatório com a lista de todos os alunos ativos na academia.

Pré-condições

•
Gerente logado no sistema.

Pós-condições

•
Relatório de alunos ativos gerado e exibido.

Fluxo Principal

1.
O gerente acessa a área de relatórios.

2.
O gerente seleciona a opção "Relatório de Alunos Ativos".

3.
O sistema processa os dados e gera o relatório.

4.
O relatório é exibido na tela, com opção de exportação.

Fluxos Alternativos

•
A1 — Nenhum aluno ativo:
O sistema informa que não há alunos ativos registrados.

RF Relacionados

•
RF09

RNF Relacionados

•
RNF01, RNF03, RNF04

RN Relacionadas

•
RN06




UC14 — Emitir Histórico de Acessos

Ator Principal

Gerente

Objetivo

Gerar um relatório com o histórico de acessos dos alunos à academia.

Pré-condições

•
Gerente logado no sistema.

Pós-condições

•
Relatório de histórico de acessos gerado e exibido.

Fluxo Principal

1.
O gerente acessa a área de relatórios.

2.
O gerente seleciona a opção "Histórico de Acessos".

3.
O gerente pode filtrar por aluno ou período.

4.
O sistema processa os dados e gera o relatório.

5.
O relatório é exibido na tela, com opção de exportação.

Fluxos Alternativos

•
A1 — Nenhum acesso encontrado:
O sistema informa que não há registros de acesso para os filtros aplicados.

RF Relacionados

•
RF09

RNF Relacionados

•
RNF01, RNF03, RNF04

RN Relacionadas

•
RN06




UC15 — Emitir Relatório de Ocupação de Aulas

Ator Principal

Gerente

Objetivo

Gerar um relatório sobre a ocupação das aulas oferecidas.

Pré-condições

•
Gerente logado no sistema.

Pós-condições

•
Relatório de ocupação de aulas gerado e exibido.

Fluxo Principal

1.
O gerente acessa a área de relatórios.

2.
O gerente seleciona a opção "Ocupação de Aulas".

3.
O gerente pode filtrar por aula ou período.

4.
O sistema processa os dados e gera o relatório.

5.
O relatório é exibido na tela, com opção de exportação.

Fluxos Alternativos

•
A1 — Nenhuma aula encontrada:
O sistema informa que não há aulas registradas para os filtros aplicados.

RF Relacionados

•
RF09

RNF Relacionados

•
RNF01, RNF03, RNF04

RN Relacionadas

•
RN06




UC16 — Receber Notificação de Vencimento de Mensalidade

Ator Principal

Sistema (Automático), Aluno

Objetivo

Informar o aluno sobre o vencimento iminente de sua mensalidade.

Pré-condições

•
Mensalidade do aluno próxima do vencimento.

Pós-condições

•
Notificação de vencimento enviada ao aluno.

Fluxo Principal

1.
O sistema verifica diariamente as mensalidades próximas do vencimento.

2.
Para cada mensalidade próxima do vencimento, o sistema gera uma notificação.

3.
O sistema envia a notificação ao aluno (e-mail, SMS, notificação no aplicativo).

Fluxos Alternativos

•
A1 — Aluno já pagou:
O sistema verifica se o pagamento já foi efetuado antes de enviar a notificação.

RF Relacionados

•
RF10

RNF Relacionados

•
RNF01

RN Relacionadas

•
Nenhuma




UC17 — Receber Notificação de Confirmação de Agendamento

Ator Principal

Sistema (Automático), Aluno

Objetivo

Confirmar ao aluno que seu agendamento de aula foi realizado com sucesso.

Pré-condições

•
Aluno agendou uma aula.

Pós-condições

•
Notificação de confirmação de agendamento enviada ao aluno.

Fluxo Principal

1.
Após o aluno agendar uma aula, o sistema gera uma notificação de confirmação.

2.
O sistema envia a notificação ao aluno (e-mail, SMS, notificação no aplicativo).

Fluxos Alternativos

•
Nenhum

RF Relacionados

•
RF10

RNF Relacionados

•
RNF01

RN Relacionadas

•
Nenhuma




UC18 — Receber Notificação de Liberação de Avaliação Física

Ator Principal

Sistema (Automático), Aluno

Objetivo

Informar o aluno que uma nova avaliação física foi registrada e está disponível para visualização.

Pré-condições

•
Instrutor registrou uma avaliação física para o aluno.

Pós-condições

•
Notificação de avaliação física liberada enviada ao aluno.

Fluxo Principal

1.
Após o instrutor registrar uma avaliação física, o sistema gera uma notificação.

2.
O sistema envia a notificação ao aluno (e-mail, SMS, notificação no aplicativo).

Fluxos Alternativos

•
Nenhum

RF Relacionados

•
RF10

RNF Relacionados

•
RNF01

RN Relacionadas

•
Nenhuma




UC19 — Bloquear Acesso por Inadimplência

Ator Principal

Sistema (Automático)

Objetivo

Impedir o acesso de alunos inadimplentes à academia através da catraca.

Pré-condições

•
Aluno com mensalidade vencida há mais de 5 dias.

•
Aluno tenta acessar a catraca.

Pós-condições

•
Acesso do aluno bloqueado na catraca.

Fluxo Principal

1.
O aluno apresenta o RFID na catraca.

2.
O sistema da catraca envia a identificação do aluno para o sistema FitPass.

3.
O sistema FitPass consulta a regularidade do aluno.

4.
Se o aluno estiver inadimplente (RN01), o sistema envia comando para bloquear a catraca.

5.
A catraca exibe mensagem de "Acesso Negado".

Fluxos Alternativos

•
A1 — Aluno regulariza pagamento:
Após a regularização (UC04), o sistema atualiza a regularidade (RN07) e o acesso é liberado.

RF Relacionados

•
RF05

RNF Relacionados

•
RNF01, RNF03, RNF06

RN Relacionadas

•
RN01




### UC20 — Atualizar Regularidade do Aluno (Automático)

### Ator Principal
Sistema (Automático)

### Objetivo
Manter o status de regularidade do aluno sempre atualizado após um pagamento.

### Pré-condições
-Pagamento de mensalidade registrado (UC04 ou UC05).

### Pós-condições
-Status de regularidade do aluno atualizado para "Regular".

### Fluxo Principal
1. Após o registro de um pagamento de mensalidade, o sistema é acionado.
2. O sistema consulta o histórico de pagamentos do aluno.
3. O sistema verifica se todas as mensalidades estão em dia.
4. O sistema atualiza o status de regularidade do aluno para "Regular".

### Fluxos Alternativos
-Nenhum

### RF Relacionados
-RF04

### RNF Relacionados
-RNF01, RNF03

### RN Relacionadas
-RN07






