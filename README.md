# ComputeTorrent
Un réseau pair-à-pair open source pour partager la puissance CPU/GPU via des VM isolées et contribuer à des calculs IA ou scientifiques.

# Cahier des Charges — ComputeTorrent

## 1. Contexte

ComputeTorrent est une infrastructure distribuée visant à mutualiser la puissance de calcul GPU entre plusieurs machines hétérogènes. Elle permet l'entraînement collaboratif de modèles d'apprentissage automatique (embeddings, LLM, etc.) via un protocole de validation décentralisé et une standardisation logicielle.

---

## 2. Objectifs

- Créer un réseau pair-à-pair de nœuds compute  
- Standardiser les environnements d'exécution  
- Assurer la reproductibilité et la fiabilité des calculs  
- Implémenter un système de validation croisée  
- Gérer la réputation et la performance des nœuds  

---

## 3. Architecture Générale

~~~py
[Client] → [Orchestrateur] → [Nœuds ComputeTorrent]
         ↘ [Validation Layer] ↙
~~~

- Client : soumet les tâches à exécuter  
- Orchestrateur : répartit les tâches selon les capacités GPU  
- Nœuds : exécutent les calculs  
- Validation Layer : vérifie les résultats et attribue des scores de confiance  

---

## 4. Standardisation des Environnements

~~~py
FROM nvidia/cuda:12.2.0-base-ubuntu22.04

RUN apt update && apt install -y python3-pip git
RUN pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu122

ENV PYTHONUNBUFFERED=1
~~~

---

## 5. Protocole de Validation

~~~py
1. Chaque tâche est exécutée par au moins 2 nœuds différents  
2. Les résultats sont comparés via hash ou métriques numériques  
3. Si divergence > seuil défini, la tâche est rejetée ou réattribuée  
4. Les nœuds ayant validé reçoivent un score de fiabilité  
~~~

---

## 6. Attribution des Tâches

~~~py
- Benchmark initial du GPU (VRAM, FLOPS, température)  
- Attribution pondérée selon :  
  - Disponibilité  
  - Historique de fiabilité  
  - Vitesse d'exécution  
~~~

---

## 7. API (extraits)

~~~py
POST /submit-job
  body: {
    model: "bert-base",
    dataset: "custom.csv",
    epochs: 5
  }

GET /job-status?id=12345
  response: {
    status: "running",
    progress: 62.5
  }

GET /results?id=12345
  response: {
    accuracy: 0.87,
    hash: "a9f3c..."
  }
~~~

---

## 8. Sécurité et Intégrité

~~~py
- Isolation des environnements via conteneurs  
- Chiffrement des échanges entre nœuds  
- Vérification des signatures de code  
- Système de réputation pour exclure les nœuds malveillants  
~~~

---

## 9. Scalabilité

~~~py
- Ajout dynamique de nœuds  
- Répartition adaptative des tâches  
- Monitoring en temps réel  
~~~

---

## 10. Limitations Connues

~~~py
- Non-déterminisme possible sur certains GPU  
- Variabilité des performances réseau  
- Fiabilité dépendante de la qualité des machines participantes  
~~~

