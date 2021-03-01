# Rocketpay

> For learning purposes only.

API for payment and transactions between users developed in Rocketseat's Next Level Week #4 (Elixir).

## Prerequisites

  - [Elixir](https://elixir-lang.org/)
  - [PostgreSQL](https://www.postgresql.org/)
  - [Phoenix](https://www.phoenixframework.org/)
  - [Ecto](https://hexdocs.pm/ecto/Ecto.html)

## Get Started

To start your Phoenix server:

  * Install dependencies with `mix deps.get`
  * Create and migrate your database with `mix ecto.setup`
  * Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check out the deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Endpoints

These are the endpoits available for this project:

| Method  | Endpoint                      | Body (JSON)                 | Response                        | 
|---------|-------------------------------|-----------------------------|---------------------------------|
| GET     | /api                          | No body                     | A text welcome message          |
| POST    | /api/users                    | [User](#user)               | User + Account data             |
| POST    | /api/accounts/<:id>/deposit   | [Value](#value)             | User + Account data             |
| POST    | /api/accounts/<:id>/withdraw  | [Value](#value)             | User + Account data             |
| POST    | /api/accounts/transaction     | [Transaction](#transaction) | User Account + Receiver Account |

### Data Definition

Details about data format to be sent in the body of the above requests.

#### User

| Key       | Value Type  | Description                                           | Example               |
|-----------|-------------|-------------------------------------------------------|-----------------------|
| name      | string      | User's name                                           | `"Lucas"`             |
| age       | integer     | User's age. Must be greater than 18                   | `25`                  |
| email     | string      | User's e-mail. Must a valid e-mail                    | `"lucas@example.com"` |
| password  | string      | Secret password to login. Must be 6+ characters long  | `"P@s5w0rD"`          |
| nickname  | string      | User's nickname. Must be unique                       | `"lucasm"`            |

#### Value

| Key       | Value Type  | Description                             | Example   |
|-----------|-------------|-----------------------------------------|-----------|
| value     | string      | Monetary value. Must be a decimal value | `"31.00"` |

#### Transaction

| Key       | Value Type  | Description                             | Example   | 
|-----------|-------------|-----------------------------------------|-----------|
| value     | string      | Monetary value. Must be a decimal value | `"31.00"` |
| to        | string      | The payee's ID                          | -         |
| from      | string      | User's ID (who is giving money)         | -         |

## Learn more

  * Official website: https://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Forum: https://elixirforum.com/c/phoenix-forum
  * Source: https://github.com/phoenixframework/phoenix
