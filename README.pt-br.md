<h1 align="center" style="color:#0091EA; font-weight:bold;">
     <img 
    src="https://user-images.githubusercontent.com/42190754/115914607-8cb1df80-a448-11eb-9ac2-75118d5ce63a.png"
    float="center"
    width="100" height="100"
    />
    <br/>
  <a href="#"> Chatty </a>
</h1>

<p align="center">
 <a href="#ℹ%EF%B8%8F-sobre-o-projeto">Sobre</a> •
 <a href="#-tecnologias">Tecnologias</a> •
 <a href="#-como-executar-o-projeto">Como executar</a> •
 <a href="#ℹ%EF%B8%8F-endpoints">Endpoints</a> •
 <a href="#-documentação-API">Documentação</a> •
 <a href="#-autores">Autores</a> •
 <a href="#-licença">Licença</a>
</p>

## ℹ️ Sobre o projeto

Chat com [Socket.IO](https://socket.io/) criado na [RocketSeat](https://rocketseat.com.br/) Next Level Week 5.0, usando TypeScript com Node.js.

---

## 🛠 Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

- **[Node.js](https://nodejs.org/en/)**
- **[Express](https://expressjs.com/)**
- **[TypeORM](https://www.npmjs.com/package/typeorm)**
- **[Sqlite3](https://www.npmjs.com/package/sqlite3)**
- **[Metadata Reflection API](https://www.npmjs.com/package/reflect-metadata)**
- **[uuid](https://www.npmjs.com/package/uuid)**
- **[socket.io](https://www.npmjs.com/package/socket.io)**
- **[socket.io-client](https://www.npmjs.com/package/socket.io-client)**
- **[Embedded JavaScript templates](https://www.npmjs.com/package/ejs)**

---

## 🚀 Como executar o projeto

### 👉 Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas: [Git](https://git-scm.com), [Node.js](https://nodejs.org/en/) and [Yarn](https://yarnpkg.com/). Além disto é bom ter um editor para trabalhar com o código como [VSCode](https://code.visualstudio.com/).

#### 🏁 Começar

```bash
# Clone este repositório
$ git clone https://github.com/BiaChacon/chatty.git

# Acesse a pasta do projeto no terminal/cmd
$ cd chatty
```

#### 🎲 Executando o servidor

```bash
# Vá para a pasta da api
$ cd api

# Instale as dependências
$ npm install

# Criar migrations
$ yarn typeorm migration:run

# Execute a aplicação
$ yarn dev

# O servidor iniciará na porta:3333 - acesse http://localhost:3333

```

---

## 🖥️ Endpoints

### 💠 Para acessar o chat do admin vá para 👉 http://localhost:3333/pages/admin

### 💠 Para acessar o chat do cliente vá para 👉 http://localhost:3333/pages/client

---

## 🗎 Documentação API

<details>
  <summary>Configurações</summary>

### 📍 Criar Configuração [/settings] [POST]

#### **Request**

- Body

```bash
{
    "chat": "true",
    "username": "admin"
}
```

#### **Response 201 (application/json)**

```bash
[
  {
    "id": "admin_id",
    "username": "admin",
    "chat": "true",
    "updated_at": "2021-04-22T19:22:37.000Z",
    "created_at": "2021-04-22T19:22:37.000Z"
}
]
```

### 📍 Atualizar Configuração [/settings/admin] [PUT]

#### **Request**

- Body

```bash
{
    "chat": "false"
}
```

#### **Response 201**

 </details>

<details>
  <summary>Usuário</summary>

### 📍Criar Usuário [/users] [POST]

#### **Request**

- Body

```bash
{
    "email": "example@email.com"
}
```

#### **Response 201 (application/json)**

```bash
[
 {
    "id": "user_id",
    "email": "example@email.com",
    "created_at": "2021-04-22T19:37:24.000Z"
}
]
```

 </details>

<details>
  <summary>Mensagem</summary>

### 📍Enviar Mensagem [/messages] [POST]

#### **Request**

- Body

```bash
{
    "user_id": "user_id",
    "text": "message"
}
```

#### **Response 201 (application/json)**

```bash
[
  {
    "id": "message_id",
    "text": "message",
    "user_id": "user_id",
    "created_at": "2021-04-23T19:40:02.000Z"
  }
]
```

### 📍Listar mensagens de um usuário [/messages/:user_id] [GET]

#### **Response 201 (application/json)**

```bash
[
  {
    "id": "message_id",
    "admin_id": "admin_id",
    "text": "message",
    "user_id": "user_id",
    "created_at": "2021-04-22T19:40:02.000Z",
    "user": {
      "id": "user_id",
      "email": "example@email.com",
      "created_at": "2021-04-22T19:37:24.000Z"
    }
  }
]
```

</details>

---

## 👩🏽‍💻 Autores

<table>
  <tr>
    <td align="center"><a href="https://github.com/biachacon"><img src="https://avatars1.githubusercontent.com/u/42190754?s=460&u=a5cbe42a4868b2bac9615226044b9cec15cee418&v=4" width="100px;" alt=""/><br /><sub><b>Bia Chacon</b></sub></a><br /><a href="https://github.com/BiaChacon/chatty" title="Code">💻</a></td>
  <tr>
</table>

---

## 📝 Licença

Este projeto está sob o MIT. Veja aqui [LICENSE](https://github.com/BiaChacon/chatty/blob/main/LICENSE) para mais informações.

---

## Versões do README

[Inglês 🇺🇸](./README.md) | [Português 🇧🇷](./README.pt-br.md)
