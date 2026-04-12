# Campagne MiroFish — Assistant de création

Quand l'utilisateur invoque **"campagne"**, exécute la procédure suivante **exactement dans cet ordre** :

---

## 1. Introduction

Annonce à l'utilisateur :

> "Je vais te poser 10 questions pour créer les fichiers Reality Seeds de ta campagne MiroFish.
> Réponds librement — je reformule et structure pour toi.
> À la fin, je génère les 4 fichiers prêts à uploader."

---

## 2. Questions — à poser une par une, attendre la réponse avant de continuer

---

### BLOC A — L'OFFRE

**Q1 — L'offre en une phrase**
> "Décris ton offre en 2-3 lignes : qu'est-ce que c'est, pour qui, et à quel prix ?"

**Q2 — Le modèle économique**
> "Comment tu es rémunéré ? (abonnement mensuel, commission, forfait, hybride...)
> Et comment ça se différencie du modèle de tes concurrents ?"

**Q3 — L'avantage fondamental**
> "Quelle est LA raison pour laquelle un client devrait choisir ton offre plutôt qu'un concurrent ?
> Formule-le comme si tu l'expliquais à un ami sceptique."

---

### BLOC B — LE MARCHÉ ET LES ACTEURS

**Q4 — Les concurrents et antagonistes**
> "Qui sont tes concurrents ou alternatives dans l'esprit du client ?
> Pour chacun, dis-moi : leur argument principal, leur point faible, leur comportement typique."

**Q5 — Les prescripteurs et alliés**
> "Qui influence la décision d'achat sans être le client final ?
> (expert-comptable, association pro, consultant, journaliste, influenceur...)"

**Q6 — Les tensions clés**
> "Quelle est la tension centrale que la simulation doit dramatiser ?
> Ex : 'ton offre payante vs concurrent gratuit', 'nouveau modèle vs marché traditionnel'..."

---

### BLOC C — LES PERSONAS CLIENTS

**Q7 — Les profils clients**
> "Décris 3 à 4 profils de clients typiques. Pour chacun :
> - Qui il est (âge, secteur, taille)
> - Sa douleur principale (ce qui lui coûte sans qu'il le sache)
> - Ce qui le fait résister
> - Ce qui le fait basculer (le déclencheur de conversion)"

---

### BLOC D — LE SCÉNARIO ET LES OBJECTIFS

**Q8 — Le scénario à simuler**
> "Y a-t-il des phases ou événements à simuler ?
> Ex : période de marché bas puis haut, avant/après une crise, lancement d'un produit...
> Ou préfères-tu une simulation 'état du marché actuel' sans phase ?"

**Q9 — Ce que tu veux apprendre**
> "Quels sont les 3-5 insights que tu veux que la simulation te révèle ?
> Ex : quel argument convertit quel profil, quel prix passe, quelles objections reviennent..."

---

### BLOC E — LES DONNÉES ET VERBATIMS

**Q10 — Les chiffres**
> "Donne-moi les chiffres clés de ton marché et de ton offre :
> - Taille du marché adressable
> - Prix / tarifs / marges
> - ROI typique pour un client
> - Données concurrentielles si tu en as"

**Q11 — Les verbatims**
> "As-tu des phrases réelles (ou typiques) de clients ?
> Pour chaque profil, 1-2 citations qui capturent leur état d'esprit :
> leur résistance, leur doute, leur moment de bascule, leur satisfaction."

*(Si l'utilisateur n'en a pas : lui proposer de les inventer ensemble à partir des profils Q7)*

---

## 3. Génération des fichiers

Une fois les 11 questions répondues, génère les fichiers suivants dans un dossier
`MiroFish-data/campagnes/[nom-campagne]/` :

---

### Fichier 1 — `01-document-principal.txt`

Structure imposée (reprendre les sections exactes) :

```
DOSSIER DE SIMULATION MIROFISH — [NOM CAMPAGNE]
Marché : [marché cible]
Secteurs : [secteurs]
Périmètre : [géographie/périmètre]
Date de simulation : [contexte temporel]

================================================================
1. CONTEXTE DU MARCHÉ
================================================================
[2-3 paragraphes : le problème fondamental du client, l'asymétrie d'information,
l'opportunité que personne ne saisit. Chiffres clés intégrés.]

================================================================
2. L'OFFRE [NOM]
================================================================
PRINCIPE : [la proposition de valeur en une phrase]

SERVICES INCLUS :
- [liste des services/bénéfices]

MODÈLE DE RÉMUNÉRATION :
- [détail du pricing]
- [comparaison avec le modèle concurrent]

AVANTAGE STRUCTUREL :
[Pourquoi le modèle est supérieur au concurrent — avec chiffres]

================================================================
3. LES ACTEURS DE LA SIMULATION
================================================================
[Pour chaque acteur : Type, Positionnement, Ton, Arguments principaux,
Faiblesses simulées, Comportement attendu dans la simulation]

--- ACTEUR 1 : [L'offre — protagoniste] ---
--- ACTEUR 2 : [Concurrent principal — antagoniste] ---
--- ACTEUR 3-N : [Autres acteurs marché] ---
--- ACTEUR N+1 : [Persona client réticent] ---
--- ACTEUR N+2 : [Persona client fidèle concurrent] ---
--- ACTEUR N+3 : [Persona client rationnel/opportuniste] ---
--- ACTEUR N+4 : [Prescripteur neutre] ---

================================================================
4. TENSIONS ET OPPOSITIONS
================================================================
[Tableau : Acteur A | Relation | Acteur B | Nature du conflit]

================================================================
5. SÉQUENCE DE SIMULATION
================================================================
[Si phases : PHASE 1 — contexte, ce qui se passe, arguments clés]
[Si pas de phases : description du contexte de marché statique]

================================================================
6. INSIGHTS À FAIRE ÉMERGER
================================================================
1. [Insight 1 — question précise]
2. [Insight 2]
...
```

---

### Fichier 2 — `02-prompt-simulation.txt`

Rédiger en **anglais**. Structure imposée :

```
================================================================
PROMPT — "Simulation Topic" field in MiroFish
================================================================

You are simulating [marché] in [contexte géographique/temporel].

CORE TENSION:
[La tension centrale en 3-5 lignes — qui s'oppose à qui et pourquoi]

THE FUNDAMENTAL INSIGHT TO SIMULATE:
[Le problème que le client ne voit pas — formulé comme une révélation]

[SI PHASES : MARKET SEQUENCE TO SIMULATE]
PHASE 1 — Rounds 1 to [N]: [NOM PHASE] ([fourchette prix ou contexte])
[Ce qui se passe, comportement de chaque acteur]

PHASE 2 — Rounds [N+1] to [Total]: [NOM PHASE]
[Ce qui se passe, comportement de chaque acteur]

ACTORS AND THEIR ROLES:
[Pour chaque acteur : nom, rôle, arguments, faiblesses, key message]

SIMULATION OBJECTIVES — What the report must reveal:
1. [Objectif 1]
2. [Objectif 2]
...

Platforms: Twitter/X + Reddit
Rounds: 96 (full) or 24 (quick test)
Language: French preferred, English acceptable for market data posts
```

---

### Fichier 3 — `03-market-data.txt`

Structure imposée :

```
DONNÉES MARCHÉ — [NOM CAMPAGNE]
(fichier complémentaire — à uploader avec le document principal)

================================================================
DONNÉES STRUCTURELLES DU MARCHÉ
================================================================
[Taille du marché, segments, parts de marché, données concurrentielles]

================================================================
DONNÉES PRIX / TARIFS (référence simulation)
================================================================
[Historique ou fourchettes de prix, niveaux haut/bas si applicable]

================================================================
STRUCTURE DU COÛT POUR LE CLIENT
================================================================
[Décomposition de ce que paie le client — quelles parties sont négociables/optimisables]

================================================================
CALCULS ROI ABONNEMENT / OFFRE
================================================================
[Exemple TPE/PME/Client type : abonnement annuel, économie potentielle, ROI, break-even]

================================================================
CONTEXTE RÉGLEMENTAIRE ET MARCHÉ
================================================================
[Réglementations pertinentes, tendances, risques/opportunités]
```

---

### Fichier 4 — `04-verbatims-clients.txt`

Structure imposée :

```
VERBATIMS CLIENTS — [NOM CAMPAGNE]
(voix authentiques du marché — à uploader pour enrichir la mémoire des agents)

================================================================
[PROFIL 1 — ex : CLIENTS RÉTICENTS]
================================================================
[3-4 citations avec contexte : secteur, taille, ce que ça révèle]

================================================================
[PROFIL 2 — ex : CLIENTS FIDÈLES AU CONCURRENT]
================================================================
[3-4 citations]

================================================================
[PROFIL 3 — ex : CLIENTS OPPORTUNISTES / DÉÇUS]
================================================================
[3-4 citations]

================================================================
TÉMOIGNAGES POST-ACCOMPAGNEMENT (réels ou réalistes)
================================================================
[2-3 témoignages de clients satisfaits avec chiffres concrets]

================================================================
OBJECTIONS FRÉQUENTES ET CONTEXTE
================================================================
Objection 1 — "[Texte de l'objection]"
Contexte : [Pourquoi le client dit ça]
Réponse à tester : "[La réponse à simuler]"

[Répéter pour chaque objection principale]
```

---

## 4. Récapitulatif final

Une fois les 4 fichiers générés, afficher :

```
Campagne [NOM] — fichiers créés dans MiroFish-data/campagnes/[nom-campagne]/

  01-document-principal.txt   ✓  Reality Seed — upload principal
  02-prompt-simulation.txt    ✓  Coller dans "Simulation Topic"
  03-market-data.txt          ✓  Upload complémentaire
  04-verbatims-clients.txt    ✓  Upload complémentaire

Paramètres recommandés :
  Rounds : 96 (complet) ou 24 (test rapide)
  Plateformes : Twitter + Reddit
  Langue agents : Français prioritaire
```

---

## Notes pour Claude

- **Reformule toujours** les réponses de l'utilisateur avant de les intégrer — pas de copier-coller brut
- **Invente les verbatims manquants** à partir des personas si l'utilisateur n'en a pas (les signaler comme "réalistes")
- **Insiste sur les chiffres** — un fichier sans données chiffrées est un fichier faible
- **Maintiens la cohérence** entre les 4 fichiers : mêmes noms d'acteurs, mêmes chiffres, même terminologie
- **Le prompt (fichier 2) est en anglais** — MiroFish fonctionne mieux avec un prompt en anglais
- Si une question reste floue, propose 2-3 options concrètes plutôt que de laisser l'utilisateur dans le vide
