# Sistema de Controle de Chamados de Manutenção

## Visão Geral

Aplicação desktop desenvolvida em C# (.NET 8) para gerenciamento de chamados de manutenção em ambiente industrial farmacêutico.

O sistema foi criado para centralizar solicitações de manutenção, controlar o ciclo de vida dos chamados, registrar evidências técnicas, acompanhar tempo de parada de equipamentos e automatizar notificações por e-mail.

O código-fonte completo permanece privado por conter regras de negócio e integrações internas da organização.

---

## Objetivos do Projeto

* Padronizar abertura e tratamento de chamados.
* Controlar SLA de manutenção.
* Registrar histórico de intervenções.
* Permitir anexação de evidências.
* Automatizar notificações por e-mail.
* Disponibilizar indicadores para gestão.

---

## Tecnologias Utilizadas

### Backend

* C#
* .NET 8
* Windows Forms

### Banco de Dados

* SQL Server

### Comunicação

* Outlook Interop
* Processamento assíncrono de fila de e-mails

### Arquitetura

* Repository Pattern
* Services Layer
* Separação por responsabilidades

---

## Principais Funcionalidades

### Abertura de Chamados

* Registro de equipamento.
* TAG do equipamento.
* Descrição do problema.
* Data e hora da parada.

### Gestão de Chamados

* Aberto
* Em Atendimento
* Finalizado

### Comentários

* Histórico completo por chamado.
* Controle por usuário.

### Anexos

* PDF
* PNG
* JPG
* JPEG

Tipos de anexo:

* Mensagem de Erro
* Cromatograma
* Resultado de Teste
* Relatório Final
* O.S.
* Orçamento
* Outros

### Controle de Permissões

#### Usuário Comum

* Abrir chamado
* Consultar chamado
* Adicionar comentários

#### Técnico

* Finalizar chamado
* Excluir anexos
* Excluir comentários
* Acesso administrativo

### Processamento Automático de E-mails

Serviço executado em segundo plano responsável por:

* Leitura de fila de e-mails
* Envio automático via Outlook
* Controle de tentativas
* Registro de falhas

---

## Estrutura do Banco de Dados

### Tabelas Principais

| Tabela             | Função                          |
| ------------------ | ------------------------------- |
| Chamados           | Registro principal dos chamados |
| ChamadoComentarios | Histórico de comentários        |
| ChamadoAnexos      | Evidências e documentos         |
| Equipamentos       | Cadastro de equipamentos        |
| UsuariosSistema    | Controle de usuários            |
| EmailQueue         | Fila de envio de e-mails        |

---

## Fluxo Operacional

1. Usuário abre chamado.
2. Chamado recebe status "Aberto".
3. Técnico inicia atendimento.
4. Chamado recebe status "Em Atendimento".
5. Comentários e anexos são registrados.
6. Técnico finaliza atendimento.
7. Chamado recebe status "Finalizado".
8. Sistema registra tempos de manutenção.
9. Serviço de e-mail envia notificações.

---

## Desafios Técnicos Resolvidos

### Controle de Concorrência

Implementação de fila de e-mails com prevenção de processamento duplicado.

### Upload de Evidências

Armazenamento centralizado de anexos com validação de extensões.

### Processamento Assíncrono

Execução contínua do serviço de e-mail utilizando Tasks e CancellationToken.

### Segurança Operacional

Separação de funcionalidades entre usuários comuns e técnicos.

---

## Evolução do Projeto

Versão atual:

**1.1.1**

Melhorias recentes:

* Inclusão de fila de e-mails.
* Histórico de comentários.
* Múltiplos tipos de anexos.
* Controle de permissões.
* Interface Tray para processamento em segundo plano.

---

## Autor

Projeto desenvolvido para suporte às operações de Controle de Qualidade, Engenharia e Manutenção de Equipamentos em ambiente industrial farmacêutico.
