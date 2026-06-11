# Arquitetura da Aplicação

## Visão Geral

A aplicação foi construída utilizando arquitetura em camadas visando:

* Separação de responsabilidades
* Facilidade de manutenção
* Baixo acoplamento
* Escalabilidade

## Camadas

### Camada de Apresentação

Responsável pela interação com o usuário.

Componentes:

* LoginForm
* PainelChamadosForm
* DetalhesChamadoForm
* Formulários auxiliares

Tecnologia:

* Windows Forms
* .NET 8

---

### Camada de Serviços

Responsável pelas regras de negócio.

Exemplos:

* AttachmentService
* PasswordService
* EmailProcessorService

Responsabilidades:

* Validações
* Orquestração
* Integração entre componentes

---

### Camada de Repositórios

Responsável pelo acesso aos dados.

Exemplos:

* ChamadoRepository
* ChamadoAnexoRepository
* ChamadoComentarioRepository
* EquipamentoRepository
* EmailQueueRepository

Responsabilidades:

* Consultas SQL
* Inserções
* Atualizações
* Exclusões

---

### Camada de Dados

Banco SQL Server.

Responsável por:

* Persistência
* Relacionamentos
* Integridade dos dados

---

## Serviço de Background

A aplicação possui um componente independente:

Email Processor

Responsável por:

* Leitura da fila de e-mails
* Envio via Outlook
* Controle de tentativas
* Registro de falhas

---

## Benefícios da Arquitetura

* Facilidade de evolução
* Separação clara de responsabilidades
* Melhor testabilidade
* Menor dependência entre módulos
