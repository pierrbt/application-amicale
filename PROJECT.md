# Projet - fonctionnement et fonctionnalites

## 1) But du projet

Campus INSA Toulouse est une application mobile Android/iOS qui regroupe les services campus dans une interface unique.

Objectif principal : eviter la fragmentation des infos (Amicale, INSA, vie etudiante, services web externes) et proposer un acces rapide depuis le mobile.

## 2) Stack technique

- React Native (bare workflow)
- TypeScript
- React Navigation (tabs + stack)
- React Native Paper (UI)
- i18n-js (traductions)
- AsyncStorage + Keychain (preferences + token)

Version actuelle du projet : `6.0.1`.

## 3) Architecture globale

### Point d'entree

- `App.tsx` charge les preferences, le token de connexion et la gestion d'URL/deep links.
- `src/screens/MainApp.tsx` configure les providers UI/navigation/theme/cache.

### Etat et persistance

- Contexts React pour :
  - session utilisateur (login)
  - preferences (theme, ecran de depart, proxiwash, mascotte, notifications)
  - cache applicatif
- Preferences stockees dans AsyncStorage (`src/utils/asyncStorage.ts`)
- Token de connexion stocke dans le keychain natif (`src/utils/loginToken.ts`)

### Navigation

- Onglets principaux (`src/navigation/TabNavigator.tsx`) :
  - Services
  - Proxiwash
  - Home
  - Evenements
  - Planex
- Stack principal (`src/navigation/MainNavigator.tsx`) pour les ecrans detail, login, profil, reglage, etc.

## 4) Fonctionnalites metier

## Home

- Dashboard avec raccourcis personnalisables
- Apercu de l'evenement a venir
- Fil d'actualite agrege

## Services

- Catalogue classe par categories (Amicale, Etudiants, INSA, Special)
- Acces vers sites/services campus (RU, ENT, mails, Wiketud, etc.)

## Proxiwash

- Etat des lave-linge/seche-linge en temps reel
- Choix de laverie (INSA / Tripode B)
- Affichage detail d'une machine (modal)
- Nettoyage automatique de la watchlist en fonction de l'etat courant

Note : l'interface de notifications Proxiwash est partiellement desactivee cote UI actuellement.

## Evenements

- Recuperation des evenements Amicale
- Affichage agenda par date
- Ecran detail d'evenement

## Planex

- Integration webview de l'emploi du temps
- Choix de groupe + favoris
- Navigation semaine/jour et details d'evenements

## Fonctionnalites liees au compte Amicale

- Connexion/deconnexion
- Profil utilisateur
- Clubs
- Reservation de materiel
- Vote (selon fenetre d'ouverture)

## Reglages

- Theme clair/sombre (et suivi du systeme)
- Ecran de demarrage
- Personnalisation dashboard
- Parametres Proxiwash
- Ecran A propos + debug (deverrouillable)

## Autres

- Intro de mise a jour
- Ecran de feedback/bug report
- Mini-jeu integre
- Galerie d'images

## 5) Sources de donnees

- API Amicale : authentification + endpoints metier
- Endpoints campus JSON (dashboard/menu)
- Proximo (categories/articles)
- Proxiwash (machines)
- Planex (groupes/planning)

Les URLs sont centralisees dans `src/constants/Urls.tsx`.

## 6) Internationalisation

- Locales presentes : `fr`, `en`, `es`, `it`
- Fichiers dans `locales/*.json`
- Verification de coherence via `npm run test-locales`

## 7) Qualite et CI/CD

- Scripts locaux : lint, tests, verif TypeScript, full-check
- GitHub Actions :
  - `lint-test`
  - `build-android`
  - `build-ios`
  - `release`

## 8) Build et environnements

- Prerequis d'installation : `doc/INSTALL.md`
- Versions Android requises (demande projet) : `doc/ANDROID_TOOLCHAIN.md`

## 9) Limites connues / vigilance

- Certaines briques notifications sont historiques et necessitent une consolidation complete
- Plusieurs services reposent sur des endpoints externes, donc sensibles aux changements serveur
- Le projet repose sur une maintenance associative ; la doc est tenue a jour pour faciliter la reprise
