```markdown
# Audio Translation Pipeline

## Description
Ce projet est un pipeline complet qui permet de transformer un fichier audio en anglais en un fichier audio traduit en français. Le pipeline combine plusieurs étapes, notamment :
1. **Reconnaissance vocale (Speech-to-Text)** : Conversion de l'audio en texte.
2. **Traduction automatique** : Traduction du texte anglais en français.
3. **Synthèse vocale (Text-to-Speech)** : Conversion du texte traduit en audio.

---

## Fonctionnalités principales
- Prise en charge de fichiers audio en anglais.
- Traduction précise utilisant des modèles MarianMT.
- Génération de voix naturelle en français grâce à la bibliothèque TTS.
- Gestion des erreurs détaillée pour garantir une expérience utilisateur robuste.

---

## Installation
Pour exécuter ce projet, vous aurez besoin de Python 3.8 ou supérieur et des bibliothèques suivantes. Installez-les avec les commandes ci-dessous :

```bash
pip install torch torchaudio transformers TTS soundfile scipy
pip install SpeechRecognition  # Optionnel pour la reconnaissance vocale avec Google
```

---

## Utilisation
### Exemple d'exécution
Pour lancer le pipeline :
1. Placez un fichier audio anglais dans le répertoire de travail (par exemple, `english_audio.wav`).
2. Modifiez les paramètres dans la section `if __name__ == "__main__"`.
3. Lancez le script :

```bash
python main.py
```

Le fichier traduit sera enregistré dans le fichier spécifié (`audio_traduit_francais.wav` par défaut).

---

## Fonctionnement du Pipeline
### 1. Chargement de l’audio
- Le fichier audio est chargé, vérifié et converti en mono si nécessaire.
- Les fichiers trop longs (> 30 secondes) sont tronqués.

### 2. Reconnaissance vocale
- Par défaut, utilise la bibliothèque `SpeechRecognition` avec l’API Google.
- En option, utilise le modèle Whisper via Hugging Face pour une reconnaissance hors ligne.

### 3. Traduction
- Traduit le texte reconnu de l’anglais au français à l’aide des modèles MarianMT de Hugging Face.

### 4. Synthèse vocale
- Génère un fichier audio en français à partir du texte traduit avec la bibliothèque TTS.

---

## Exemple de code
Voici un exemple pour transformer un fichier audio en français :

```python
audio_input = "english_audio.wav"
output_audio = "audio_traduit_francais.wav"

process_audio_pipeline(audio_input, output_audio, target_language="fr-fr")
```

---

## Prérequis
- **Python 3.8+**
- GPU recommandé pour une exécution plus rapide avec `torch`.

---

## Problèmes fréquents
- **Fichier audio introuvable** : Vérifiez que le chemin est correct.
- **Manque de RAM** : Certains modèles peuvent nécessiter beaucoup de mémoire.
- **Pas de GPU** : Assurez-vous que `torch` est configuré pour utiliser le CPU ou GPU.

---

## Auteur
**Yonli Fidèle**  
Contact : [email@example.com](mailto:email@example.com)

---

## Licence
Ce projet est sous licence MIT.
```

Ce `README.md` est structuré pour expliquer le projet de manière claire et guider les utilisateurs dans son utilisation. Si vous avez des modifications ou des précisions à ajouter, n'hésitez pas !
