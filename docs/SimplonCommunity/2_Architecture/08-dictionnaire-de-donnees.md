## Table : Users

| **Column Name**      | **Type**  | **Size** | **Description**                                  |
|----------------------|-----------|----------|--------------------------------------------------|
| user_uuid            | UUID      |          | Identifiant unique de l'utilisateur.             |
| user_pseudo          | VARCHAR   | 255      | Pseudonyme ou nom d'affichage de l'utilisateur.  |
| role_id              | NUMBER    |          | Identifiant du rôle attribué à l'utilisateur.    |
| role_name            | VARCHAR   | 100      | Nom descriptif du rôle attribué à l'utilisateur. |
| user_xp              | NUMBER    |          | Points d'expérience accumulés par l'utilisateur. |
| user_level           | NUMBER    |          | Niveau de l'utilisateur.                         |
| user_badges          | VARCHAR[] |          | Liste des badges obtenus par l'utilisateur.      |
| report_count         | VARCHAR   |          | Nombre de signalements reçus.                    |
| user_ranking         | NUMBER    |          | Classement de l'utilisateur.                     |

---

## Table : Resources

| **Column Name**            | **Type**   | **Size** | **Description**                                       |
|----------------------------|------------|----------|-------------------------------------------------------|
| resource_title             | VARCHAR    | 255      | Titre de la ressource.                                |
| resource_description       | TEXT       |          | Description détaillée de la ressource.                |
| resource_tags              | VARCHAR[]  |          | Liste des tags associés à la ressource.               |
| resource_content           | TEXT       |          | Contenu de la ressource (URL, fichier, etc.).         |
| resource_status            | VARCHAR    | 50       | Statut de la ressource (actif, obsolète).             |
| resource_creator           | UUID       |          | Identifiant de l'utilisateur ayant créé la ressource. |
| resource_creation_date     | TIMESTAMPZ |          | Date et heure de création de la ressource.            |
| resource_modification_date | TIMESTAMPZ |          | Date et heure de la dernière modification.            |
| resource_reports           | NUMBER     |          | Nombre de signalements reçus par la ressource.        |
| useful_votes               | NUMBER     |          | Nombre de votes utiles.                               |
| useless_votes              | NUMBER     |          | Nombre de votes inutiles.                             |

---

## Table : Reports

| **Column Name**       | **Type**   | **Size** | **Description**                                         |
|------------------------|------------|----------|---------------------------------------------------------|
| report_uuid            | UUID       |          | Identifiant unique du signalement.                      |
| report_category        | VARCHAR    | 100      | Catégorie du signalement (contenu illégal, spam, etc.). |
| report_reason          | TEXT       |          | Raison détaillée du signalement.                        |
| report_status          | VARCHAR    | 50       | Statut du signalement (en attente, validé, rejeté).     |
| report_creator         | UUID       |          | Identifiant de l'utilisateur ayant créé le signalement. |
| reported_resource      | UUID       |          | Identifiant de la ressource signalée.                   |
| report_date            | TIMESTAMPZ |          | Date et heure de création du signalement.               |
| report_moderator       | UUID       |          | Modérateur qui a pris en charge le signalement.         |

---

## Table : Event History

| **Column Name**       | **Type**   | **Size** | **Description**                                         |
|-----------------------|------------|----------|---------------------------------------------------------|
| event_uuid            | UUID       |          | Identifiant unique de l’événement.                      |
| event_type            | VARCHAR    | 50       | Type d'événement (création, modification, suppression). |
| event_user            | UUID       |          | Identifiant de l'utilisateur lié à l’événement.         |
| event_resource        | UUID       |          | Identifiant de la ressource liée à l’événement.         |
| event_date            | TIMESTAMPZ |          | Date et heure de l’événement.                           |
| event_details         | JSON       |          | Détails spécifiques de l’événement (champs modifiés).   |

---

## Table : Blacklist

| **Column Name**         | **Type**   | **Size** | **Description**                                     |
|-------------------------|------------|----------|-----------------------------------------------------|
| blacklist_value         | VARCHAR    | 255      | Mot-clé, lien ou expression bloquée.                |
| blacklist_creation_date | TIMESTAMPZ |          | Date d'ajout de l'entrée dans la liste noire.       |

---

## Table : XP and Rewards

| **Column Name**       | **Type**   | **Size** | **Description**                                           |
|-----------------------|------------|----------|-----------------------------------------------------------|
| reward_user           | UUID       |          | Identifiant de l'utilisateur ayant reçu/perdu des points. |
| reward_value          | NUMBER     |          | Valeur de l'XP gagnée ou perdue.                          |
| reward_date           | TIMESTAMPZ |          | Date et heure d'attribution de la récompense/pénalité.    |
