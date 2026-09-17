
# 🔐 SO-EMBALLAGE – Analyse de risques & conformité SI (MEHARI & EBIOS RM)

## 🎯 Objectif du projet

Ce projet explore l'**analyse de risques cyber** et la **gouvernance SSI**, à travers l'application des méthodes **MEHARI** (CLUSIF) et **EBIOS Risk Manager** (ANSSI) sur le système d'information d'une entreprise fictive de distribution d'emballages B2B (33,8 M€ de CA, 185 salariés).

Le projet a été réalisé dans le cadre de l'atelier *Cyber & E-réputation* avec :

* Méthode MEHARI (CLUSIF)
* Méthode EBIOS Risk Manager (ANSSI)
* Référentiels ISO/IEC 27001 et 27005, RGPD, directive NIS2

---

## 🧩 Périmètre analysé

Le système d'information étudié couvre :

* Application interne de gestion des achats/ventes
* Modules SAP ERP (stocks, finance)
* Serveur Linux (SPOF identifié)
* Parc de ~100 postes Windows hétérogènes
* Site e-commerce (catalogue, commandes en ligne)
* Infrastructure réseau (LAN, VPN partenaires)

---

## 📊 Analyse des risques (MEHARI)

* **20 scénarios de risques** modélisés et évalués, dont un scénario de type **LockBit** (ransomware)
* **Matrice de criticité** : 4 risques critiques (ransomware, intrusion web, phishing, panne serveur), 7 risques majeurs, 9 risques significatifs à mineurs
* Évaluation quantitative des risques (potentialité x impact), conforme ISO/IEC 27005

---

## 🗺️ Gouvernance des risques (EBIOS Risk Manager)

* 5 ateliers menés : cadrage, sources de risques, scénarios stratégiques, scénarios opérationnels, traitement du risque
* Identification des besoins de sécurité selon les critères **DICT** (Disponibilité, Intégrité, Confidentialité, Traçabilité)
* Cartographie des chemins d'attaque, des sources de risques jusqu'aux impacts sur les valeurs métier

---

## 💰 Retour sur investissement

* **Ratio 7:1** sur les mesures de sécurité proposées
* Budget recommandé : 100-186 k€ (initial), 125-201 k€ (annuel), soit 0,37-0,59 % du CA — conforme aux recommandations sectorielles (0,5-1 % du CA)

---

## 🛡️ Préconisations

* **Techniques** : EDR, WAF, segmentation réseau, homogénéisation du parc Windows
* **Organisationnelles** : rédaction d'une PSSI, charte informatique, gestion des accès (moindre privilège), procédure de gestion des incidents, conformité RGPD (DPO, registre des traitements, AIPD), audits périodiques, clauses de sécurité fournisseurs
* **Humaines** : programme de sensibilisation annuel (185 employés), campagnes de phishing simulé trimestrielles, formation de l'équipe IT, nomination d'un RSSI, veille sur les vulnérabilités SAP/Linux/Windows

---

## 📄 Rapport complet

Le rapport complet du projet est disponible ici :

📄 **SO-EMBALLAGE_Rapport.pdf** [SO-EMBALLAGE_Rapport.pdf](https://github.com/userattachments/files/32332503/GROUPE.8.Analyse.Risques.SO.EMBALLAGE.pdf)

---

## 🛠️ Méthodologies et référentiels utilisés

* MEHARI (CLUSIF)
* EBIOS Risk Manager (ANSSI)
* ISO/IEC 27001:2022, ISO/IEC 27005:2022
* RGPD, directive NIS2

---

## 👥 Équipe

Projet réalisé en groupe dans le cadre de l'atelier Cyber & E-réputation (ING-MA CYBER, 11 février 2026) : Imelda Mague, Ephra, Mayeva, Alex.
