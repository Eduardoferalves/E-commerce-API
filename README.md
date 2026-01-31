# E-commerce API com Flask

Uma API RESTful desenvolvida em Python com o micro-framework Flask para simular as funcionalidades de back-end de um sistema de e-commerce.

## Funcionalidades

- **Autenticação de Usuários:** Sistema de login e logout baseado em sessão para proteger rotas específicas.
- **Gerenciamento de Produtos (CRUD):**
    - Adicionar novos produtos.
    - Visualizar todos os produtos ou detalhes de um produto específico.
    - Atualizar informações de produtos existentes.
    - Deletar produtos.
- **Gerenciamento de Carrinho de Compras:**
    - Adicionar e remover itens do carrinho de um usuário autenticado.
    - Visualizar o conteúdo do carrinho.
    - Realizar um "checkout" para limpar o carrinho.

## Tecnologias Utilizadas

- **Framework:** [Flask](https://flask.palletsprojects.com/)
- **Banco de Dados:** [SQLite](https://www.sqlite.org/index.html) com [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/) (ORM)
- **Autenticação:** [Flask-Login](https://flask-login.readthedocs.io/en/latest/)
- **CORS:** [Flask-Cors](https://flask-cors.readthedocs.io/en/latest/)

## Endpoints da API

Abaixo está a lista de endpoints disponíveis na API.

| Funcionalidade          | Método | Rota                                | Autenticação | Descrição                                        |
| ----------------------- | :----: | ----------------------------------- | :----------: | -------------------------------------------------- |
| **Autenticação**        |        |                                     |              |                                                    |
| Login de Usuário        | `POST` | `/login`                            |     Não      | Autentica um usuário e inicia uma sessão.          |
| Logout de Usuário       | `POST` | `/logout`                           |      Sim     | Desconecta o usuário e encerra a sessão.           |
|                         |        |                                     |              |                                                    |
| **Produtos**            |        |                                     |              |                                                    |
| Listar Produtos         | `GET`  | `/api/products`                     |     Não      | Retorna uma lista de todos os produtos.            |
| Detalhes do Produto     | `GET`  | `/api/products/<int:product_id>`    |     Não      | Retorna os detalhes de um produto específico.      |
| Adicionar Produto       | `POST` | `/api/products/add`                 |      Sim     | Adiciona um novo produto ao banco de dados.        |
| Atualizar Produto       | `PUT`  | `/api/products/update/<int:product_id>` |      Sim     | Atualiza as informações de um produto existente.   |
| Deletar Produto         | `DELETE`| `/api/products/delete/<int:product_id>`|      Sim     | Deleta um produto do banco de dados.               |
|                         |        |                                     |              |                                                    |
| **Carrinho**            |        |                                     |              |                                                    |
| Ver Carrinho            | `GET`  | `/api/cart`                         |      Sim     | Exibe todos os itens no carrinho do usuário.       |
| Adicionar ao Carrinho   | `POST` | `/api/cart/add/<int:product_id>`    |      Sim     | Adiciona um produto ao carrinho do usuário.        |
| Remover do Carrinho     | `DELETE`| `/api/cart/remove/<int:product_id>` |      Sim     | Remove um produto do carrinho do usuário.          |
| Checkout                | `POST` | `/api/cart/checkout`                |      Sim     | Esvazia o carrinho do usuário após a "compra".     |

## Deploy

A API está implantada na AWS (Amazon Web Services) utilizando o serviço Elastic Beanstalk.

---

*Este README foi gerado com base na análise do código-fonte do projeto.*
