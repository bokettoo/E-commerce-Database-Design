# Online Sales Database

This repository contains the structure of a database designed for an online sales company. The database manages clients, orders, and products. Below are the specifications for creating the database tables:

## Tables

### 1. Clients Table

- This table stores information about the clients of the company.
- Fields included:
  - `id_client` (Primary Key)
  - `nom` (Last Name)
  - `prenom` (First Name)
  - `email`
  - `telephone`

### 2. Products Table

- This table contains details about the products sold by the company.
- Fields included:
  - `id_produit` (Primary Key)
  - `nom` (Name)
  - `description`
  - `prix` (Price)
  - `stock`

### 3. Orders Table

- This table records the orders placed by clients.
- Fields included:
  - `id_commande` (Primary Key)
  - `id_client` (Foreign Key referencing the `clients` table)
  - `date_commande` (Order Date)
  - `statut` (Status: in progress, delivered, canceled)
  - `total` (Total Order Amount)

## Constraints

4. **CHECK Constraint on the `statut` field of the `orders` table**:
   - A CHECK constraint is added to ensure that only the values "in progress", "delivered", or "canceled" are allowed for the order status.

## Default Value

5. **Default Value for the `statut` field of the `orders` table**:
   - The default value is set to "in progress" for the `statut` field of the `orders` table.

These specifications aim to create a consistent and well-organized database structure that allows the company to efficiently manage its online sales operations by tracking clients, products, and orders.
