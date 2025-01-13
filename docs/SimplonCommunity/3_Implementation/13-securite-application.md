# Introduction
Ce document vise à présenter de manière claire et accessible la stratégie globale de sécurisation appliquée aux projets de bots Discord, ainsi qu’à l’API et au tableau de bord associés. Pour garantir une sécurité optimale, nous nous appuyons sur les recommandations de l’ANSSI (Agence Nationale de la Sécurité des Systèmes d’Information), de l’OWASP (Open Web Application Security Project) et des bonnes pratiques issues de MDN Security.

## Défense en profondeur
Le système repose sur plusieurs composants distincts : les bots Discord, l’API, la base de données et le tableau de bord (dashboard). Pour garantir une sécurité robuste, chaque composant sera traité comme un point de contrôle stratégique. Ces points de contrôle joueront un rôle clé dans la détection, le filtrage et la neutralisation des menaces, limitant ainsi leur propagation au sein du système.

## Réduction de la surface d'attaque
Dans le cadre du principe de réduction de la surface d'attaque, nous limiterons l'exposition des points d'entrée au strict minimum nécessaire. Chaque composant disposera de permissions et d'accès restreints, et toutes les fonctionnalités ou services non essentiels au bon fonctionnement du système seront désactivés.

### Exemple
- **Communication dédiée :** Le bot Discord "signature" interagira avec l'API uniquement via des routes spécifiques et isolées du reste du système.
- **Port dédié :** Le bot Discord "signature" utilisera exclusivement le port 5239 pour ses communications.

En complément, l’exposition réseau sera également limitée grâce à l’utilisation d’une liste blanche de ports autorisés. Tous les services inutiles seront désactivés pour réduire les risques d’exploitation (exemple : service FTP).

## RGPD
Pour chaque utilisateur du système, certaines parties interagiront avec des données personnelles telles que le nom, le prénom et l’adresse e-mail. Conformément à la réglementation en vigueur, notamment le RGPD, nous respecterons les directives de la CNIL (Commission Nationale de l'Informatique et des Libertés). Ces mesures garantiront une collecte, un stockage et un traitement des données personnelles dans des conditions sécurisées et transparentes.

### Consentement explicite
Nous demanderons de façon claire et explicite à l'utilisateur son accord pour la collecte et l'utilisation de ses données personnelles.

### Droit de consultation
Nous nous assurerons que l'utilisateur est en mesure de pouvoir consulter les données qui lui sont associées.

### Droit de modification
Nous permettrons à l'utilisateur de pouvoir modifier simplement ses données lorsqu'il le souhaite.

### Droit à l'oubli
Nous permettrons à l'utilisateur de pouvoir supprimer totalement ses informations du système.

### Prévention
En cas de faille dans le système, nous avertirons les utilisateurs que leurs données personnelles ont été compromises.

---

# Back-end

## Introduction

### Politique de moindre privilège
Cette politique a pour objectif de ne donner que les permissions strictement nécessaires aux acteurs et éléments du système pour fonctionner. L'objectif est de limiter le risque de vol, d’altération ou de destruction de données dans le cas de compromission d’un ou plusieurs éléments. Cette politique contribue à la réduction de la surface d'attaque et s'applique au niveau de la base de données ainsi que de l'API.

#### 1. Moindre privilège dans la BDD
Les comptes utilisés pour accéder à la base de données doivent être configurés de manière à limiter les privilèges :
- **Accès rôle spécifique :** Un utilisateur ayant un rôle "lecteur" dans la base de données ne doit avoir que des privilèges en lecture, et non des privilèges en écriture ou en suppression.

#### 2. Moindre privilège dans l'API
Chaque utilisateur doit avoir accès uniquement aux ressources nécessaires pour ses fonctions :
- **Limiter les rôles et permissions :** Par exemple, un utilisateur standard n'a pas besoin d'accéder à des données administratives ou de configurer les paramètres du serveur.
- **Séparer les rôles :** La création de rôles différents, comme "utilisateur", "modérateur", "administrateur", permet de restreindre l'accès aux fonctionnalités spécifiques selon les besoins des utilisateurs.

---

### RBAC
Le **RBAC** (**R**ole **B**ased **A**ccess **C**ontrol) permet de définir les permissions pour chaque rôle. Établir un RBAC assure la bonne distribution des permissions dans l'application et contribue à la mise en place de la politique de moindre privilège.

---

### Journalisation
La **journalisation** consiste à enregistrer des événements et actions importantes afin de faciliter la surveillance, le débogage, la sécurité et la maintenance de l'application. 

#### Objectifs
- Surveiller les actions des utilisateurs.
- Effectuer des audits réguliers.

#### Bonnes pratiques
- Les journaux ne doivent pas contenir d'informations sensibles exploitables.
- Prévention des attaques par déni de service via journaux.

---

## Base de données

### Utilisation des UUID
Un UUID (Universally Unique Identifier) est un identifiant standardisé de 128 bits garantissant l'unicité à l'échelle mondiale.

#### Avantages
- Remplacement des identifiants séquentiels par des identifiants uniques, aléatoires et non prédictibles.
- Prévention des attaques par force brute.

---

### Politique de sauvegarde

#### Règle 3-2-1
1. **Trois copies des données :** Original + 2 copies.
2. **Deux supports différents :** Exemple : disque dur et cloud.
3. **Une copie hors site :** Protéger contre les risques locaux (incendie, vol, etc.).

#### Automatisation
- Sauvegarde quotidienne à 02h00.

#### Politique de rétention
- Conservation maximale : 7 jours (une sauvegarde par jour).

---

# API

## Sécurisation des communications
### TLS
- Utilisation obligatoire de HTTPS.
- Certificat TLS Let’s Encrypt (version TLSv1.3).

### HSTS
- Connexions forcées via HTTPS.
- Durée : 1 an minimum.

---

## Limitation des appels API
- **Quota :** 30 requêtes par minute par utilisateur.
- **Mesure :** Blocage temporaire en cas de dépassement.

---

# Front-end

## Sanitation
- Nettoyage et validation des données entrantes via REGEX.

---

## Sécurisation des communications
### HTTPS
- Utilisation obligatoire avec HSTS et TLS.

### CORS
- Définir explicitement les origines autorisées.

### Content Security Policy (CSP)
- Prévention des attaques XSS.

---

## Gestion des messages d'erreur
- Messages génériques côté utilisateur.
- Logs détaillés côté serveur.

---

## Web Storage
### Local Storage
- Ne pas y stocker d'informations sensibles.

### Session Storage
- Utilisation limitée et sécurisée.

