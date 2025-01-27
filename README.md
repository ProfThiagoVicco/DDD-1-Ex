# Design Estratégico do Projeto: Keller's Health

## Objetivo
Identificar os subdomínios do **Keller's Health**, classificá-los (Core, Supporting, Generic) e desenhar os bounded contexts, incluindo suas interações. Esse exercício ajuda a criar uma visão clara e estratégica do domínio.

---

## 1. Nome do Projeto
**Keller's Health**

---

## 2. Objetivo Principal do Projeto
Facilitar o acesso a consultas médicas online, conectando pacientes e médicos por meio de uma plataforma confiável e eficiente, que inclui agendamento, histórico médico e chamadas de vídeo.

---

## 3. Identificação dos Subdomínios

| **Subdomínio**              | **Descrição**                                                                                      | **Tipo**         |
|-----------------------------|--------------------------------------------------------------------------------------------------|------------------|
| Gestão de Consultas         | Gerencia o agendamento, consulta por vídeo e emissão de atestados e receitas.                   | Core Domain      |
| Cadastro de Pacientes       | Gerencia o cadastro e informações pessoais e médicas dos pacientes.                             | Supporting       |
| Gerenciamento de Médicos    | Cadastro e validação de médicos, incluindo suas licenças e horários disponíveis.                | Supporting       |
| Pagamentos                  | Processa pagamentos e gerencia os repasses para médicos e clínicas.                            | Generic          |
| Comunicação por Vídeo       | Realiza chamadas de vídeo durante as consultas.                                                | Generic          |
| Autenticação de Usuários    | Gerencia login, permissões e segurança de acesso.                                              | Generic          |

---

## 4. Desenho dos Bounded Contexts

| **Bounded Context**           | **Responsabilidade**                                                                                 | **Subdomínios Relacionados** |
|-------------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------|
| Contexto de Consultas         | Gerencia todo o processo de consultas médicas, do agendamento à finalização, incluindo receitas.    | Gestão de Consultas         |
| Contexto de Cadastro          | Centraliza o cadastro de pacientes e médicos, armazenando informações básicas e históricas.         | Cadastro de Pacientes, Gerenciamento de Médicos |
| Contexto de Pagamentos        | Processa cobranças de consultas e gerencia repasses para médicos e clínicas.                       | Pagamentos                  |
| Contexto de Comunicação       | Gerencia as chamadas de vídeo durante as consultas médicas.                                        | Comunicação por Vídeo       |
| Contexto de Autenticação      | Controla login, cadastro e permissões de usuários (pacientes, médicos e administradores).           | Autenticação de Usuários    |

---

## 5. Comunicação entre os Bounded Contexts

| **De (Origem)**              | **Para (Destino)**          | **Forma de Comunicação**    | **Exemplo de Evento/Chamada**                  |
|------------------------------|-----------------------------|-----------------------------|-----------------------------------------------|
| Contexto de Consultas        | Contexto de Pagamentos      | Mensageria (Evento)         | "Consulta Finalizada"                         |
| Contexto de Cadastro         | Contexto de Consultas       | API                         | Obter informações de paciente e médico        |
| Contexto de Consultas        | Contexto de Comunicação     | API                         | Iniciar chamada de vídeo                      |
| Contexto de Autenticação     | Contexto de Cadastro        | API                         | Validar login e permissões                    |

---

## 6. Definição da Linguagem Ubíqua

| **Termo**                    | **Descrição**                                                                                   |
|------------------------------|-----------------------------------------------------------------------------------------------|
| Consulta                     | Sessão médica entre paciente e médico, podendo incluir chamada de vídeo, receita ou atestado. |
| Paciente                     | Usuário que agenda e realiza consultas na plataforma.                                         |
| Médico                       | Profissional de saúde que realiza as consultas.                                              |
| Prontuário                   | Registro com o histórico médico do paciente, incluindo diagnósticos e receitas.              |
| Receita                      | Prescrição médica emitida durante uma consulta.                                              |
| Pagamento                    | Transação financeira realizada pelo paciente para completar uma consulta.                    |
| Disponibilidade              | Horários livres dos médicos para agendamento de consultas.                                   |

---

## 7. Estratégia de Desenvolvimento

| **Subdomínio**              | **Estratégia**                         | **Ferramentas ou Serviços (se aplicável)** |
|-----------------------------|---------------------------------------|-------------------------------------------|
| Gestão de Consultas         | Desenvolvimento interno               |                                           |
| Cadastro de Pacientes       | Desenvolvimento interno               |                                           |
| Gerenciamento de Médicos    | Desenvolvimento interno               |                                           |
| Pagamentos                  | Terceirizar usando API Stripe         | Stripe                                    |
| Comunicação por Vídeo       | Terceirizar usando API Twilio         | Twilio                                    |
| Autenticação de Usuários    | Usar serviço externo                  | Auth0                                     |

---

## 8. Diagrama Visual (Opcional, mas Recomendado)

---

## Dicas para Apresentação
- Explique o **Core Domain** (Gestão de Consultas) como o diferencial competitivo.  
- Justifique por que alguns subdomínios foram classificados como Supporting ou Generic.  
- Destaque como a comunicação entre bounded contexts é eficiente e escalável.

---

Boa sorte! 🚀
