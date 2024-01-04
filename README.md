# Gentileza alterar a branch para dev.

# EnviarTicketsAPI.php - Script de Envio de Tickets para a API Zammad

## Descrição

Este script PHP, criado por Caique Renan Alves em 08/12/2023 às 17:24, é responsável pelo envio de tickets para a API Zammad.

## Requisitos

- Ambiente com acesso à API Zammad.
- Credenciais de autenticação do agente RightNow.
- O arquivo `AgentAuthenticator.phph` está incluído no caminho especificado.

## Instalação

1. Faça o login no console instalado em seu computador.
2. Acesse Configurações > Configurações do Site > Gerenciador de Arquivos.
3. Altere o tipo de arquivo para "Scripts Personalizados".
4. Todos os arquivos estarão disponíveis; o arquivo mencionado é `EnviarTicketsAPI.php`.

## Uso

O script é projetado para ser chamado por meio de uma requisição HTTP contendo dados JSON, especialmente o ID do incidente.

Exemplo de requisição:

```json
{
  "id": 114249
}
```
Fluxo de Execução
Autenticação e Inicialização:

Configuração da localização e autenticação do agente.
Inicialização da API de Conexão do RightNow.
Entrada de Dados:

Obtenção dos dados JSON da requisição.
Envio de Ticket para a API Zammad:

Acessa o objeto Incident com base no ID fornecido.
Coleta informações relevantes do incidente.
Cria uma requisição para a API Zammad.
Envia a requisição utilizando cURL.
Analisa a resposta da API Zammad.
Atualiza o incidente no RightNow com o ID da resposta da API Zammad.
Tratamento de Erros
Em caso de falha na execução ou exceção, mensagens de erro detalhadas são impressas.

Avisos
A autenticação e autorização são fundamentais para o acesso e manipulação de dados no RightNow e na API Zammad.
