# Estrutura do Banco de Dados

## Tabelas Principais

### Chamados

Tabela central do sistema.

Armazena:

* Equipamento
* TAG
* Marca
* Módulo
* Problema reportado
* Solução aplicada
* Status do chamado
* Horas de parada
* Horas de manutenção
* Usuário de abertura
* Usuário de finalização

---

### ChamadoComentarios

Relacionamento:

Chamado 1:N Comentários

Armazena:

* Nome do usuário
* Matrícula
* Comentário
* Data e hora da inclusão

---

### ChamadoAnexos

Relacionamento:

Chamado 1:N Anexos

Armazena:

* Nome original do arquivo
* Caminho físico do documento
* Tipo do anexo
* Usuário responsável pelo upload
* Data de inclusão

---

### Equipamentos

Cadastro de equipamentos disponíveis para abertura de chamados.

Campos principais:

* Nome
* TAG
* Marca
* Status ativo/inativo

---

### EmailQueue

Fila de processamento assíncrono de notificações por e-mail.

Campos principais:

* Destinatário
* Assunto
* Corpo da mensagem
* Status de processamento
* Quantidade de tentativas
* Mensagem de erro
* Anexo associado

---

## Tabelas Auxiliares

### UsuariosSistema

Tabela prevista para futura implementação de gerenciamento de usuários.

Atualmente não é utilizada pela aplicação em produção, pois o controle de acesso é realizado por sessão de usuário e perfil técnico.

---

## Relacionamentos

Chamados
├── ChamadoComentarios
├── ChamadoAnexos
└── EmailQueue

---

## Estratégia de Armazenamento de Anexos

Os documentos não são armazenados diretamente no banco de dados.

O banco mantém apenas:

* Nome do arquivo
* Caminho físico
* Metadados do anexo

Os arquivos são armazenados em diretório externo ao SQL Server, reduzindo o tamanho do banco e facilitando o gerenciamento dos documentos.

---

## Observações

A solução foi projetada para manter o banco de dados enxuto, armazenando apenas informações transacionais e de rastreabilidade.

Arquivos, logs operacionais e processamento de notificações são tratados por componentes externos especializados.
