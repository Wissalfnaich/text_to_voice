# 🎙️ Voice Cloning – Coqui XTTS v2 

Ce projet permet de générer une **voix clonée réaliste, fluide et expressive** à partir d’un échantillon vocal et d’un texte libre.  
Le système est destiné à produire des **audios pédagogiques** dans un contexte **santé / enfant / parent**, avec un rendu **rassurant, motivant et souriant**.

L’objectif du projet est d’aider les praticiens à **expliquer plus facilement leurs bilans**, en transformant automatiquement un rapport en **audio narratif** utilisable dans une vidéo avec avatar.

---

## ✨ Fonctionnement général

1. On fournit un **fichier voix `.wav`** (10–40s) → le modèle **clône la voix**
2. On colle **n’importe quel texte**
3. Coqui XTTS génère un **audio fluide, naturel et expressif**
4. Le résultat est exporté en `.wav`

---

## 🎛️ Paramètres modifiables

### ✅ Paramètres principaux
| Paramètre | Rôle |
|-----------|------|
| `text` | Le texte à lire (multi-ligne, emoji, accents, retour à la ligne OK) |
| `speaker_wav` | Voix à cloner (WAV 10–40s) |
| `language` | Langue à utiliser (`"fr"`, `"en"`, etc.) |
| `split_sentences` | Si `True`, XTTS gère les respirations automatiquement |

> **Recommandé :** `split_sentences=True` → voix plus naturelle, sans coupures

---

### ✅ Influence de la ponctuation sur la voix

| Ponctuation | Effet sur la prosodie |
|-------------|----------------------|
| `.` | pause courte, ton neutre |
| `,` | micro respiration |
| `?` | intonation montante, ton interrogatif |
| `!` | sourire / énergie / motivation |
| `…` | pause expressive, suspense |
| `\n\n` | respiration plus longue, changement de rythme |

> **Astuce :** phrases courtes + ponctuation variée = voix beaucoup plus humaine

---

### ✅ Paramètres avancés (émotion / expressivité)

Ces paramètres sont utilisables si on passe par `tts()` au lieu de `tts_to_file()` :

| Paramètre | Effet |
|-----------|-------|
| `temperature` | expressivité (0.3 = monotone, 0.8 = vivant) |
| `length_scale` | vitesse et rythme (>1 lent, <1 rapide) |
| `noise_scale` | variation d’intonation (prosodie) |
| `noise_scale_w` | variation fine (micro-intentions) |

| Style recherché | `temperature` | `length_scale` | `noise_scale` |
|----------------|---------------|----------------|---------------|
| Doux / rassurant | 0.4–0.6 | 1.05–1.2 | 0.2–0.4 |
| Enfant souriant motivant | 0.6–0.8 | 1.0–1.15 | 0.4–0.6 |
| Dynamique / énergique | 0.8–1.0 | 0.9–1.1 | 0.5–0.7 |

---

## ✅ Conseils pour un rendu naturel

✔️ phrases courtes plutôt que pavés  
✔️ varier ponctuation (. , ! ?)  
✔️ ajouter des retours à la ligne pour marquer des respirations (`\n\n`)  
✔️ choisir un échantillon voix propre, sans bruit ni écho  
✔️ éviter les textes trop longs en un seul bloc




