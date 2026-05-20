# 🧠 Journal Coach

Assistant coach personnel pour Google AI Edge Gallery. Il lit ton journal Google Docs directement sur ton téléphone — tout tourne en local avec Gemma 4, rien n'est envoyé à un serveur.

---

## Structure du repo

```
journal-coach/
├── SKILL.md          ← Instructions pour Gemma (persona + logique du skill)
├── scripts/
│   └── index.html    ← Handler JS qui fetch le Google Doc
└── README.md
```

> ⚠️ Le dossier doit s'appeler `scripts` (avec un **s**), pas `script`.

---

## Installation

### 1. Activer GitHub Pages

Dans ton repo → **Settings** → **Pages**  
Source : `Deploy from a branch` → branch `main` → `/ (root)` → **Save**

Attends 2-3 minutes. Ton skill sera disponible à :
```
https://meconium94.github.io/journal-coach/SKILL.md
```

### 2. Charger dans Edge Gallery

1. Ouvre **Google AI Edge Gallery**
2. Sélectionne un modèle et lance **Agent Skills**
3. Tape sur le chip **Skills** → bouton **(+)**
4. **Load from URL** → colle :
   ```
   https://meconium94.github.io/journal-coach/SKILL.md
   ```

> ⚠️ Utilise l'URL `github.io` et **pas** `raw.githubusercontent.com`  
> (raw bloque l'exécution des scripts)

### 3. Préparer ton Google Doc

1. Ouvre ton journal Google Docs
2. **Partager** → **Toute personne disposant du lien** → **Lecteur**
3. Copie le lien

---

## Utilisation

Une fois le skill chargé, dis simplement :

> *"Je veux analyser mon journal : https://docs.google.com/document/d/..."*

Gemma lit le document et commence la session de coaching.

---

## Modèle recommandé

**Gemma 4 E2B** sur Pixel (Tensor G4/G5).  
Active **"Support speculative decoding"** dans les paramètres pour un gain de vitesse.

---

## Dépannage

| Problème | Solution |
|---|---|
| `Blocked script execution` | Tu utilises l'URL `raw.githubusercontent.com` → utilise l'URL `github.io` |
| Skill introuvable | GitHub Pages pas encore actif — attends 2-3 min après activation |
| Erreur 403 sur le doc | Active le partage du Google Doc avec le lien |
| Réponses lentes | Active "Support speculative decoding" + utilise E2B |

---

## Licence

Apache 2.0
