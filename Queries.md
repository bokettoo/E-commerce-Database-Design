# SQLBook: Code
## 1 Create a "clients" table
  CREATE TABLE clients(
      id_client INT,
      nom VARCHAR(100),
      prenom VARCHAR(100),
      email VARCHAR(125),
      adresse VARCHAR(225),
      telephone INT,
      PRIMARY KEY (id_client)
  );

## 2 Create a "produits" table
  CREATE TABLE produits(
      id_produit INT,
      nom VARCHAR(100),
      description VARCHAR(255),
      prix DECIMAL(12,2),
      stock INT,
      PRIMARY KEY(id_produit)
  );

## 3 Create a "commandes" table
  CREATE TABLE commandes(
      id_commande INT,
      id_client INT,
      date_commande DATE,
      statut VARCHAR(10),
      total DECIMAL(10,2),
      PRIMARY KEY(id_commande),
      FOREIGN KEY (id_client) REFERENCES clients(id_client)
  );

## 4 Add a CHECK constraint on the "statut" field of the "commandes" table to ensure that only the values "in progress", "delivered", or "canceled" are allowed.
  ALTER TABLE commandes
  ADD CONSTRAINT check_statut CHECK (statut IN ('en cours','livrée','annulée'));

## 5 Set a default value for the "statut" field of the "commandes" table to "in progress"
  ALTER TABLE commandes
  MODIFY COLUMN statut VARCHAR(10) DEFAULT 'en cours';
