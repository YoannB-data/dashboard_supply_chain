# Analyse Supply Chain & Impact financier – Power BI
# A. Contexte du projet

Ce projet vise à mettre en place un tableau de bord interactif Power BI pour analyser la performance globale de la Supply Chain, identifier les retards, les inefficacités et mesurer l’impact financier, afin d’optimiser les processus de livraison et d’améliorer la satisfaction client.

Axes d'analyse :
* Identifier les inefficiences et goulots d’étranglement dans la chaîne logistique
* Mesurer la performance des livraisons (OTD, délais, retards)
* Classer les produits avec la méthode ABC pour optimiser les efforts commerciaux et logistiques
* Suivre la rentabilité par segment client, région et produit

Le tableau de bord interactif est publié ici :

📂 **[Accéder au rapport Power BI](https://app.powerbi.com/view?r=eyJrIjoiNDQ0MWVkZmYtNmQ2OC00MThiLWE3ODQtNTQ2MGUyNjI0ZTY3IiwidCI6IjQ4M2QxZjAzLWIwNTgtNDA3Mi05YjRmLTA2NzY5NzA5MTkxMCJ9&pageName=5f046aae45f25f0c8c4a
)**


# B. Données

* **Source :** [Kaggle – DataCo Smart Supply Chain](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis/data)
* **Volume :** ~180 000 lignes
* **Granularité :** niveau transactionnel (commande, produit, expédition)
* **Champs clés :**
  * Statut de commande (Complete, Pending, Canceled, Processing…)
  * Délais réels et planifiés, risque de retard (Late delivery risk)
  * Hiérarchie produit (département, nom produit, catégorie)
  * Segments clients et marchés géographiques
  * Modes de livraison (Standard, Second Class, Same Day…)

# C. Analyse des données
## Aperçu des résultats

* Ce projet Power BI analyse 180 000 transactions de Supply Chain et de ventes mondiales.
* Il met en évidence une faible performance logistique (OTD = 44 %) et une forte dépendance aux produits de la catégorie Fan Shop (47% des ventes).
* Les recommandations portent sur la sécurisation des flux logistiques critiques, la rationalisation du portefeuille produit et le développement du segment Corporate.
* Le tableau de bord interactif permet un pilotage clair et en temps réel des performances financières et opérationnelles.

## Analyse des dashboards

### 1. Dashboard Logistique
* Données présentées :
  * Les KPI de tête (Ventes, Profits, Commandes, OTD, Délais de livraison) donnent une vue synthétique
  * La courbe commandes par mois et la prévision donnent une lecture claire de la tendance
  * La vue par classe ABC permet d’évaluer l’importance logistique des produits stratégiques
  * Les analyses par provenance (régions) et par segments clients montrent où sont les marchés clés
  * Le graphe modes de livraison et OTD permet un lien direct entre choix logistique et fiabilité
* Points d’attention :
  * L’OTD global (44%) est catastrophique : plus de la moitié des livraisons sont en retard
  * Les délais de livraison sont relativement stables (~3,5 jours), mais la fiabilité (OTD) est trop basse
  * En Standard Class (mode le plus utilisé), seulement 62% OTD, il y a un gros levier d’amélioration
  * Le segment Consumer domine en volume, mais le Corporate a un potentiel de marge plus élevé 
  * Certaines régions (Europe, Pacific Asia, LATAM) génèrent beaucoup de commandes, il est donc besoin d’optimiser la supply chain internationale

#### Conclusion logistique :
Le principal problème de l’entreprise est la fiabilité des livraisons. Même si les délais moyens sont corrects, l’irrégularité (retards fréquents) impacte l’OTD et donc la satisfaction client. Cela peut expliquer en partie la chute des ventes et des profits.

### 2. Dashboard Financier
* Données présentées :
  * La prévision de ventes par mois permet de voir la tendance et l’anticipation
  * La carte par État relie les ventes/performance géographique
  * La vue par classe ABC est une aide pour prioriser les références qui génèrent le plus de valeur
  * Le graphe Top 3 départements montre la concentration du CA
* Points d’attention :
  * Le chiffre d’affaires actuel ($331K) est en forte baisse par rapport à l'année précédente ($1,03M), avec une perte d’environ -68%
  * Les profits chutent aussi fortement ($33K vs $115K), signe que la rentabilité suit la tendance du CA
  * La dépendance au Fan Shop est très marquée (plus de la moitié du CA et de la marge), il y a donc un risque de concentration

#### Conclusion financière :
La performance dépend de quelques produits/segments (Fan Shop, catégorie A). Cela rend la supply chain vulnérable, il est donc nécessaire de diversifier et d’améliorer la fiabilité logistique.

## Recommandations
1.	Améliorer l’OTD : revoir les process avec les transporteurs, fiabiliser le traitement des commandes (prioriser Standard Class)
2.	Diversifier le portefeuille produit : trop de dépendance à quelques produits de classe A
3.	Focaliser sur les marchés clés : Europe et Asie génèrent beaucoup de commandes, il peut être intéressant d’investir dans les hubs régionaux
4.	Segmentation clients : mettre en place un service premium pour Corporate/Home Office afin de sécuriser les ventes B2B
5.	Mettre en place un suivi hebdo OTD pour détecter rapidement les retards et déclencher des actions correctives

# D. Problèmes rencontrés

À partir d’octobre, les ventes des produits classés A et B chutent brutalement à zéro, ce qui est hautement improbable dans un contexte business réel.

## Hypothèses envisagées

1. Problème technique : pipeline de données cassé ou champs non alimentés

2. Problème métier : arrêt volontaire de la gamme ou changement de stratégie commerciale

## Démarches possibles

1. Vérifier avec les Data Engineers les logs ETL et de la bonne complétude des tables sources

2. Valider avec les équipes Marketing un éventuel arrêt des produits des classes A et B ou un changement de stratégie.

## Solution retenue

Privilégier l’approche Data Engineers d’abord, car une coupure nette et totale des ventes est certainement dû à une erreur technique plutôt qu'à un choix business (d'autant que l'on parle des produits qui représentaient 80% des ventes).

Si l’intégrité des données est confirmée, escalader vers le Marketing pour valider le phénomène.
