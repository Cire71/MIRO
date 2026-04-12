# MiroFish — Procédure de démarrage

## Stack

| Service | Rôle | Port |
|---------|------|------|
| Neo4j (Docker) | Base de données graphe | 7687 / 7474 |
| Ollama (Windows) | Embeddings (`nomic-embed-text`) | 11434 |
| Backend (Flask + venv) | API Python | 5001 |
| Frontend (Vite) | Interface utilisateur | 3000 |

## Configuration

- LLM : OpenRouter → `google/gemini-2.5-flash-lite`
- Embeddings : Ollama local → `nomic-embed-text`
- Neo4j : `bolt://localhost:7687`, auth `neo4j/mirofish123`
- Venv Python : `backend/.venv/Scripts/python`

---

## Séquence de démarrage

### 1. Neo4j

Vérifier si le conteneur tourne déjà :
```bash
docker ps --filter name=mirofish-neo4j --format "{{.Status}}"
```

S'il n'est pas `Up`, le démarrer :
```bash
docker start mirofish-neo4j
```

Attendre que Neo4j réponde sur `http://localhost:7474` (réessayer jusqu'à succès).

### 2. Ollama

Vérifier si Ollama répond :
```bash
curl -s http://localhost:11434/api/tags
```

Si pas de réponse, Ollama n'est pas lancé (l'utilisateur doit le démarrer manuellement depuis le système tray Windows ou via `ollama serve`).

Vérifier que `nomic-embed-text` est disponible dans la liste des modèles.

### 3. Backend Flask

Vérifier si le port 5001 est déjà utilisé :
```bash
netstat -ano | grep ":5001"
```

Si pas de processus, lancer le backend avec le venv :
```bash
cd c:/projets/MiroFish && backend/.venv/Scripts/python backend/run.py > /tmp/mirofish-backend.log 2>&1 &
disown $!
```

Attendre que le log affiche `Backend startup complete` ou que `http://localhost:5001` réponde.

### 4. Frontend

Vérifier si le port 3000 est déjà utilisé :
```bash
netstat -ano | grep ":3000"
```

Si pas de processus, lancer le frontend :
```bash
cd c:/projets/MiroFish/frontend && npm run dev > /tmp/mirofish-frontend.log 2>&1 &
disown $!
```

---

## Vérification finale

Confirmer que les 4 services sont actifs et afficher un récapitulatif :

```
Neo4j     ✓  localhost:7687
Ollama    ✓  localhost:11434
Backend   ✓  localhost:5001
Frontend  ✓  localhost:3000
```

Puis indiquer à l'utilisateur : **"MiroFish est prêt → http://localhost:3000"**

---

## Workflow campagne

1. **Graph Build** — Uploader un document (PDF, texte, communiqué de presse...)
2. **Env Setup** — Générer les personas d'agents IA
3. **Simulation** — Lancer la simulation de réactions sociales
4. **Report** — Analyser les résultats via ReportAgent
5. **Interaction** — Chatter avec les agents simulés

## Arrêt propre

```bash
# Arrêter Neo4j
docker stop mirofish-neo4j

# Les processus backend et frontend se terminent en fermant le terminal
```
