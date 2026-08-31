# Documentação do Trabalho – Engenharia de Requisitos

## Equipe e Papéis

* [**Lucas Martins Barreto**](https://github.com/LucasBarretoDev-eng) – Documentação
* [**João Pedro Duarte Borges**](https://github.com/joaopedroduarteborges) – Analista de Requisitos
* [**Felipe Roosevelt**](https://github.com/fe-lip-pe) – Analista de Processos
* [**Lucas de Oliveira Andrade**](https://github.com/LucasOlvrAndrade) – Representante do Cliente
* [**Yuri Marques Oliveira**](https://github.com/yuriyz22) – Representante da Clínica
* [**Henrique Mota Monteiro**](https://github.com/Henriquemotaux) – Modelador

---

## 1. Análise do Negócio

### 1.1. Identificação do Processo

* **Nome do processo:** Processo de Atendimento e Agendamento de Consultas da Clínica Vida+ Saúde
* **Objetivo do processo:** Garantir que o paciente consiga solicitar, agendar e receber atendimento médico de forma organizada, confiável e sem retrabalho, evitando conflitos de horário e falhas de comunicação.
* **Cliente do processo:** O paciente, pois é quem solicita o serviço e recebe o valor final (a consulta realizada).
* **Quem executa as atividades:** Recepcionistas (cadastro, agendamento, confirmação, cancelamentos) e médicos (realização da consulta e registro do atendimento).
* **Quem gerencia o processo:** A direção/gerência da clínica, que acompanha o desempenho por meio de indicadores.
* **Evento que inicia o processo:** O paciente entra em contato (telefone, WhatsApp ou presencialmente) solicitando um agendamento.
* **Evento que encerra o processo:** O médico registra as informações do atendimento após a consulta ser realizada.
* **Valor entregue ao cliente:** Acesso rápido e confiável a uma consulta médica, com confirmação clara do horário, sem precisar repetir dados já cadastrados e com comunicação eficiente em caso de mudanças.

### 1.2. Identificação dos Stakeholders

| Stakeholder | Interesse no Processo | Participação | Necessidades |
| :--- | :--- | :--- | :--- |
| **Paciente** | Conseguir agendar e ser atendido de forma rápida, sem burocracia ou erros de agenda | Solicita o agendamento, fornece dados pessoais, comparece à consulta, pode cancelar/remarcar | Agendamento simples, confirmação confiável, lembretes automáticos, não precisar repetir dados a cada contato |
| **Recepcionista** | Realizar agendamentos sem conflitos e sem retrabalho manual | Atende solicitações, consulta a agenda, registra e confirma agendamentos, trata cancelamentos | Sistema centralizado, atualizado em tempo real, fácil e rápido de usar |
| **Médico** | Ter uma agenda organizada, sem conflitos de horário, e tempo adequado para cada atendimento | Define sua disponibilidade, realiza as consultas, registra informações do atendimento | Visibilidade da própria agenda e integração entre o agendamento e o prontuário do paciente |
| **Gerente** | Operação eficiente da clínica, sem gargalos no atendimento | Supervisiona a recepção e a organização das agendas | Dados confiáveis para tomar decisões operacionais no dia a dia |
| **Direção** | Melhorar o desempenho da clínica e reduzir faltas/cancelamentos | Define diretrizes e acompanha indicadores de desempenho | Dashboard com indicadores, redução de custos e retrabalho operacional |
| **Equipe de TI** | Sistema estável, sustentável e fácil de manter | Implementa e mantém o sistema de agendamento | Sistema estável, documentado e com arquitetura sustentável |

### 1.3. Análise do Processo Atual (AS-IS)

#### Quem?
* **Quem é o cliente?** O paciente que solicita e realiza consultas médicas na clínica.
* **Quem executa as atividades?** As principais atividades são feitas pelas recepcionistas (cadastro, consulta de agenda, agendamentos, confirmações de dados, cancelamentos e alterações). Os médicos participam na realização da consulta e no registro das informações do atendimento.
* **Quem gerencia?** A direção da clínica gerencia o processo de atendimento e acompanha seu desempenho por meio de indicadores.
* **Quem fornece informações?** Os pacientes fornecem dados pessoais e informações de agendamento. Os médicos fornecem disponibilidade e dados de atendimento. As recepcionistas registram e atualizam as informações dos agendamentos.
* **Quem participa das decisões?** A direção participa das decisões de funcionamento e melhoria. As recepcionistas tomam decisões operacionais cotidianas (verificação de horários, agendamentos e alterações).

#### O quê?
* **Quais são as entradas?**
  * Dados do paciente;
  * Solicitação de agendamento;
  * Especialidade desejada;
  * Disponibilidade dos médicos;
  * Informações de cancelamentos;
  * Alterações na agenda dos médicos.
* **Quais são as saídas?**
  * Consulta agendada;
  * Confirmação do agendamento;
  * Cancelamento ou alteração de consulta;
  * Atendimento realizado;
  * Registro das informações da consulta;
  * Indicadores de desempenho.
* **Quais são os recursos utilizados?**
  * Recepcionistas;
  * Médicos;
  * Pacientes;
  * Computadores;
  * Planilhas;
  * Sistema utilizado pelo médico;
  * Canais de comunicação (telefone e WhatsApp).
* **Quais ferramentas são utilizadas?**
  * Planilhas para controle das agendas;
  * WhatsApp;
  * Telefone;
  * Sistema separado utilizado pelos médicos para registrar os atendimentos.
* **Quais são os problemas?**
  * Falta de centralização das informações;
  * Conflitos de horários;
  * Informações que não são atualizadas imediatamente;
  * Necessidade de repetir dados cadastrais;
  * Divergência entre confirmações feitas pelo WhatsApp e registros da planilha;
  * Tratamento manual dos cancelamentos;
  * Ausência de lembretes automáticos;
  * Dificuldade para comunicar alterações na agenda;
  * Informações do atendimento armazenadas em um sistema separado.
* **Quais são os pontos positivos?**
  * O paciente possui diferentes canais para solicitar atendimento;
  * A clínica já possui um processo de agendamento definido;
  * Existe controle da agenda dos médicos;
  * Os médicos registram as informações após o atendimento;
  * A direção tem interesse em acompanhar indicadores de desempenho.
* **Quais indicadores poderiam ser utilizados?**
  * Quantidade de consultas realizadas;
  * Quantidade de cancelamentos;
  * Quantidade de faltas (*no-show*);
  * Tempo médio de atendimento;
  * Taxa de ocupação dos horários.

#### Quando?
* **Quando o processo começa?** Quando o paciente entra em contato com a clínica para solicitar um agendamento.
* **Quando as atividades são executadas?** Desde a solicitação do agendamento, passando pelo cadastro e confirmação, até a realização do atendimento. Atividades de cancelamento ou alteração ocorrem conforme as demandas surgem.
* **Quando o processo termina?** O processo completo termina após a realização da consulta e o registro das informações do atendimento médico.

#### Onde?
* **Onde o processo é iniciado?** Por telefone, WhatsApp ou presencialmente na recepção da clínica.
* **Onde as atividades são executadas?** Principalmente na recepção da clínica e no consultório médico.
* **Onde as informações são registradas?** Atualmente, os agendamentos são registrados em planilhas mantidas pelas recepcionistas. Os dados do atendimento médico são registrados em um sistema separado.

#### Por quê?
* **Por que o processo existe?** Para organizar o agendamento e a realização das consultas médicas, garantindo que os pacientes sejam atendidos nos horários disponíveis.
* **Qual valor ele entrega ao paciente?** Acesso ao agendamento, confirmação do horário e atendimento médico garantido.
* **Qual valor ele entrega para a clínica?** Organização das agendas dos médicos, controle dos atendimentos e suporte ao gerenciamento por indicadores de desempenho.

#### Como?
* **Como o processo é executado atualmente?** O paciente solicita agendamento por telefone, WhatsApp ou presencialmente. A recepcionista verifica a disponibilidade em uma planilha e registra o agendamento. No dia da consulta, a recepção confirma a chegada. Após o atendimento, o médico registra as informações em um sistema à parte.
* **Como as informações são registradas?** Em planilhas manuais (muitas vezes individuais por recepcionista) e em um sistema separado para o atendimento médico.
* **Como ocorre a comunicação com o paciente?** Via telefone, WhatsApp e presencialmente, sofrendo com divergências entre confirmações no WhatsApp e os registros na planilha.
* **Como são tratados os cancelamentos?** Manualmente pela recepcionista, que precisa buscar outro paciente na fila para preencher a vaga.
* **Como são tratadas as alterações de agenda?** A recepcionista realiza contato individual e manual com cada paciente afetado pela mudança na agenda do médico.

### 1.5. Regras de Negócio

| Código | Regra de Negócio | Origem |
| :--- | :--- | :--- |
| **RN01** | Um paciente deve possuir cadastro válido (com CPF) antes de realizar um agendamento. | Evitar cadastros anônimos e duplicidades de registros. |
| **RN02** | Um médico não pode possuir dois agendamentos no mesmo horário. | Eliminar conflitos de agendamento observados no processo atual. |
| **RN03** | Os agendamentos só podem ser efetuados em horários previamente disponibilizados na agenda do médico. | Garantir o cumprimento da grade de trabalho cadastrada pelo profissional. |
| **RN04** | O cancelamento de uma consulta deve liberar o horário imediatamente na agenda global. | Permitir reagendamentos rápidos e otimizar a taxa de ocupação da clínica. |
| **RN05** | Em caso de alteração na agenda do médico, o sistema deve bloquear o período alterado para novos agendamentos. | Prevenir novos conflitos de horários em momentos de imprevistos médicos. |
| **RN06** | Lembretes automáticos de consulta devem ser enviados ao paciente com 24 horas de antecedência. | Reduzir a taxa de não comparecimento (*no-show*) dos pacientes. |
| **RN07** | Apenas usuários com perfil “Médico” podem registrar ou alterar informações relativas ao atendimento/prontuário pós-consulta. | Garantir sigilo, ética e integridade nos dados de saúde dos pacientes. |
| **RN08** | Todo agendamento deve ter seu status atualizado automaticamente (Agendado, Confirmado, Em Atendimento, Concluído, Cancelado, Falta). | Prover a base de dados necessária para o cálculo de indicadores de desempenho. |
| **RN09** | Caso um paciente cancele com mais de 2 horas de antecedência, o sistema deve sugerir aos pacientes da lista de espera para preencher o horário. | Reduzir o tempo ocioso dos médicos e acelerar o atendimento da demanda reprimida. |
| **RN10** | Não deve ser permitida a exclusão física de cadastros de pacientes com histórico de consultas. | Manter a conformidade legal (LGPD e CFM) e preservar o histórico do paciente. |

---

## 2. Modelagem e Melhorias

### 2.1. Proposta de Melhorias

| Problema | Melhoria Proposta | Benefício Esperado |
| :--- | :--- | :--- |
| Cadastros duplicados e retrabalho no atendimento por uso de planilhas individuais. | Implantar cadastro único e centralizado com busca obrigatória por CPF antes do registro. | Eliminação de registros duplicados e agilidade na identificação do paciente. |
| Conflitos de horários na agenda do mesmo médico por concorrência entre recepcionistas. | Criar agenda médica centralizada em tempo real com bloqueio transacional de horários. | Fim dos agendamentos em duplo horário e total confiabilidade das agendas. |
| Ausência de mecanismo automático para lembrar pacientes, provocando altos índices de faltas. | Automatizar o envio de lembretes de consulta por WhatsApp e E-mail 24h antes da consulta. | Redução expressiva na taxa de faltas (*no-show*) e melhor aproveitamento da agenda. |
| Gerenciamento manual e demorado de reagendamentos quando ocorrem cancelamentos. | Implementar módulo automatizado de lista de espera com notificação para novos horários vagos. | Preenchimento rápido de lacunas de agenda e redução do tempo ocioso do médico. |
| Contato manual exaustivo da recepção com pacientes ao ocorrer alteração na agenda do médico. | Criar funcionalidade de remanejamento com notificação automática e instantânea aos pacientes afetados. | Redução da carga operacional da recepção e comunicação mais rápida e assertiva. |
| Inexistência de confirmação ativa de agendamentos pelo próprio paciente. | Disponibilizar confirmação bidirecional (link interativo no WhatsApp/E-mail) atualizando o status na hora. | Previsibilidade exata da presença dos pacientes no dia da consulta. |
| Desconexão entre o atendimento médico e a recepção, com prontuário em sistema separado. | Integrar o registro pós-consulta do médico à mesma plataforma centralizada. | Histórico clínico unificado, eliminação de retrabalho e integridade das informações. |
| Falta de visibilidade gerencial sobre desempenho, consultas realizadas, faltas e cancelamentos. | Desenvolver dashboard de indicadores gerenciais em tempo real para a gestão e direção da clínica. | Tomada de decisão baseada em dados e facilidade no acompanhamento de metas institucionais. |

### 2.2. Modelagem TO-BE

O processo futuro (**TO-BE**) da Clínica Vida+ Saúde foi projetado para integrar a recepção, a agenda dos médicos, a comunicação com o paciente e o registro do prontuário em uma plataforma única e centralizada, com informações atualizadas em tempo real.

O novo fluxo elimina o uso de planilhas individuais, automatiza o envio de lembretes e o gerenciamento da lista de espera, reduz os conflitos de horários por meio do bloqueio transacional e unifica as informações do atendimento médico à base de dados central da clínica.

#### 2.2.1. Raias de Responsabilidade do Processo

* **Paciente:** Realiza a solicitação de agendamento por WhatsApp, telefone ou presencialmente, responde às mensagens de confirmação, cancelamento ou remarcação e comparece à consulta.
* **Recepcionista:** Atende o paciente, realiza a busca pelo CPF, efetua o cadastro quando necessário, consulta horários disponíveis, registra os agendamentos, confirma a chegada do paciente no dia da consulta e trata situações excepcionais.
* **Sistema de Gestão Centralizado (Automações):** Controla a agenda global em tempo real, realiza o bloqueio transacional dos horários, envia lembretes automáticos via WhatsApp/E-mail com 24 horas de antecedência, gerencia a lista de espera, bloqueia horários afetados por alterações na agenda médica, envia notificações aos pacientes afetados e atualiza os status dos agendamentos e os indicadores do Dashboard Gerencial.
* **Médico:** Gerencia sua disponibilidade no sistema, visualiza os pacientes agendados e confirmados, realiza as consultas e registra as informações do atendimento diretamente no sistema.

#### 2.2.3. Mapeamento dos Pontos de Decisão Críticos

1. **O paciente possui cadastro?**
   * *Não:* A recepcionista realiza o cadastro único do paciente utilizando o CPF como identificador, conforme **RF01** e **RN01**.
   * *Sim:* O sistema recupera os dados cadastrais existentes por meio da busca por CPF, nome ou telefone, conforme **RF02**, evitando duplicidade e retrabalho.
2. **O horário está disponível?**
   * *Não:* O sistema oferece outras opções de horários ou permite a inclusão do paciente na Lista de Espera, conforme **RF05**, **RF10** e **RN09**.
   * *Sim:* O sistema realiza a reserva do horário com bloqueio transacional imediato, conforme **RNF06**, evitando que outro agendamento seja realizado simultaneamente para o mesmo horário.
3. **O agendamento foi confirmado pelo paciente?**
   * *Sim:* O sistema atualiza o status do agendamento para *Confirmado*, conforme **RN08**, mantendo o horário ocupado na agenda centralizada do médico.
   * *Não houve confirmação:* O agendamento permanece com o status correspondente até que o paciente confirme ou solicite o cancelamento/remarcação.
   * *Cancelamento solicitado:* O processo segue para o tratamento de cancelamento e liberação do horário.
4. **O paciente cancelou a consulta?**
   * *Sim:* O sistema altera o status para *Cancelado*, conforme **RN08**, libera imediatamente o horário na agenda global, conforme **RN04**, e consulta a Lista de Espera para oferecer o horário disponível a pacientes que estejam aguardando atendimento.
   * *Não:* O agendamento permanece ativo e segue para a etapa de realização da consulta.
5. **O médico alterou a agenda ou ocorreu algum imprevisto?**
   * *Sim:* O sistema bloqueia a grade afetada para novos agendamentos, conforme **RN05**, identifica os pacientes já agendados e envia notificações automáticas para que sejam informados e possam realizar o reagendamento, conforme **RF11**.
   * *Não:* O agendamento permanece normalmente até a data da consulta.
6. **O paciente compareceu no dia da consulta?**
   * *Sim:* A recepcionista confirma a chegada do paciente no sistema, alterando o status para *Em Atendimento*, conforme **RN08**, e o paciente é encaminhado ao médico.
   * *Não:* A recepcionista registra a ausência do paciente no sistema, alterando o status para *Falta*, conforme **RN08** e **RF13**. Essa informação será utilizada no cálculo dos indicadores de desempenho.

#### 2.2.4. Descrição Passo a Passo do Fluxo TO-BE

1. **Início do processo:** O paciente entra em contato com a clínica por telefone, WhatsApp ou presencialmente para solicitar um agendamento.
2. **Identificação e cadastro:** A recepcionista realiza a busca pelo CPF no sistema. Caso o paciente não possua cadastro, realiza o cadastro único conforme **RF01**. Caso já esteja cadastrado, o sistema recupera seus dados conforme **RF02**.
3. **Consulta e seleção de horário:** A recepcionista pesquisa a especialidade e o médico desejado e visualiza os horários disponíveis em tempo real, conforme **RF05**.
4. **Verificação da disponibilidade:**
   * Caso o horário não esteja disponível, o sistema apresenta outras opções de horários ou oferece a inclusão do paciente na Lista de Espera.
   * Caso esteja disponível, o sistema valida a disponibilidade e as regras de agendamento.
5. **Reserva e registro do agendamento:** A recepcionista seleciona o horário escolhido. O sistema aplica o bloqueio transacional para impedir agendamentos simultâneos, registra a consulta com o status *Agendado* e envia ao paciente a confirmação do agendamento.
6. **Lembrete automático:** Com 24 horas de antecedência, o sistema envia automaticamente um lembrete interativo por WhatsApp ou E-mail, conforme **RF09** e **RN06**.
   * *Paciente confirma:* o sistema altera o status para *Confirmado*, conforme **RN08**.
   * *Paciente solicita cancelamento:* o sistema altera o status para *Cancelado*, libera o horário e inicia o processo da Lista de Espera.
   * *Paciente não responde:* o agendamento permanece registrado até ação conforme política da clínica.
7. **Alteração da agenda médica:** Caso o médico altere sua disponibilidade ou ocorra um imprevisto, o sistema bloqueia os horários afetados, identifica os pacientes envolvidos e envia notificações automáticas para reagendamento.
8. **Recepção no dia da consulta:** O paciente comparece à clínica e a recepcionista localiza o agendamento e confirma sua chegada.
   * *Paciente compareceu:* status é alterado para *Em Atendimento*.
   * *Paciente não compareceu:* registra-se a falta e o status é alterado para *Falta*.
9. **Realização da consulta:** O médico atende o paciente e, ao finalizar, registra as informações do prontuário diretamente na plataforma centralizada, conforme **RF12** e **RN07**.
10. **Encerramento do atendimento:** Após o registro pelo médico, o sistema altera o status da consulta para *Concluído*, conforme **RN08**, e atualiza os dados do Dashboard Gerencial.
11. **Fim do processo:** O processo encerra-se após o registro do atendimento e a atualização das métricas de desempenho.

---

## 3. Engenharia de Requisitos

### 3.1. Requisitos Funcionais

| Código | Requisito Funcional | Prioridade |
| :--- | :--- | :--- |
| **RF01** | O sistema deverá permitir o cadastro de pacientes (Nome, CPF, Telefone, Data de Nascimento, E-mail). | Must Have |
| **RF02** | O sistema deverá permitir a consulta de pacientes por CPF, Nome ou Telefone. | Must Have |
| **RF03** | O sistema deverá permitir o cadastro e a manutenção de médicos e suas respectivas especialidades. | Must Have |
| **RF04** | O sistema deverá permitir o cadastro e o gerenciamento das agendas de horários dos médicos. | Must Have |
| **RF05** | O sistema deverá permitir a consulta de horários disponíveis por médico, especialidade e data. | Must Have |
| **RF06** | O sistema deverá permitir a realização e o registro de agendamentos de consultas. | Must Have |
| **RF07** | O sistema deverá permitir o registro de confirmação de presença do paciente. | Must Have |
| **RF08** | O sistema deverá permitir o cancelamento e a remarcação de consultas agendadas. | Must Have |
| **RF09** | O sistema deverá enviar lembretes automáticos de consulta para o paciente (via WhatsApp/E-mail). | Should Have |
| **RF10** | O sistema deverá gerenciar uma lista de espera de pacientes para horários desocupados por cancelamento. | Could Have |
| **RF11** | O sistema deverá disparar notificações automáticas aos pacientes afetados caso haja alteração na agenda do médico. | Should Have |
| **RF12** | O sistema deverá permitir ao médico registrar as informações do atendimento (prontuário pós-consulta). | Must Have |
| **RF13** | O sistema deverá registrar o motivo do cancelamento ou falta (*no-show*) do paciente. | Should Have |
| **RF14** | O sistema deverá disponibilizar um painel/dashboard com indicadores de desempenho (quantidade de consultas, faltas, cancelamentos). | Should Have |
| **RF15** | O sistema deverá calcular e exibir a taxa de ocupação dos horários e o tempo médio de atendimento. | Should Have |

### 3.2. Requisitos Não Funcionais

| Código | Categoria | Requisito Não Funcional |
| :--- | :--- | :--- |
| **RNF01** | Desempenho | O sistema deverá apresentar os horários disponíveis de um médico em no máximo 5 segundos após a solicitação do usuário. |
| **RNF02** | Segurança | O sistema deverá autenticar os usuários e controlar acessos por perfis. |
| **RNF03** | Privacidade | O sistema deverá armazenar e tratar os dados pessoais dos pacientes de acordo com as normas da LGPD. |
| **RNF04** | Disponibilidade | O sistema deverá apresentar disponibilidade mínima de 99,5% durante o horário de funcionamento da clínica. |
| **RNF05** | Usabilidade | O sistema deverá ser intuitivo, permitindo que a recepcionista conclua um agendamento em no máximo 4 etapas. |
| **RNF06** | Confiabilidade | O sistema deverá utilizar mecanismos de bloqueio para impedir agendamentos concorrentes simultâneos no mesmo milissegundo. |
| **RNF07** | Compatibilidade | O sistema deverá ser acessível via navegadores web modernos (Chrome, Firefox, Edge, Safari), sem necessidade de instalação de plugins adicionais. |
| **RNF08** | Manutenibilidade | O sistema deverá possuir arquitetura modular com código documentado, a fim de facilitar futuras expansões. |
| **RNF09** | Integração | O sistema deverá integrar-se a uma API de mensageria (WhatsApp/E-mail) para o envio automatizado de lembretes. |
| **RNF10** | Portabilidade | A interface do sistema deverá se adaptar a telas de computadores e tablets. |

---

## 4. Indicadores de Desempenho

Os indicadores de desempenho serão utilizados para acompanhar como está funcionando o processo de atendimento e agendamento da Clínica Vida+ Saúde. Com eles, a direção e a gerência poderão identificar problemas e verificar se as melhorias propostas estão trazendo resultados.

| Indicador | Objetivo |
| :--- | :--- |
| **Quantidade de consultas realizadas** | Verificar a quantidade de atendimentos realizados em determinado período. |
| **Taxa de cancelamentos** | Acompanhar a quantidade de consultas canceladas. |
| **Taxa de faltas (*No-show*)** | Verificar quantos pacientes não compareceram às consultas. |
| **Tempo médio de atendimento** | Acompanhar quanto tempo, em média, dura cada atendimento. |
| **Taxa de ocupação dos horários** | Verificar quanto dos horários disponíveis dos médicos estão sendo utilizados. |

Esses indicadores ajudam a clínica a entender melhor o funcionamento da agenda. Por exemplo, se a quantidade de faltas estiver alta, a clínica pode verificar se os lembretes de consulta estão funcionando corretamente. Da mesma forma, muitos cancelamentos podem indicar a necessidade de melhorar o processo de confirmação ou utilizar melhor a lista de espera.

O sistema também poderá apresentar esses dados em um **dashboard**, facilitando o acompanhamento pela direção e permitindo uma visualização mais rápida dos resultados.

Para que os indicadores sejam calculados corretamente, é importante que os agendamentos tenham seus status atualizados. A regra **RN08** define os status que podem ser utilizados: *Agendado*, *Confirmado*, *Em Atendimento*, *Concluído*, *Cancelado* e *Falta*.

---

## 5. Relação com o Ciclo BPM

O trabalho realizado para a Clínica Vida+ Saúde possui relação direta com o ciclo BPM (*Business Process Management*), pois primeiro foi analisado como o processo funciona atualmente (**AS-IS**), depois foram identificados os problemas e, a partir disso, foram propostas melhorias para o processo (**TO-BE**).

1. **AS-IS (Análise do Processo Atual):** Verificou-se que a clínica utiliza planilhas, telefone e WhatsApp para realizar os agendamentos, e que as informações do atendimento médico ficam em um sistema separado. Isso gera conflitos de horários, dados desatualizados, retrabalho e dificuldade de comunicação.
2. **TO-BE (Proposta de Melhorias):** Propos-se o cadastro único de pacientes, agenda centralizada, lembretes automáticos, lista de espera, notificações de alteração de agenda e integração com o prontuário.
3. **Implementação:** O sistema apoia diretamente a execução do processo centralizado.
4. **Monitoramento:** Através dos indicadores de desempenho (taxa de faltas, ocupação, etc.).
5. **Novas Melhorias:** Caso algum indicador apresente desempenho insatisfatório, a clínica analisa o problema e desenvolve novas soluções.

```
AS-IS → Identificação dos problemas → Propostas de melhoria → TO-BE → Implementação → Monitoramento → Novas melhorias
```

A **Engenharia de Requisitos** ajuda a transformar os problemas encontrados no processo em requisitos para o sistema, enquanto o **BPM** ajuda a analisar, acompanhar e melhorar o processo de forma contínua.

---

## 6. Questões para Discussão

1. **Qual é a diferença entre uma função e um processo de negócio?**
   * **Resposta:** Função é uma atividade isolada (ex.: "verificar agenda"). Processo de negócio é uma sequência de atividades interligadas, com início e fim, que entrega valor ao cliente — no caso, só entrega valor quando o paciente é efetivamente atendido.

2. **Por que o processo de agendamento deve ser analisado de forma ponta a ponta?**
   * **Resposta:** Porque os problemas do caso estão nas transições entre etapas (recepção → confirmação → médico), e não em uma atividade isolada. Vislumbrar o processo inteiro permite identificar a causa raiz dos gargalos.

3. **Quais atividades atualmente geram maior retrabalho?**
   * **Resposta:** Registro em planilhas separadas, repetição de dados de pacientes já cadastrados, contato manual em alterações de agenda e busca manual por paciente substituto em cancelamentos.

4. **Quais atividades poderiam ser automatizadas?**
   * **Resposta:** Envio de lembretes, liberação de horário após cancelamento, notificação de mudanças de agenda, lista de espera, atualização de status e cálculo de indicadores.

5. **Quais regras de negócio precisam obrigatoriamente ser implementadas pelo sistema?**
   * **Resposta:** Regras obrigatórias: **RN01** (cadastro único), **RN02** (sem conflito de horário), **RN03** (agendar só em horário disponível), **RN04** (liberar horário no cancelamento) e **RN07** (só médico altera prontuário).

6. **Quais informações são essenciais para o processo?**
   * **Resposta:** Dados do paciente, especialidade e disponibilidade do médico, status do agendamento e registro do atendimento.

7. **Qual é o principal gargalo identificado?**
   * **Resposta:** Falta de agenda centralizada e atualizada em tempo real — causa raiz dos conflitos de horário e divergências de confirmação.

8. **Quais requisitos surgiram diretamente da análise do processo?**
   * **Resposta:** **RF04/05/06** (agenda centralizada), **RF08/10** (cancelamento e lista de espera), **RF09/11** (lembretes e notificações) e **RF12** (registro do atendimento integrado).

9. **Quais requisitos não funcionais são críticos para esse sistema?**
   * **Resposta:** **RNF02** e **RNF03** (segurança e LGPD, por lidarem com dados sensíveis), **RNF06** (bloqueio transacional, evita conflito de horário) e **RNF04** (disponibilidade do sistema).

10. **Como os indicadores podem auxiliar na melhoria contínua do processo?**
    * **Resposta:** Mostram, com dados reais, se as melhorias estão funcionando (ex.: taxa de faltas caindo com lembretes) e apontam onde ainda ajustar — fechando o ciclo de
