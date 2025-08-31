# ComputeTorrent
Un réseau pair-à-pair open source pour partager la puissance CPU/GPU via des VM isolées et contribuer à des calculs IA ou scientifiques.

## 🚀 Objectif du projet

**ComputeTorrent** est une plateforme décentralisée qui permet à chacun de **partager la puissance de calcul** de son ordinateur (CPU, GPU) avec d'autres utilisateurs via un réseau pair-à-pair.  
L’idée est simple : au lieu de dépendre de serveurs coûteux ou de services cloud, on utilise les machines des volontaires pour exécuter des tâches lourdes comme :

- L'entraînement de modèles d'intelligence artificielle (IA)
- Le rendu d’images ou de vidéos
- Des calculs scientifiques ou statistiques

Ce système repose sur des environnements isolés (machines virtuelles ou containers) pour garantir la sécurité et la cohérence des résultats.

---

## 👥 Pour qui ?

- Les développeurs qui veulent contribuer à un projet open source ambitieux
- Les chercheurs ou créateurs qui ont besoin de puissance de calcul
- Les curieux qui veulent apprendre à créer des systèmes distribués

---

## 🛠️ Comment ça fonctionne (en résumé)

1. Chaque utilisateur installe un **client ComputeTorrent** sur sa machine.
2. Ce client détecte les ressources disponibles (CPU, GPU, RAM).
3. Lorsqu’une tâche est soumise au réseau, elle est découpée en petits blocs.
4. Ces blocs sont envoyés à plusieurs machines pour être exécutés.
5. Les résultats sont vérifiés, agrégés, puis renvoyés à l’utilisateur demandeur.

---

## 🐍 Langage utilisé

Le projet commence en **Python**, car c’est un langage :

- Facile à apprendre
- Très utilisé en IA et en science des données
- Compatible avec les bibliothèques GPU (comme PyTorch, TensorFlow)
- Bien adapté à la gestion de containers (Docker, etc.)

Les premiers scripts seront donc écrits en Python, avec une structure simple et modulaire.

~~~py
# Exemple de structure de dossier (à venir)
compute_torrent/
├── client/
├── orchestrator/
├── tasks/
├── utils/
└── README.md
~~~

---

## 📦 Ce que le projet inclura plus tard

- Une interface web pour suivre les tâches en cours
- Un système de réputation pour les machines fiables
- Des outils de monitoring (CPU/GPU, température, logs)
- Une API pour soumettre des jobs et récupérer les résultats

---

## 🧑‍💻 Comment commencer à coder ?

1. Cloner le dépôt GitHub (à venir)
2. Installer les dépendances Python (via `pip`)
3. Lancer le client local et tester avec une tâche simple
4. Contribuer à l’orchestrateur ou à la validation des résultats

~~~py
# Exemple de commande pour installer les dépendances
pip install -r requirements.txt
~~~

---

## 🧭 Prochaines étapes

- Définir les premiers types de tâches (ex: calcul de Pi, rendu d’image)
- Créer un orchestrateur simple pour distribuer les blocs
- Mettre en place un système de validation par redondance
- Documenter chaque module pour faciliter la contribution

---

## 💬 En résumé

ComputeTorrent est une aventure technique et communautaire.  
Le but est de **rendre la puissance de calcul accessible, distribuée et sécurisée**, en s’appuyant sur Python pour démarrer rapidement et efficacement.
