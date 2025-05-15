

📌 Nome do Projeto
LifeBoard — Gestor de Tarefas e Organização Pessoal

# 📑 Descrição

O LifeBoard é uma aplicação web desenvolvida para auxiliar jovens que moram sozinhos na gestão da rotina doméstica e pessoal. A plataforma permite o cadastro e controle de tarefas, eventos, listas de compras, anotações e planos de refeições, proporcionando organização e praticidade no dia a dia.

# 🖥️ Tecnologias utilizadas

* **Node.js**
* **Express**
* **MySQL**
* **Sequelize (ORM opcional)**
* **JavaScript**
* **HTML & CSS**
* **Postman (testes de API)**
* **VS Code**

# 📂 Estrutura de Pastas

```bash
mvc-boilerplate/
├── assets/
├── config/
├── controllers/
├── documentos/
│   └── wad.md
├── models/
├── routes/
├── scripts/
├── services/
├── tests/
├── views/
├── .env.example
├── .gitignore
├── jest.config.js
├── package.json
├── package-lock.json
├── readme.md
├── rest.http
└── server.js
```

# 🗄️ Modelo Físico do Banco de Dados

### 📊 Diagrama Relacional

![Captura de tela 2025-05-09 084055](https://github.com/user-attachments/assets/b5301736-ccda-42a3-8cdb-b0912ebb293a)

### 📜 Script SQL

```sql
CREATE TABLE users (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(100),
  email VARCHAR(100) UNIQUE,
  password VARCHAR(100)
);

CREATE TABLE events (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  title VARCHAR(100),
  description TEXT,
  date DATE,
  time TIME,
  FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE item_lists (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  item_name VARCHAR(100),
  quantity INT,
  category VARCHAR(50),
  status VARCHAR(20),
  FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE tasks (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  title VARCHAR(100),
  description TEXT,
  date DATE,
  time TIME,
  status VARCHAR(20),
  FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE notes (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  title VARCHAR(100),
  content TEXT,
  category VARCHAR(50),
  FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE meal_plans (
  id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT,
  date DATE,
  meal_type VARCHAR(50),
  description TEXT,
  FOREIGN KEY (user_id) REFERENCES users(id)
);
```

# 📑 Funcionalidades

* 📌 Cadastro e login de usuários
* 📝 Criação e listagem de tarefas diárias com status e horários
* 📅 Cadastro de eventos e compromissos
* 🛒 Gerenciamento de listas de compras e itens faltantes
* 📓 Área de anotações organizadas por categorias
* 🍽️ Planejamento de refeições diárias

# 📮 Rotas da API

| Método | Rota          | Descrição                   |
| :----- | :------------ | :-------------------------- |
| GET    | `/users`      | Listar usuários             |
| POST   | `/users`      | Cadastrar usuário           |
| GET    | `/tasks`      | Listar tarefas              |
| POST   | `/tasks`      | Cadastrar nova tarefa       |
| GET    | `/events`     | Listar eventos              |
| POST   | `/events`     | Cadastrar evento            |
| GET    | `/item_lists` | Listar itens de compra      |
| POST   | `/item_lists` | Adicionar item à lista      |
| GET    | `/notes`      | Listar anotações            |
| POST   | `/notes`      | Criar anotação              |
| GET    | `/meal_plans` | Listar planos de refeição   |
| POST   | `/meal_plans` | Cadastrar plano de refeição |

# 📝 Instruções de Uso

1. Clone o repositório:

   ```bash
   git clone https://github.com/vivianperesinteli/projeto_individual_Mod2.git
   ```
2. Instale as dependências:

   ```bash
   npm install
   ```
3. Configure as variáveis de ambiente no `.env`
4. Execute o projeto:

   ```bash
   node server.js
   ```

# 👥 Autora

**Vivian Peres Inteli**
[GitHub](https://github.com/vivianperesinteli)

