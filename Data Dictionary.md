# Documentation - Modifications des Colonnes

Ce document présente la **modification des colonnes** du dataset utilisé pour le projet.  
Les modifications suivantes permettent de rendre les noms des colonnes plus lisibles et mieux adaptés à une modélisation en étoile.

## Modifications des Colonnes

### 1. Table de faits
| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Order Id                                   | Commande Id                               |
| order date (DateOrders)                    | Date de la commande                       |
| Shipping date (DateOrders)                 | Date de livraison                         |
| Days for shipment (scheduled)              | Délais de livraison théoriques            |
| Days for shipping (real)                   | Délais de livraison réels                 |
| Category Id                                | Catégorie Id                              |
| Department Id                              | Département Id                            |
| Order Item Discount                        | Réduction                                 |
| Order Item Product Price                   | Prix unitaire brut                        |
| Order Item Quantity                        | Quantité                                  |
| Sales                                      | Prix de vente brut                        |
| Order Item Total                           | Prix de vente net                         |
| Order Profit Per Order                     | Profit                                    |

### 2. Table de dimensions
#### a. Table : Clients

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Customer Id                                | Client Id                                 |
| Customer Lname                             | Nom                                       |
| Customer Fname                             | Prénom                                    |
| Customer Street                            | Adresse                                   |
| Customer Zipcode                           | Code postal                               |
| Customer City                              | Ville                                     |
| Customer State                             | État                                      |
| Customer Country                           | Pays                                      |
| Customer Segment                           | Segment                                   |
| Latitude                                   | Latitude                                  |
| Longitude                                  | Longitude                                 |

#### b. Table : Destinataires des commandes

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Market                                     | Marché                                    |
| Order City                                 | Ville dest commande                       |
| Order Region                               | Région dest commande                      |
| Order State                                | État dest commande                        |
| Order Country                              | Pays dest commande                        |

#### c. Table : Produits

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Product Name                               | Nom produit                               |
| Department Name                            | Département produit                       |
| Category Name                              | Catégorie produit                         |

#### d. Table : Etats des livraisons

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Delivery Status                            | Etat de la livraison                      |

#### e. Table : Modes de livraison

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Shipping Mode                              | Mode de livraison                         |

#### f. Table : Etats des commandes

| **Nom d'origine**                          | **Nouveau nom des colonnes**              |
|--------------------------------------------|-------------------------------------------|
| Order Status                               | Etat de la commande                       |



### 3. Données supprimées

| **Nom d'origine**                          | **Cause de la suppression**                     |
|--------------------------------------------|-------------------------------------------------|
| Product Card Id                            | Supprimée - doublon de Order Item Cardprod Id   |
| Product Category Id                        | Supprimée - doublon de Category Id              |
| Product Description                        | Supprimée - vide                                |
| Product Image                              | Supprimée - inutile                             |
| Order Item Id                              | Supprimée - inutile                             |
| Product Price                              | Supprimée - doublon de Order Item Product Price |
| Product Status                             | Supprimée - ne contient que des 0               |
| Late_delivery_risk                         | Supprimée - inutile                             |
| Benefit per order                          | Supprimée - doublon de Order Profit Per Order   |
| Sales per customer                         | Supprimée - doublon de Order Item Total         |
| Order Customer Id                          | Supprimée - doublon de Customer Id              |
| Order Item Cardprod Id                     | Supprimée - inutile                             |
| Customer Email                             | Supprimée - vide                                |
| Customer Password                          | Supprimée - vide                                |
| Order Item Discount Rate                   | Supprimée - inutile                             |
| Order Item Profit Ratio                    | Supprimée - inutile                             |


---

## Conclusion
Les modifications proposées simplifient et rendent les noms des colonnes plus intuitifs, pour une analyse plus fluide. 

Les tables nécessaires pour le modèle en étoile ont été identifiées et seront créées pour optimiser la performance et la structure du modèle Power BI.


