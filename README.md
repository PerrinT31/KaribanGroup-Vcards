# Kariban Digital VCard

> Statut : version actuelle en production  
> Déploiement : Vercel  
> Type : application web statique mobile-first

Application web permettant de générer une carte de visite digitale avec QR code pour les équipes Kariban Group.

L'objectif de l'application est de permettre à un collaborateur de :
- saisir ses informations professionnelles
- générer une carte de visite digitale
- afficher un QR code
- permettre à un client d'enregistrer rapidement un contact
- ajouter un contact conseiller commercial en option

## Fonctionnalités actuelles

- Génération d'une carte de visite digitale
- QR code principal
- QR code conseiller commercial (optionnel)
- Génération d'une vCard côté client
- Téléchargement du QR code en PNG
- Téléchargement du contact en `.vcf`
- Sauvegarde locale via `localStorage`
- Ajout à l'écran d'accueil iPhone
- Interface mobile-first

## Structure fonctionnelle

L'application fonctionne aujourd'hui côté front uniquement, sans base de données centralisée.

### Données gérées
- Contact principal
- Contact conseiller commercial
- Vue active du QR code
- Persistance locale dans le navigateur

### Logique actuelle
- Les données sont saisies dans le formulaire
- Elles sont stockées localement
- Une vCard est générée côté client
- Le QR code encode cette vCard
- Le QR code peut être téléchargé en image PNG
- Le contact peut être téléchargé au format `.vcf`

## Stack technique

- HTML
- CSS
- JavaScript vanilla
- [qrcodejs](https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js)

## Installation

### 1. Cloner le dépôt

```bash
git clone <url-du-repo>
cd <nom-du-repo>
```

### 2. Lancer localement

Comme il s'agit d'une application statique, il suffit d'ouvrir le fichier HTML dans un navigateur ou de lancer un serveur local.

Exemple avec Python :

```bash
python3 -m http.server 8000
```

Puis ouvrir :

```text
http://localhost:8000
```

## Déploiement

Le projet est prévu pour être déployé sur **Vercel**.

### Workflow recommandé
- `main` : production
- branches `feature/...` : développements et tests
- preview deployments via Vercel avant merge vers `main`

## Utilisation

### Carte principale
L'utilisateur saisit :
- prénom
- nom
- poste
- mobile
- fixe
- email
- site web
- adresse

Puis clique sur **Générer ma carte**.

### Conseiller commercial
Un bloc optionnel permet d'ajouter :
- prénom
- nom
- poste
- mobile
- fixe
- email
- site web
- adresse

Si ces données sont renseignées, un second QR code est disponible.

## Limitations actuelles

- Pas de base centralisée
- Pas d'URL stable par commercial
- Pas d'analytics intégrés
- Pas de gestion des droits ou d'administration
- Pas de synchronisation entre appareils
- Les données sont stockées localement sur le device

## Pistes d'évolution

- URLs stables avec identifiant
- Stockage centralisé
- Landing commerciale par commercial
- Analytics / tracking
- Intégration SharePoint ou autre base interne
- Personnalisation des contenus commerciaux
- Version orientée vente plutôt que simple contact

## Bonnes pratiques projet

- Ne pas développer directement sur `main`
- Utiliser une branche dédiée pour chaque évolution
- Tester via preview deployment Vercel avant merge
- Documenter les évolutions structurantes dans ce README

## Auteur / Propriété

Projet développé pour les besoins de **Kariban Group**.

Tous droits réservés.

## Licence

Voir le fichier [LICENSE](./LICENSE).
