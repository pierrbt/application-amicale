# Traductions

Le projet utilise des fichiers JSON dans `locales/`.

Langues actuellement presentes : `fr`, `en`, `es`, `it`.

Envoie-moi un mail avant de commencer pour me prévenir que tu veux travailler sur une traduction. Cela me permettra de te mettre en relation avec d'autres personnes travaillant également sur cette traduction.

## Ajouter ou corriger une traduction

1. Copier `locales/en.json` (locale de reference)
2. Traduire uniquement les valeurs (ne pas changer les cles)
3. Lancer la verification :

```bash
npm run test-locales
```

4. Ouvrir une PR avec le fichier modifie

## Convention

- Garder le ton coherent avec l'app
- Eviter les phrases trop longues pour mobile
- Ne pas supprimer de cles

## Besoin d'aide

- Discord : <https://discord.gg/W8MeTec>
- Mail : <mailto:app@amicale-insat.fr>
