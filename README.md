#Documentação Funcional - Script de Consulta Correios

#Introdução
Para acessar o arquivo mencionado neste documento, siga o passo a passo abaixo:

Após efetuar o login no console instalado em seu computador, acesse Configurações > Configurações do Site > Gerenciador de Arquivos.

No Gerenciador de Arquivos, altere o tipo de arquivo para "Scripts Personalizados".

Após essa configuração, todos os arquivos estarão disponíveis. O arquivo mencionado neste documento é consulta.php.

Objetivo
Este script PHP tem como objetivo integrar dados de tickets do sistema RightNow com informações relacionadas ao Correios, como código de postagem, data de postagem e status, obtidos por meio de uma API externa.

Fluxo de Execução
Autenticação e Inicialização:
O script inicia definindo a localização e autenticando o agente.
Inicializa a API de Conexão do RightNow.
Entrada de Dados:

Obtém dados JSON da requisição, especialmente o ID do incidente do RightNow.
Requisição à API Externa:

Utiliza a extensão cURL para fazer uma requisição GET a uma API externa (URL fornecida).
Envia parâmetros na query para buscar tickets específicos associados ao incidente do RightNow.
Processamento da Resposta:

Decodifica a resposta JSON da API externa.
Verifica se existem ativos ("assets") retornados na resposta.
Atualização do Incidente no RightNow:

Para cada ticket retornado:
Verifica a presença do campo 'state_id'.
Atribui valores relevantes aos campos personalizados do incidente no RightNow.
Salva as alterações no incidente.
Saída de Dados:

Imprime informações relevantes dos tickets processados.
Fechamento da Sessão cURL:

Fecha a sessão cURL após a conclusão do processamento.
Pré-requisitos
A extensão cURL deve estar habilitada no ambiente PHP.
O ambiente deve ter acesso à API externa (URL fornecida) para consulta.
Configurações
Nenhuma configuração adicional é necessária, além das credenciais de autenticação do agente RightNow e da URL da API externa.
Uso
Chamada do Script:
O script é chamado com uma requisição HTTP contendo dados JSON, especialmente o ID do incidente.
json

Possíveis Saídas
O script imprime informações sobre os tickets processados, incluindo estado, código de postagem, data de postagem e status.
Tratamento de Erros
Em caso de erro na execução da requisição cURL ou qualquer exceção, mensagens de erro detalhadas são impressas.
Avisos
A autenticação e autorização são fundamentais para o acesso e manipulação de dados no RightNow e API externa.
