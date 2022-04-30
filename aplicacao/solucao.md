# Solução aplicada

### 1. Containerização do Banco

Foi criado um arquivo docker-compose.yml para realizar a containerização do banco de dados. Esse arquivo contém o serviço db e a imagem do Postgres que será usada.

### 2. Containerização da Aplicação + Banco

Aqui foi adicionado o serviço web no docker-compose.yml. Além disso, o Dockerfile foi criado para criar uma imagem com as dependências necessárias. Também foi feito o arquivo entrypoint.sh para corrigir um problema específico do Rails que impede a reinicialização do servidor quando um arquivo server.pid já existe. Este script é executado toda vez que o container é iniciado. 

### 3. Adição de um container do Nginx

Nessa etapa foi criada a pasta nginx com o arquivo de configuração app.conf e o Dockerfile. Além disso, no docker-compose.yml foi adicionado o serviço responsável pelo nginx.

### 4.  Integração Contínua (CI)

Para o CI foram criados 3 workflows dentro da pasta .github/workflows. O build da aplicação, os testes usando o rspec e o lint foi feito utilizando o Rubocop.

### 5. Deploy Contínuo (CD)