## API Rest sistema Todo list em Node.JS :desktop_computer:

Olá seja bem vindo ao repositorio do projeto API todo list (lista de afazeres). :rocket:

Este projeto consiste em uma API no padrão REST de uma aplicação de lista de afazeres,
esta API e consumida por um front-end em React. Utilizei a arquitetura `MSC` para construir esta api, de forma que sua `manutenção e adição de novas funcionalidades` ficam mais faceis de se implementar.

Sua estrutura interna de arquivos esta dividida por `papel técnico`.

Fique a vontade para contribuir, será um prazer interagir com você!

## Estrutura

![estrutura](./public/imgs/01-estrutura-project.png)

**`MSC`** - MODEL, SERVICES e CONTROLLERS

1. Pasta model é responsável por toda interface com banco de dados, query's, conexão etc.

2. Pasta Services se concentra toda regra de negócio e chamadas ao banco de dados.

3. Pasta Controllers se dedica apenas para receber requisições e direcionar ao services, e por
    consequência receber as respostas e repassar para rotas da aplicação.

4. Pasta Schemas ficam todas as validações da aplicação, ex: regex de email etc.

5. Pasta de middlewares ficam os middlewares, mais especifico neste projeto middleware de erro.

6. Pasta routers contém as rotas da aplicação.

7. Pasta public/imgs contém as imagens utilizadas no projeto.

## tecnologias utilizadas

- Linguagens:
  - NodeJs
- Database: 
  - Mongodb
- Tratamento de erros:
  - hapi/boom
  - express-rescue
  - joi
- Configurações
  - Dotenv
- Organização e Padronização de codigo:
  - Eslint / config-airbnb-base
- Facilitador de desenvolvimento:
  - nodemon
- framework's:
  - Express

## Começando

#### Para executar o projeto, será necessário ter instalado:

1. [MongoDB](https://www.mongodb.com/try/download/community) banco utilizado para o desenvolvimento
2. [Insomnia](https://insomnia.rest/download) para fazer requisições nas rotas da API. (ou qualquer outro para testes de API)
3. [NodeJS](https://nodejs.org/en/) Este projeto necessita do NodeJs instalado em seu computador para rodar localmente.

#### próximos passos

- Clone o repositório `git clone git@github.com:clebertonf/Projeto-API-REST-todo-list.git`
- Na raiz do projeto rode o comando **npm install** para instalar as depedências do projeto.

## Configuracão

Crie um arquivo com nome **`.env`** na raiz do projeto, dentro deste arquivo adicione as seguintes variáveis de ambiente:

1. `PORT`=3000
2. `MONGO_DB_URL` = 'mongodb://127.0.0.1:27017'

![arquivo-env](./public/imgs/02-arquivo-env.png)

## Executando API

Verifique o `package.json`, la se encontram scripts para execução do projeto.

- `"debug": "nodemon index.js",`  (`npm run dev`) inicia o projeto com nodemon.
- `"start": "node index.js",` (`npm start`) inicia o projeto com  node.

#### Após todos os passos execute npm run dev na raiz para iniciar o projeto.

## Endpoints da API (Criação, leitura, edição, deleção de tarefa)

1. #### `POST` localhost:3000/todo/create
  Este endpoint cadastra uma tarefa no banco de dados, basta passar um JSON  na
  requisição do tipo POST com chave TEXT e a tarefa a ser cadastrada. O retorno da
  API é conforme a imagem abaixo:

  ![cadastro tarefa](./public/imgs/03-cadstro-tarefa.png)

- Validações:
  - Se for passado campo text vazio:
  ![campo vazio](./public/imgs/04-campo-vazio.png)

  - Se for passado um texto maior que 200 caracteres:
  ![texto maior 200 caracteres](./public/imgs/05-campo-maior-200-caracteres.png)

2. #### `GET` localhost:3000/todo/list
  Este endpoint lista todas as tarefas cadatradas no banco de dados da API.
   ![lista tarefas](./public/imgs/06-listar-tarefas.png)

3. #### `PATCH` localhost:3000/todo/update
  Este endpoint edita uma tarefa conforme o id passado na requisição. Caso a edição 
  acontecer com sucesso o retorno será conforme abaixo:
   ![edit tarefa](./public/imgs/07-editar-tarefa.png)

- Validações:
  - Se for passado campo text vazio:
  ![campo vazio](./public/imgs/08-campo-vazio.png)

  - Se passar um id inexistente:
  ![id que  não existe](./public/imgs/09-task-not-found.png)

  - Se for passado um texto maior que 200 caracteres:
  ![texto maior 200 caracteres](./public/imgs/12-texto-miaor-200-edit-task.png)

4. #### `DELETE` localhost:3000/todo/delete
  Este endpoint deleta uma tarefa do banco de dados a partir de um id passado na requisição,
  caso a deleção acontecer com sucesso, o retorno será conforme abaixo:
  ![deletado com sucesso](./public/imgs/11-deleted.png)

  - Validações:
  - Se for passado id inexistente:
  ![id inexistente](./public/imgs/10-task-not-found-delete.png)


#### Muito obrigado por ler ate aqui, qualquer contribuição será bem vinda! ate a proxima!
