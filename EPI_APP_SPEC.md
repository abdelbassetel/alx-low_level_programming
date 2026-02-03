# Application de gestion des EPI (Équipements de Protection Individuelle)

## Objectif
Mettre en place une application interne qui permet de suivre les EPI de l’entreprise (stocks, affectations, renouvellements, conformité et traçabilité), afin d’améliorer la sécurité et réduire les ruptures de stock.

## Périmètre (MVP)
- **Gestion des employés** : fiche collaborateur (nom, service, poste, site).
- **Catalogue EPI** : type d’EPI, norme, taille, durée de vie, fournisseur.
- **Stock** : quantités par site, alertes de seuil minimal.
- **Affectations** : attribution d’un EPI à un employé avec date, état et date de renouvellement.
- **Historique & traçabilité** : journal des entrées/sorties et des renouvellements.
- **Notifications** : alertes pour renouvellement, expiration, stock bas.

## Utilisateurs & rôles
- **Administrateur** : paramétrage global, gestion des utilisateurs.
- **Responsable HSE** : suivi des normes, audits, rapports.
- **Magasinier** : gestion du stock, réception et sortie.
- **Chef d’équipe** : affectation et validation des EPI pour son équipe.
- **Employé** : visualisation de ses EPI attribués.

## Flux principaux
1. **Création catalogue EPI** (type, norme, durée de vie).
2. **Réception stock** (entrée de lot, quantité, fournisseur).
3. **Affectation** à un employé (date, taille, état).
4. **Renouvellement** (mise au rebut/retour + nouvelle attribution).
5. **Alertes** (stock bas, expiration, contrôle périodique).

## Données minimales (modèle simplifié)
- **Employé** : id, nom, prénom, service, poste, site, actif.
- **EPI** : id, type, norme, taille, durée_vie_mois, fournisseur.
- **Stock** : id, epi_id, site, quantite, seuil_min.
- **Affectation** : id, employe_id, epi_id, date_attribution, date_renouvellement, etat.
- **Mouvement** : id, epi_id, type (entrée/sortie), quantite, date, reference.

## Rapports utiles
- **EPI expirés/à renouveler** par site ou service.
- **Historique des affectations** par employé.
- **Rotation du stock** par type d’EPI.

## Contraintes & conformité
- Respect des normes EPI (EN/ISO selon le type).
- Traçabilité des affectations (audit HSE).
- Conservation des historiques (durée définie par politique interne).

## Prochaine étape (conseillée)
- Valider le périmètre du MVP avec les parties prenantes.
- Définir un cahier des charges fonctionnel détaillé.
- Choisir la stack technique (ex: web app + base de données).
- Prototyper un écran de gestion des stocks et des affectations.
