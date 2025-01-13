
# Exigences du Bot Discord Simplon HDF

## Introduction

Notre objectif ? Faciliter la communication, le partage de ressources et l'engagement au sein de cette communauté d'apprenants, de formateurs et d'anciens élèves. Grâce à ce bot, nous souhaitons créer un espace dynamique, interactif et convivial où chacun peut contribuer et s'épanouir.

Découvrons ensemble les **exigences** qui feront de ce bot un outil indispensable pour tous ! 🚀

---

## Exigences Fonctionnelles ⚙️

### 1. Gestion des Ressources 📚

| ID  | Exigence                 | Description                                                                                                                                                                                                                                                                                 |
|-----|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F1  | **Partage de Ressources**    | - Les utilisateurs peuvent partager des liens, articles ou documents utiles dans des canaux dédiés.<br>- Permettre le partage de ressources à travers différentes promotions et formations, accessibles à tous, y compris les anciens apprenants.                                                                            |
| F2  | **Classification par Tags**  | - Utiliser des tags pour catégoriser les ressources (ex : #développement-web, #cybersécurité, #data).<br>- Possibilité d'attribuer plusieurs tags pour une classification précise.                                                                                                       |
| F3  | **Recherche de Ressources**  | - Offrir des commandes ou interfaces pour rechercher des ressources par tags ou mots-clés.<br>- Filtrer les résultats par pertinence ou popularité.                                                                                                                                      |
| F4  | **Gestion des Doublons**     | - Détecter automatiquement les ressources en doublon (mêmes liens ou contenus similaires).<br>- Si un doublon est détecté, conserver la publication avec la description la plus complète ou la meilleure notation.<br>- Transférer les points du post supprimé vers la publication conservée. |

### 2. Conformité Réglementaire et Sécurité 🔒

| ID   | Exigence                     | Description                                                                                                                                                                                                                                                 |
|------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F5   | **Conformité au RGPD**           | Respecter le Règlement Général sur la Protection des Données (RGPD), garantissant à chaque utilisateur le contrôle de ses données personnelles.                                                                                                            |
| F6   | **Sécurité des Données**         | Assurer la sécurité des données collectées, en évitant tout accès non autorisé ou fuite d'informations.                                                                                                                                                    |
| F7   | **Modération Automatisée**       | Intégrer des mécanismes pour détecter et supprimer les contenus inappropriés (liens vers des sites inappropriés, contenus offensants), tout en permettant aux utilisateurs de signaler les messages problématiques.                                       |

### 3. Performance et Fiabilité ⚙️

| ID   | Exigence        | Description                                                                                                                                                                  |
|------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F8   | **Disponibilité**   | Le bot doit être opérationnel 24h/24 et 7j/7 pour une expérience utilisateur optimale.                                                                                    |
| F9   | **Scalabilité**     | Capable de gérer une augmentation du nombre d'utilisateurs sans perdre en performance.                                                                                     |
| F10  | **Robustesse**      | Gérer les erreurs et exceptions sans interruption du service.                                                                                                             |

### 4. Expérience Utilisateur 🎨

| ID   | Exigence            | Description                                                                                                                                                                                  |
|------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F11  | **Interface Intuitive** | Proposer des interactions simples et conviviales, privilégiant les boutons, menus et réactions plutôt que des commandes complexes.                                                         |
| F12  | **Accessibilité**       | Accessible à tous les utilisateurs, y compris ceux ayant des limitations techniques ou des handicaps.                                                                                      |
| F13  | **Multilinguisme**      | Prévoir la possibilité de gérer plusieurs langues si nécessaire, bien que la communauté soit principalement francophone.                                                                  |

### 5. Gamification et Engagement 🏆

| ID  | Exigence                      | Description                                                                                                                                                                                                                                            |
|-----|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F14  | **Système de Notation**           | - Les utilisateurs peuvent évaluer les ressources via des réactions (👍 ou 👎).<br>- Le nombre de "likes" influence la réputation de l'utilisateur et la visibilité de la ressource.                                                                 |
| F15  | **Système de Points et Récompenses** | - Accumuler des points en fonction des "likes" reçus.<br>- Définir des paliers de niveaux avec des récompenses spécifiques (rôles spéciaux, accès exclusifs, badges, etc.).<br>- Notifier les utilisateurs lors de leur progression.                   |
| F16  | **Classements et Statistiques**      | - Afficher les classements des utilisateurs les plus actifs ou les mieux notés.<br>- Fournir des statistiques sur les ressources les plus populaires.                                                                                                  |

### 6. Modération et Sécurité 🛡️

| ID   | Exigence                           | Description                                                                                                                                                                                                                                                                                                                                                                  |
|------|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F17  | **Détection de Contenu Inapproprié**   | - Surveiller les messages pour détecter et supprimer automatiquement les contenus inappropriés (spam, liens malveillants, contenu offensant).                                                                                                                                                                                                                               |
| F18  | **Surveillance des Modifications de Messages** | - Détecter les modifications apportées aux messages par les utilisateurs.<br>- Si un message modifié contient du contenu inapproprié (ex : liens inappropriés), prendre les mesures appropriées (suppression, notification des modérateurs, etc.).<br>- Prévenir les abus tels que la modification d'une ressource acceptable en contenu interdit. |
| F19  | **Signalement par les Utilisateurs**   | - Permettre aux utilisateurs de signaler des messages problématiques via une action dédiée (ex : `!report`).<br>- Notifier les modérateurs pour une action rapide.                                                                                                                              |
| F20  | **Gestion des Sanctions**              | - Appliquer des sanctions en cas de non-respect des règles (avertissements, mute, bannissement temporaire ou permanent).                                                                                                                                                                                                                |
| F21  | **Affichage des Règles**               | - Le bot doit pouvoir afficher les règles de bonne conduite sur demande ou lors de l'arrivée de nouveaux membres.                                                                                                                                                                                                                       |

### 7. Interaction Utilisateur 💬

| ID  | Exigence            | Description                                                                                                                                                                                                                             |
|-----|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F22 | **Interface Intuitive** | - Utiliser des boutons, menus interactifs et réactions pour faciliter l'interaction avec le bot.<br>- Éviter les commandes complexes, favoriser les interactions simples et guidées.                                                 |

### 8. Administration 🔑

| ID  | Exigence                             | Description                                                                                                                                                                                                                                     |
|-----|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F23 | **Commandes Avancées pour les Administrateurs** | - Fournir des commandes spécifiques pour gérer les utilisateurs, les ressources et configurer le bot.                                                                                                                                             |
| F24 | **Personnalisation des Paramètres**      | - Permettre la personnalisation des paramètres via le panel d'administration ou des commandes (niveaux, récompenses, messages automatiques).                                                                                                       |
| F25 | **Gestion des Rôles et Permissions**     | - Contrôler l'attribution automatique des rôles en fonction des niveaux ou actions des utilisateurs.<br>- Configurer les permissions associées à chaque rôle.                                                                                       |
| F26 | **Logs d'Activité**                      | - Accéder aux logs détaillés pour surveiller les interactions et identifier les problèmes éventuels.                                                                                                                                             |

### 9. Gestion Multicanale 🌐

| ID  | Exigence                        | Description                                                                                                                                                                                                                             |
|-----|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| F27 | **Support de Multiples Canaux**     | - Le bot doit fonctionner sur plusieurs canaux dédiés à différentes promotions, formations ou thématiques.                                                                                                                              |
| F28 | **Accès pour les Anciens Apprenants** | - Les anciens apprenants doivent pouvoir accéder aux ressources et continuer à participer à la communauté.                                                                                                                               |
| F29 | **Notifications Transversales**     | - Possibilité d'envoyer des annonces ou notifications à tous les canaux ou groupes spécifiques.                                                                                                                                          |
## Exigences Non Fonctionnelles 🌟

### 1. Maintenabilité et Évolutivité 🔧

| ID    | Exigence                     | Description                                                                                                                                                                                         |
|-------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NF1  | **Code Propre et Documenté**     | Un code bien structuré et commenté pour faciliter la maintenance et les futures évolutions.                                                                                                          |
| NF2  | **Architecture Modulaire**       | Une conception modulaire permettant d'ajouter ou modifier des fonctionnalités sans impacter le reste du système.                                                                                     |
| NF3  | **Choix Technologique Approprié** | Justifier les choix technologiques avec une comparaison objective des options disponibles.                                                                                                           |
---
