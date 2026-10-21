# ☁️ AWS IAM Lab - Gestion des identités et des accès

Travaux pratiques réalisés en **Bachelor 3 Réseaux et Systèmes Informatiques**.

##  Objectif

Mettre en pratique la gestion des utilisateurs, des groupes et des permissions dans AWS à l’aide d’**AWS CLI**, depuis **AWS CloudShell**.

Ce laboratoire présente la création de quatre utilisateurs, leur répartition dans deux groupes et l’attribution de politiques de permissions.

---

##  Environnement utilisé

| Service / outil | Utilisation |
|---|---|
| AWS IAM | Gestion des utilisateurs, des groupes et des permissions |
| AWS CloudShell | Exécution des commandes depuis la console AWS |
| AWS CLI | Création et vérification des ressources IAM en ligne de commande |

---

##  Organisation du laboratoire

| Groupe IAM | Utilisateurs | Politiques utilisées dans le TP |
|---|---|---|
| `Groupe_developpeur` | `developpeur_1`, `developpeur_2` | `ReadOnlyAccess`, `AmazonS3FullAccess` |
| `Groupe_cybersecurite` | `Administrateur_1`, `Administrateur_2` | `AdministratorAccess`, `IAMFullAccess` |

Les politiques utilisées permettent d’étudier l’attribution et le cumul des permissions. Elles ne constituent pas un modèle de droits recommandé pour un environnement de production.

---

## ⚙️ Réalisation

### 1. Création des groupes IAM

```bash
aws iam create-group --group-name Groupe_developpeur

aws iam create-group --group-name Groupe_cybersecurite
```

### 2. Création des utilisateurs

```bash
aws iam create-user --user-name developpeur_1

aws iam create-user --user-name developpeur_2

aws iam create-user --user-name Administrateur_1

aws iam create-user --user-name Administrateur_2
```

### 3. Association des utilisateurs aux groupes

```bash
aws iam add-user-to-group \
  --user-name developpeur_1 \
  --group-name Groupe_developpeur

aws iam add-user-to-group \
  --user-name developpeur_2 \
  --group-name Groupe_developpeur

aws iam add-user-to-group \
  --user-name Administrateur_1 \
  --group-name Groupe_cybersecurite

aws iam add-user-to-group \
  --user-name Administrateur_2 \
  --group-name Groupe_cybersecurite
```

### 4. Attribution des politiques aux groupes

#### Groupe développeurs

```bash
aws iam attach-group-policy \
  --group-name Groupe_developpeur \
  --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess

aws iam attach-group-policy \
  --group-name Groupe_developpeur \
  --policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess
```

#### Groupe cybersécurité

```bash
aws iam attach-group-policy \
  --group-name Groupe_cybersecurite \
  --policy-arn arn:aws:iam::aws:policy/AdministratorAccess

aws iam attach-group-policy \
  --group-name Groupe_cybersecurite \
  --policy-arn arn:aws:iam::aws:policy/IAMFullAccess
```

### 5. Accès programmatiques et connexion à la console

Le rapport présente également :

- La création de clés d’accès pour les utilisateurs.
- La création de profils de connexion à la console AWS.
- L’utilisation des commandes `create-access-key` et `create-login-profile`.

Aucune clé d’accès ni aucun mot de passe réel ne doit être publié dans ce dépôt.

### 6. Vérification des ressources IAM

#### Lister les groupes

```bash
aws iam list-groups
```

#### Lister les utilisateurs

```bash
aws iam list-users
```

#### Vérifier les membres de chaque groupe

```bash
aws iam get-group --group-name Groupe_developpeur

aws iam get-group --group-name Groupe_cybersecurite
```

#### Vérifier les politiques attachées aux groupes

```bash
aws iam list-attached-group-policies \
  --group-name Groupe_developpeur

aws iam list-attached-group-policies \
  --group-name Groupe_cybersecurite
```

---

##  Analyse des permissions

### Groupe développeurs

Le groupe reçoit les politiques `ReadOnlyAccess` et `AmazonS3FullAccess`.

Il ne dispose donc pas uniquement de droits de lecture : la seconde politique accorde également des permissions étendues sur Amazon S3.

### Groupe cybersécurité

Le groupe reçoit les politiques `AdministratorAccess` et `IAMFullAccess`.

Dans ce laboratoire, l’ajout de `IAMFullAccess` est redondant avec les permissions déjà accordées par `AdministratorAccess`.

### Enseignement principal

Il faut examiner l’ensemble des politiques applicables à une identité pour comprendre ses permissions effectives. Le nom d’un groupe ne suffit pas à déterminer ses droits.

---

##  Compétences travaillées

- Utilisation d’AWS CLI depuis CloudShell.
- Création d’utilisateurs et de groupes IAM.
- Gestion des appartenances aux groupes.
- Attribution de politiques AWS.
- Vérification des ressources et des permissions.
- Analyse des écarts entre les droits annoncés et les droits attribués.
- Rédaction d’un compte rendu technique.

---

##  Limites et pistes d’amélioration

Ce TP constitue une première mise en pratique d’AWS IAM. Les améliorations suivantes sont identifiées pour aller plus loin :

- Définir les permissions selon les besoins réels et le principe du moindre privilège.
- Limiter les permissions S3 aux ressources et aux actions nécessaires.
- Éviter l’attribution systématique de droits administrateur.
- Privilégier les rôles et les accès temporaires lorsque le contexte le permet.
- Renforcer la protection des accès à la console avec une authentification multifacteur.
- Supprimer les utilisateurs et les clés de test devenus inutiles.
- Compléter les vérifications par des tests d’accès autorisés et refusés.

Ces améliorations ne sont pas présentées comme déjà réalisées dans le laboratoire.

---

## 📄 Rapport du projet

➡️ **[Consulter le rapport complet - AWS IAM](https://github.com/user-attachments/files/33782416/AGUEDIA.MAGUE.RSI.CLOUD.pdf)
**

Le rapport présente les étapes du TP, les commandes utilisées et les illustrations associées.

**Note de lecture :** le rapport initial décrit le groupe développeurs comme étant en lecture seule, alors que les commandes lui attribuent aussi `AmazonS3FullAccess`. Ce README explicite cette différence.

---

## 📁 Organisation du dossier

- **README.md** : présentation du laboratoire, commandes et analyse.
- **Rapport_AWS_IAM.pdf** : compte rendu du projet.

---
<img width="600" height="400" alt="pngw" src="https://github.com/user-attachments/assets/fe5be389-5c93-41f5-9407-b47b9c48a149" />

##  Auteure

**Imelda AGUEDIA MAGUE**

- [Profil GitHub](https://github.com/imeldamague)
- [Autres projets et laboratoires](https://github.com/imeldamague/projets)
