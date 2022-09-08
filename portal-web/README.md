# Desafio: Constução de Portal Web

## Objetivo

Esperamos testar as habilidades do candidato no desenvolvimento de aplicações web utilizando as tecnologias .Net Core, React, Docker e banco de dados.

Para isso, deverá ser desenvolvido um portal web para o uso de colaboradores internos e clientes. Ele deverá permitir o cadastro de clientes, a configuração dos serviços, visualização de dashboards, baixa de relatórios, etc.

## Requisitos

Neste desafio o candidato irá construir um portal com as seguintes características:

### Módulo: Usuários

- Página – Login
  - Login por usuário e senha
  - Após o login o usuário é direcionado para o módulo "Colaborador" ou "Cliente" de acordo com o tipo de usuário
- Página - Cadastro de Usuário
  - Preenchimento do formulário:
    - Preencher o nome e e-mail
    - Salvar o usuário com o tipo "Colaborador"
- Página "Esqueci minha Senha" (**BONUS**)
  - Enviar e-mail com link para recuperação

### Módulo: Colaborador (Precisa estar logado)

- Página – Clientes
  - Tabela paginada que permita a pesquisa por nome
  - Tela - Dados dos Cliente
  - Exibir as informações do Cliente juntamente com sua selfie
- Página - Formulário de Cadastro de Cliente
  - Preenchimento do formulário:
    - Fazer upload de documento de identificação com foto
    - Usar o mostQI para auxiliar no cadastro de novos usuários: https://docs.mostqi.com/. A client key deve ser solicitada pelo e-mail rh@most.com.br.
    - Consumir o content-extraction do mostQI para preencher automaticamente o nome, RG e data de nascimento
    - Permitir que o usuário confirme se os dados extraídos estão corretos, completar o cadastro com o preenchimento do email
    - Consumir o liveness do mostQI para realizar uma prova de vida do usuário (https://mostqiapi.com/liveness/detect)
    - Usar o retorno do liveness (frontalImage) mais o documento de identificação para submeter ao face-compare e verificar se a pessoa que realizou a prova de vida é a mesma que está no documento de identificação
    - Salvar o documento, a selfie e o formulário no banco de dados
    - Finalizar a criação do usuário
    - Criar registro de rastreabilidade do processo de cadastro com usuário, data e hora.
- Página - Histórico de Alteração dos Clientes
  - Tabela paginada que permita a pesquisa por nome do cliente ou usuário que realizou o cadastro

### Módulo: Cliente (Precisa estar logado)

- Serviço - Monitoramento da Cotação do Dólar
  - Crie um serviço de background (Background Service) que verifique a cotação do dólar a cada minuto e registre a informação em banco de dados. A fonte da informação sobre a cotação do dólar é de livre escolha.
- Página - Cotação do Dólar
  - Tabela paginada que permita a busca por data e hora das cotações registradas pelo serviço acima
  - Exibir média, máxima e mínima no dia
  - Exibir um gráfico das variações no dia (PLUS)

## Notas

Tecnologias a serem exploradas:

- FRAMEWORKS:
  - Back-end: .Net Core (Última versão)
  - Front-end: React (Última versão)
- BANCO DE DADOS
  - MongoDB
- INFRAESTRUTURA
  - O projeto deve ser containerizado através do DOCKER. Saiba mais em:
    - [What is a container?](https://www.docker.com/resources/what-container)
    - [Dotnet Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core)
