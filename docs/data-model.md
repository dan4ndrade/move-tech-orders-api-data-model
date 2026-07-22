# Modelagem de Dados

## Entidades

### Pedido (orders)

| Coluna     | Tipo      | Descrição                                    |
|------------|-----------|----------------------------------------------|
| id         | INTEGER   | Identificador único, gerado automaticamente  |
| customer   | TEXT      | Nome do cliente                              |
| status     | TEXT      | Estado do pedido (ex.: pending, completed)   |
| created_at | TIMESTAMP | Data e hora de criação, automática           |

### Item (items)

| Coluna      | Tipo    | Descrição                            |
|-------------|---------|--------------------------------------|
| id          | INTEGER | Identificador único, gerado auto.    |
| order_id    | INTEGER | Chave estrangeira → orders(id)       |
| sku         | TEXT    | Código do item                       |
| description | TEXT    | Descrição do item                    |
| quantity    | INTEGER | Quantidade                           |

## Relacionamento

O pedido (orders) tem vários items (items). O relacionamento e 1:N.
A tabela items tem o atributo order_id que é um FK para o a PK id da tabela orders.
Se apagar um registro na tabela orders, todos os registros de items relacionados ao pedido são deletados também.