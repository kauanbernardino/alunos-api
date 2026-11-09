# API Escola (C# / ASP.NET Core)

API REST em C# para cadastro de alunos e disciplinas, com registro e login de usuários usando JWT. Serve o front-end React do repositório [apicrud](https://github.com/kauanbernardino/apicrud).

## Funcionalidades

- CRUD de **alunos** e **disciplinas** (`GET`, `POST`, `PUT`, `DELETE`)
- **Registro e login** de usuários, com senha criptografada (BCrypt) e token JWT
- Banco **SQLite** com Entity Framework Core e *migrations* (o banco é criado e migrado sozinho ao iniciar)
- Documentação interativa com **Swagger**
- **Dockerfile** para rodar em contêiner

## Rotas

| Método | Rota | Para quê |
|---|---|---|
| POST | `/api/Auth/registrar` | Criar usuário |
| POST | `/api/Auth/login` | Entrar e receber o token |
| GET, POST | `/api/Alunos` | Listar e cadastrar alunos |
| GET, PUT, DELETE | `/api/Alunos/{id}` | Ver, editar e excluir aluno |
| GET, POST | `/api/Disciplinas` | Listar e cadastrar disciplinas |
| GET, PUT, DELETE | `/api/Disciplinas/{id}` | Ver, editar e excluir disciplina |

## Tecnologias

C# · .NET 8 · ASP.NET Core · Entity Framework Core · SQLite · JWT · BCrypt · Swagger · Docker

## Como rodar

Pré-requisito: .NET SDK 8.

```bash
git clone https://github.com/kauanbernardino/WebApplication2.git
cd WebApplication2
dotnet run
```

Abra `/swagger` no endereço que o terminal mostrar para testar as rotas.

Com Docker:

```bash
docker build -t api-escola .
docker run -p 8080:8080 api-escola
```

## Limitações conhecidas

- As rotas de alunos e disciplinas ainda **não exigem login**: o JWT é gerado, mas falta proteger os controllers com `[Authorize]`.
- A chave do JWT está no código e no `appsettings.json`; o ideal é passá-la por variável de ambiente.
- O CORS está aberto para qualquer origem (apenas para desenvolvimento).

## Sobre o projeto

Trabalho da faculdade, desenvolvido com apoio de ferramentas de IA.

## Autor

Kauan Bernardino da Silva
