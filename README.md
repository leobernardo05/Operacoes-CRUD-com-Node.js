# CRUD de Pessoas com Node.js e Express

Projeto desenvolvido durante um laboratório prático da [Cognitive Class / IBM Skills Network](https://cognitiveclass.ai/), com o objetivo de implementar uma API REST para o gerenciamento de pessoas utilizando Node.js e Express.

A aplicação permite cadastrar, consultar, atualizar e excluir pessoas, utilizando informações como primeiro nome, sobrenome, e-mail e data de nascimento. O projeto também apresenta um mecanismo de autenticação com sessões e JSON Web Tokens (JWT) para proteger os endpoints.

## Tecnologias utilizadas

- **Node.js** — ambiente de execução JavaScript.
- **Express.js** — criação do servidor e gerenciamento das rotas HTTP.
- **express-session** — gerenciamento de sessões.
- **jsonwebtoken (JWT)** — geração e verificação de tokens de autenticação.
- **cURL e Postman** — ferramentas para testar os endpoints da API.

## Funcionalidades

- Listagem de pessoas cadastradas.
- Busca de uma pessoa pelo e-mail.
- Cadastro de novas pessoas.
- Atualização dos dados de uma pessoa.
- Exclusão de pessoas cadastradas.
- Autenticação de usuários por sessão e JWT.
- Proteção das rotas de gerenciamento de pessoas.

## Estrutura do projeto

```text
App_resenha_livros/
├── routes/
│   └── users.js
├── .gitignore
├── LICENSE
├── README.md
├── index.js
├── index_withauth.js
├── package.json
└── package-lock.json
```

## Como executar o projeto

### Pré-requisitos

- [Node.js](https://nodejs.org/)
- npm, instalado junto com o Node.js.

### 1. Clone o repositório

```bash
git clone https://github.com/leobernardo05/App_resenha_livros.git
```

### 2. Entre na pasta do projeto

```bash
cd App_resenha_livros
```

### 3. Instale as dependências

```bash
npm install
```

### 4. Inicie o servidor

Consulte o arquivo `package.json` para verificar os scripts disponíveis. Caso o arquivo de entrada seja `index.js`, execute:

```bash
node index.js
```

Se estiver utilizando a versão com autenticação, execute o arquivo correspondente:

```bash
node index_withauth.js
```

Por padrão, o servidor está configurado para utilizar a porta `5000`.

## Endpoints da API

Considerando o servidor em execução localmente em `http://localhost:5000`:

| Método | Endpoint | Descrição |
|---|---|---|
| GET | `/user` | Lista as pessoas cadastradas |
| GET | `/user/:email` | Busca pessoas pelo e-mail |
| POST | `/user` | Cadastra uma pessoa |
| PUT | `/user/:email` | Atualiza os dados de uma pessoa |
| DELETE | `/user/:email` | Exclui uma pessoa |
| POST | `/login` | Realiza a autenticação na versão protegida |

### Exemplos de requisições

Consultar uma pessoa:

```bash
curl "http://localhost:5000/user/johnsmith@gmail.com"
```

Cadastrar uma pessoa:

```bash
curl -X POST "http://localhost:5000/user?firstName=Jon&lastName=Lovato&email=jonlovato@theworld.com&DOB=10-10-1995"
```

Atualizar a data de nascimento:

```bash
curl -X PUT "http://localhost:5000/user/johnsmith@gmail.com?DOB=01-01-1971"
```

Excluir uma pessoa:

```bash
curl -X DELETE "http://localhost:5000/user/johnsmith@gmail.com"
```

**Observação:** os exemplos utilizam os parâmetros de consulta (`query parameters`) implementados no laboratório. Na versão protegida, é necessário autenticar-se antes de acessar as rotas de usuários.

## Aprendizados

Durante o desenvolvimento deste laboratório, são praticados conceitos importantes de desenvolvimento backend:

- Criação e organização de rotas HTTP com Express.
- Implementação das operações CRUD.
- Manipulação de dados em memória.
- Utilização de middlewares.
- Autenticação com sessões e JWT.
- Testes de APIs com cURL e Postman.

## Próximas melhorias

- Implementar validação dos dados recebidos.
- Utilizar variáveis de ambiente para configurações sensíveis.
- Melhorar o tratamento de erros e os códigos de status HTTP.
- Armazenar os dados em um banco de dados.
- Reforçar a segurança do mecanismo de autenticação.

## Créditos

Laboratório prático baseado no conteúdo educacional da Cognitive Class / IBM Skills Network. Este repositório tem finalidade de estudo e demonstração de conhecimentos em desenvolvimento backend.
