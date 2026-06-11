# Estrutura do Banco de Dados

## Tabelas Principais

### Chamados

Tabela central do sistema.

Armazena:

* Equipamento
* TAG
* Marca
* Módulo
* Problema
* Solução
* Status
* Horas de parada
* Horas de manutenção

---

### ChamadoComentarios

Relacionamento:

Chamado 1:N Comentários

Armazena:

* Usuário
* Matrícula
* Comentário
* Data

---

### ChamadoAnexos

Relacionamento:

Chamado 1:N Anexos

Armazena:

* Nome original
* Caminho físico
* Tipo do anexo
* Usuário de upload
* Data

---

### Equipamentos

Cadastro de equipamentos.

Campos principais:

* Nome
* TAG
* Marca
* Ativo

---

### UsuariosSistema

Cadastro de usuários.

Campos principais:

* Nome
* Matrícula
* Perfil
* Ativo

---

### EmailQueue

Fila de processamento de e-mails.

Campos principais:

* Destinatário
* Assunto
* Corpo
* Status
* Tentativas
* Erro

---

## Relacionamentos

Chamados
├── ChamadoComentarios
└── ChamadoAnexos

Chamados
└── EmailQueue

---

## Estratégia de Anexos

Os arquivos não são armazenados no banco.

O banco mantém apenas:

* Nome
* Caminho físico
* Metadados

Os documentos ficam armazenados em diretório externo.
