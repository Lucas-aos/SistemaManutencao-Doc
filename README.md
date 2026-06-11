# Sistema de Controle de Chamados de Manutenção

![Status](https://img.shields.io/badge/Source%20Code-Private-blue)
![.NET](https://img.shields.io/badge/.NET-8-purple)
![SQL Server](https://img.shields.io/badge/SQL%20Server-Database-red)
![WinForms](https://img.shields.io/badge/Windows%20Forms-Desktop-green)

![Arquitetura](docs/images/arquitetura-projeto.png)

Sistema desktop desenvolvido em C# (.NET 8) para gerenciamento de chamados de manutenção em ambiente industrial farmacêutico.

---

## Sobre o Projeto

O Sistema de Controle de Chamados de Manutenção foi desenvolvido para centralizar o gerenciamento de ocorrências relacionadas a equipamentos laboratoriais e industriais, permitindo o acompanhamento completo do ciclo de vida de um chamado, desde sua abertura até sua conclusão.

O projeto foi construído utilizando arquitetura em camadas, SQL Server para persistência dos dados e um serviço independente para processamento assíncrono de notificações por e-mail.

---

## Principais Funcionalidades

### Gestão de Chamados

* Abertura de chamados
* Atendimento de chamados
* Finalização de chamados
* Reabertura de chamados
* Exclusão/Inativação
* Controle de status

### Gestão de Comentários

* Histórico completo de interações
* Registro de usuário e data
* Controle por perfil de acesso
* Bloqueio de inclusão após finalização para usuários comuns

### Gestão de Anexos

* Upload de documentos
* Download de anexos
* Exclusão controlada por perfil
* Armazenamento externo ao banco de dados

### Gestão de Equipamentos

* Cadastro de equipamentos
* Controle de TAG
* Controle de marca
* Controle de ativação/desativação

### Notificações por E-mail

* Geração automática de notificações
* Processamento assíncrono
* Controle de tentativas
* Registro de falhas
* Rastreabilidade completa

---

## Tecnologias Utilizadas

| Tecnologia               | Utilização                 |
| ------------------------ | -------------------------- |
| .NET 8                   | Aplicação principal        |
| Windows Forms            | Interface gráfica          |
| SQL Server               | Banco de dados             |
| Outlook Interop          | Envio de e-mails           |
| Windows Tray Application | Serviço de processamento   |
| Git                      | Controle de versão         |
| GitHub                   | Hospedagem da documentação |

---

## Arquitetura

A aplicação utiliza arquitetura em camadas:

* Camada de Apresentação (WinForms)
* Camada de Serviços
* Camada de Repositórios
* Camada de Dados (SQL Server)

Além disso, possui um serviço independente responsável pelo processamento da fila de e-mails.

Documentação detalhada:

* docs/arquitetura.md
* docs/banco-dados.md
* docs/fluxo-email.md

---

# Capturas de Tela

## Tela de Login

![Login](docs/images/login.png)

---

## Painel Principal

![Painel Principal](docs/images/painel-principal.png)

---
## Abertura de Chamado

![Abertura de Chamado](docs/images/abertura-1.png)

---

## Detalhamento de Chamado

![Detalhes do Chamado](docs/images/Detalhes-1.png)
![Detalhes do Chamado](docs/images/Detalhes-2.png)
![Detalhes do Chamado](docs/images/Detalhes-3.png)

---
## Filtro de Chamado

![Filtro de Chamado](docs/images/Filtro-chamados.png)

---
## Configuração de Equipamentos

![Configuração de Equipamentos](docs/images/equipamentos.png)
![Configuração de Equipamentos](docs/images/abertura-2.png)

---

## Arquitetura do Banco de Dados

![Arquitetura do Banco de Dados](docs/images/DiagramaBanco.png)

---


## Fluxo de Processamento de E-mails

![Fluxo de E-mails](docs/images/Fluxo-emails.png)

---


## Funcionalidades Implementadas

### Controle de Chamados

* Abertura
* Atendimento
* Encerramento
* Reabertura
* Inativação

### Controle de Comentários

* Registro histórico
* Controle por perfil
* Bloqueio em chamados finalizados

### Controle de Anexos

* Upload
* Download
* Exclusão controlada

### Processamento de E-mails

* Fila assíncrona
* Controle de tentativas
* Registro de falhas
* Integração com Outlook

---

## Status do Projeto

Versão atual:

**v1.1.1**

---

## Código-Fonte

Este repositório possui finalidade exclusivamente documental.

O código-fonte completo encontra-se em repositório privado.

Disponível para recrutadores, gestores técnicos ou avaliadores mediante solicitação.

---

## Autor

Lucas Oliveira
