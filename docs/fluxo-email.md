# Fluxo de Processamento de E-mails

## Objetivo

Evitar que o sistema principal fique bloqueado durante o envio de notificações.

## Fluxo

### 1. Usuário realiza ação

Exemplos:

* Finalização de chamado
* Reabertura
* Solicitação de aprovação

---

### 2. Sistema cria registro na EmailQueue

São armazenados:

* Destinatário
* Assunto
* Corpo
* Status inicial

---

### 3. Email Processor identifica pendências

O serviço executa continuamente:

SELECT emails pendentes

---

### 4. Processamento

Para cada registro:

* Bloqueia o item
* Monta mensagem
* Conecta ao Outlook
* Envia e-mail

---

### 5. Atualização de status

Sucesso:

* Status = ENVIADO

Falha:

* Incrementa tentativas
* Registra erro

---

### 6. Monitoramento

São registrados:

* Data/Hora
* Destinatários
* Resultado
* Erros
* Número de tentativas

## Benefícios

* Processamento assíncrono
* Maior estabilidade
* Controle de falhas
* Auditoria completa
* Melhor experiência do usuário
