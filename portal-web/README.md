# Desafio: Constução de Portal Web

## Objetivo

O objetivo deste desafio é testar as habilidades do candidato no desenvolvimento de aplicações web utilizando as tecnologias .Net Core, Angular, Docker e banco de dados.

O portal é uma aplicação web utilizada por nossos colaboradores e clientes. Ele permite o cadastro de clientes, a configuração dos serviços, visualização de dashboards, baixa de relatórios, etc.

## Requisitos

Neste desafio o candidato irá construir um portal com os seguintes requisitos:

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
  - Exibir as informações do Cliente juntamente com a imagem de sua biometria recortada do documento
- Página - Formulário de Cadastro de Cliente
  - Preenchimento do formulário:
    - Fazer upload do documento com foto
    - Consumir "content-extraction" do API do mostQI para preencher o nome, RG e data de nascimento
    - Permitir que o usuário confirme se os dados extraídos estão corretos e preencher o email
    - Consumir "face-extract-features" do API do mostQI extrair os dados biométricos do Cliente
    - Salvar o documento, o formulário e os dados biométricos no banco de dados
    - Criar um usuário no módulo de usuários do tipo "Cliente"
    - É necessário registrar o usuário que realizou o cadastro e a data de cadastro.
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
  - Back-end: .Net Core 2.2+
  - Front-end: Angular 8+
- BANCO DE DADOS
  - MongoDB ou qualquer banco relacional
- INFRAESTRUTURA
  - O projeto deve ser containerizado através do DOCKER. Saiba mais em:
    - [What is a container?](https://www.docker.com/resources/what-container)
    - [Dotnet Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core)
