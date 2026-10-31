# Projet BI – Enquêtes de satisfaction de fin de module

## 1. Présentation du projet

Ce projet vise à mettre en place un dispositif structuré d’enquêtes de satisfaction auprès des étudiants inscrits dans les cursus longs du Groupe C&D.

L’objectif est de mesurer la satisfaction des étudiants à l’issue de chaque module de formation, de suivre la qualité des enseignements et d’identifier les points forts ainsi que les axes d’amélioration.

La solution s’appuie sur des processus automatisés de collecte et de traitement des réponses, ainsi que sur des tableaux de bord interactifs développés avec Power BI.

## 2. Objectifs métier

| ID | Objectif | Indicateur de succès | Cible |
|---|---|---|---|
| O1 | Concevoir les formulaires d’enquête selon les axes d’analyse définis. | Formulaires validés et disponibles | 100 % des formulaires nécessaires |
| O2 | Automatiser l’envoi des questionnaires aux étudiants éligibles. | Taux d’envoi automatisé | 100 % des étudiants éligibles |
| O3 | Automatiser la collecte et la centralisation des réponses. | Taux de réponses correctement enregistrées | ≥ 95 % des réponses soumises |
| O4 | Nettoyer, transformer et préparer les données pour l’analyse. | Taux de données conformes et exploitables | ≥ 95 % |
| O5 | Développer des tableaux de bord interactifs de suivi de la satisfaction. | Disponibilité des indicateurs prioritaires | 100 % |
| O6 | Faciliter l’identification des tendances et des axes d’amélioration. | Couverture des besoins analytiques prioritaires | 100 % |

## 3. Périmètre fonctionnel et processus métier

Le projet couvre l’ensemble du processus, de la préparation des données à la restitution des résultats.

1. **Préparation des données de référence**
   - Contrôle et nettoyage des données d’inscription.
   - Identification des étudiants et des modules concernés.
   - Extraction des données depuis IGOR vers une base SQL Server dédiée.

2. **Conception des formulaires**
   - Création des questionnaires de satisfaction par module.
   - Paramétrage des questions et des axes d’analyse.
   - Association des formulaires aux populations étudiantes concernées.

3. **Automatisation des enquêtes**
   - Envoi des questionnaires aux étudiants éligibles.
   - Suivi des réponses reçues.
   - Envoi automatique des relances.
   - Réception et enregistrement des réponses.

4. **Centralisation et préparation des données**
   - Stockage des réponses dans une base dédiée.
   - Rapprochement avec les données de référence.
   - Nettoyage, contrôle qualité et normalisation.
   - Calcul des indicateurs et scores de satisfaction.

5. **Reporting et restitution**
   - Développement de tableaux de bord Power BI interactifs.
   - Suivi de la participation et de la satisfaction par module.
   - Analyse comparative et identification des modules les mieux et les moins appréciés.

## 4. Indicateurs clés de performance (KPI)

| KPI | Définition | Formule / règle | Cible |
|---|---|---|---|
| **KPI 01 – Nombre de réponses reçues** | Nombre de réponses enregistrées pour une campagne. | Comptage des réponses valides après déduplication. | Suivi évolutif |
| **KPI 02 – Taux de réponse** | Part des étudiants invités ayant répondu. | (Nombre de répondants valides ÷ Nombre d’étudiants invités) × 100 | ≥ 70 % à titre indicatif |
| **KPI 03 – Nombre de notifications envoyées** | Volume des invitations et relances transmises. | Comptage des notifications par type et campagne. | 100 % des notifications planifiées traitées |
| **KPI 04 – Taux de satisfaction par module** | Part des étudiants satisfaits pour chaque module. | (Nombre de réponses satisfaites ÷ Nombre de réponses reçues) × 100, par module. | À définir après la première campagne |
| **KPI 05 – Classement des modules** | Identification des modules les mieux et les moins appréciés. | Score moyen de satisfaction globale par module, avec classement Top 10 et Bottom 10. | À définir |

Les KPI sont actualisés à chaque actualisation des données dans Power BI.

## 5. Sources de données et technologies

### Sources de données

- **IGOR / SQL Server :** données d’inscription, étudiants, formations et axes analytiques. Accès en lecture selon les autorisations accordées.
- **Base SQL Server Data Analytics :** stockage des données préparées et des réponses aux enquêtes. Accès en lecture et écriture contrôlé selon les traitements.

### Technologies utilisées

- SQL Server : stockage et centralisation des données.
- Power BI : modélisation, calcul des KPI et visualisation.
- Outils d’automatisation : gestion des envois, relances et réponses aux enquêtes.

## 6. Principales règles de gestion

| ID | Catégorie | Règle |
|---|---|---|
| **RG-DEF-001** | Définition | Un destinataire éligible est un étudiant inscrit dans IGOR, associé à une période de formation concernée et disposant des informations nécessaires à l’envoi. |
| **RG-CAL-001** | Calcul | Le taux de réponse est calculé sur la base des destinataires ayant reçu le formulaire et ayant transmis une réponse valide. |
| **RG-PER-001** | Périmètre | Les enquêtes couvrent les cursus, marques d’école et périodes de formation inclus dans la campagne. Les étudiants non éligibles et les campagnes annulées sont exclus. |
| **RG-QUA-001** | Qualité | Les informations obligatoires, notamment l’identifiant étudiant, la période de formation et l’adresse e-mail, doivent être contrôlées avant l’envoi. |
| **RG-EXC-001** | Exceptions | Les données manquantes, réponses non associées et doublons sont signalés comme anomalies et exclus des calculs concernés jusqu’à vérification. |
| **RG-TMP-001** | Temporalité | Envoi initial à J-7 avant la fin du module, première relance à J-3 et seconde relance à J-2. Aucune relance après une réponse valide ou après clôture de la campagne. |
| **RG-SEC-001** | Sécurité | L’accès aux données nominatives et aux résultats est limité selon les rôles, les responsabilités et les habilitations accordées. |

*Statuts de validation des règles : RG-DEF-001, RG-CAL-001 et RG-PER-001 sont en revue. RG-QUA-001, RG-EXC-001, RG-TMP-001 et RG-SEC-001 sont au statut brouillon.*

---

*Projet réalisé dans le cadre de l’analyse de la satisfaction des étudiants du groupe Compétences & Développement.*
