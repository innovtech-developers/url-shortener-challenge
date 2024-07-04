# Desafio: Encurtador de URL 🔗
Gratidão pelo interesse em trabalhar conosco! Nesta etapa, será requisitado a criação de uma aplicação para encurtar URLs, com uma API REST e um frontend com o framework de sua preferência, de forma que possamos rastrear a quantidade de cliques na URL.

## Requisitos 📝
Antes de começar, certifique-se de que você possui o **Node.js 20** e o **Docker** instalados em sua máquina. Além disso, é interessante ter conhecimento em **TypeScript**, **Express**, e **MySQL**.

## 1. Configuração Inicial
### 1.1. Inicialize um novo projeto TypeScript
```bash
npm init -y
npm i -D typescript tsx @types/node
npx tsc --init
```
### 1.2. Instale as dependências
```bash
npm i express
npm i -D prisma @types/express
npx prisma init --datasource-provider mysql
```
## 2. Configuração do Banco de Dados
### 2.1. Configure o Docker para o MySQL
Execute o seguinte comando para criar um contêiner Docker com MySQL:

```bash
docker run --name mysql-database -e MYSQL_ROOT_PASSWORD=secret -d -p 3306:3306 mysql:8.0
```
### 2.2. Configure o Prisma
Crie um arquivo prisma/schema.prisma e defina seu modelo de dados, por exemplo:

```prisma
// prisma/schema.prisma

model Url {
  id       String  @id @default(uuid())
  slug     String  @unique
  longUrl  String
  clicks   Int
}
```
Execute os comandos para gerar o código Prisma e criar o banco de dados:

```bash
npx prisma generate
npx prisma migrate dev --name initial
```

## 3. Implementação
Implemente a lógica de validação de URL e registro dos dados no banco através do **Prisma ORM**. Você deve criar seu projeto usando de preferência o paradigma **OO** ou **Funcional**, seguindo os padrões e boas práticas de desenvolvimento.

## 4. Rode
Execute o seguinte comando para iniciar o servidor Express:

```bash
npx tsx index.ts
```

## Avaliação
### O que valorizamos ❤️
- Proficiência em JavaScript
- Método de resolução do problema
- Compreensão do paradigma
- Uso do padrão REST
- Manutenibilidade do código
- Tratamento de erros
- Código limpo e organizado

### O que NÃO será avaliado ❌
- Fluxo de cadastro de usuários
- Autenticação

### Diferenciais 🤓
- Documentação
- Testes unitários e E2E
- Uso de Design Patterns
- Proposta de arquitetura
- Commit semântico
- UX

### Materias úteis 📚
- https://www.redhat.com/pt-br/topics/api/what-is-a-rest-api
- https://hub.packtpub.com/why-we-need-design-patterns/
- https://refactoring.guru/
- https://www.atlassian.com/continuous-delivery/software-testing/types-of-software-testing
- https://danieldcs.com/tratamento-de-erros-e-excecoes-em-javascript/
- https://blog.geekhunter.com.br/o-que-e-commit-e-como-usar-commits-semanticos/
- https://posdigital.pucpr.br/blog/design-de-experiencia-do-usuario