# Notes de developpement

Ce document centralise les decisions techniques utiles a la maintenance.

## 2026-02 - Etat general

- Socle actuel : React Native `0.79.6`, React `19.0.0`
- CI standardisee sur Node `24`
- Application toujours en architecture React Native bare workflow

## 2026-02 - Navigation collapsible

- `react-navigation-collapsible` retire
- En-tete collapsible supprime pour simplifier maintenance et compatibilite

## 2026-02 - Stockage token

- `react-native-keychain` mis a jour (les regressions historiques semblent resolues)
- Le token Amicale reste stocke dans le keychain natif

## Historique (rappel)

- Migration Flow -> TypeScript (simplification contribution)
- Abandon d'Expo managed workflow au profit du bare workflow
