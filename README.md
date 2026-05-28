````md id="lab9drozer"
# LAB 9 — Analyse de Surface d’Attaque Android avec Drozer

![Android](https://img.shields.io/badge/Platform-Android-green)
![Drozer](https://img.shields.io/badge/Tool-Drozer-red)
![OWASP](https://img.shields.io/badge/OWASP-MASVS-blue)

## 📌 Description

Ce laboratoire présente l’analyse de surface d’attaque Android avec Drozer dans un environnement autorisé.

Objectifs :

- identifier les composants Android exposés
- analyser les risques sécurité
- cartographier l’application
- proposer des remédiations OWASP

---

# ⚙️ Prérequis

- Python
- ADB
- Drozer installé
- Android avec USB Debugging
- APK pédagogique autorisé

---

# 🎯 Objectifs Pédagogiques

- utiliser Drozer
- analyser une application Android
- détecter des composants vulnérables
- documenter un audit mobile

---

# 🛠 Étape 1 — Configuration

Vérifier ADB :

```bash id="t7m2xd"
adb devices
````
<img width="634" height="335" alt="image" src="https://github.com/user-attachments/assets/f2aca5b3-e506-4a6e-9f91-fb199a7a39ca" />

Lancer le port forwarding :

```bash id="g4v9qs"
adb forward tcp:31415 tcp:31415
```

---

# 📱 Étape 2 — Connexion Drozer

Démarrer Drozer :

```bash id="r8k3yn"
drozer console connect
```

Résultat attendu :

```text id="m2x6qa"
Connected to com.mwr.dz
```
<img width="732" height="375" alt="image" src="https://github.com/user-attachments/assets/005556de-a8e9-457c-b048-7d9d87ae55bb" />

---

# 🔍 Étape 3 — Cartographie des Composants

Lister les packages :

```bash id="d5w1lp"
run app.package.list
```
<img width="1198" height="472" alt="image" src="https://github.com/user-attachments/assets/746c0812-183d-4395-89d2-9fc218de6671" />

Informations package :

```bash id="x7c4vu"
run app.package.info -a com.example.app
```

---

# ⚡ Étape 4 — Analyse des Components

Activities exportées :

```bash id="p9v3kn"
run app.activity.info -a com.example.app
```

Services :

```bash id="z1m7qt"
run app.service.info -a com.example.app
```

Content Providers :

```bash id="j4x8rw"
run app.provider.info -a com.example.app
```
<img width="834" height="553" alt="image" src="https://github.com/user-attachments/assets/718060cb-8109-4de1-b4d5-3dd945ecc5bf" />

---

# 🛡 Étape 5 — Vérification des Protections

Analyser :

* composants exportés
* permissions faibles
* providers vulnérables
* intents non sécurisés
<img width="1444" height="296" alt="image" src="https://github.com/user-attachments/assets/4c2f927c-7c09-43c1-abbd-eb5e9d9d63d9" />

---
<img width="880" height="748" alt="image" src="https://github.com/user-attachments/assets/1726040a-7441-4d79-a377-4fc4c423e491" />

# 🔥 Étape 6 — Analyse des Risques

Exemples :

| Risque              | Impact               |
| ------------------- | -------------------- |
| Activity exportée   | accès non autorisé   |
| Provider vulnérable | fuite données        |
| Permissions faibles | élévation privilèges |

---

# 📸 Étape 7 — Collecte de Preuves

Capturer :

* screenshots
* commandes utilisées
* résultats Drozer

---

# 📚 Mapping OWASP

Correspondance :

* OWASP MASVS
* MASTG
* Mobile Security Testing

---

# 🛠 Remédiations

* désactiver `exported=true`
* ajouter permissions
* sécuriser intents
* protéger providers

---

# ✅ Résultats Attendus

* composants analysés
* risques identifiés
* preuves collectées
* recommandations sécurité

---

# ⚠️ Usage Éducatif

Utilisation uniquement :

* en laboratoire
* sur applications autorisées
* pour apprentissage cybersécurité mobile

---

# 👨‍💻 Auteur

Ayoub Laafar — EMSI Marrakech

```
```
