# iOS - certificats et build

Procedure de reference pour renouveler les certificats de distribution iOS.

## Prerequis

- macOS avec Xcode recent
- Acces Apple Developer de l'organisation
- Acces aux secrets GitHub Actions (`build-ios`)

## Renouveler les certificats

1. Generer une CSR sur macOS
2. Creer et signer le certificat dans Apple Developer
3. Importer le certificat dans Keychain
4. Exporter en `.p12`
5. Regenerer un provisioning profile App Store
6. Encoder les fichiers en base64 et mettre a jour les secrets GitHub
7. Lancer le workflow `build-ios` pour valider

## Commande utile (base64)

```bash
base64 -i clubinfo.mobileprovision | tr -d '\n'
```

Adapter le nom de fichier selon le profil utilise.

## Liens Apple/GitHub

- CSR : <https://developer.apple.com/help/account/create-certificates/create-a-certificate-signing-request>
- Certificats : <https://developer.apple.com/account/resources/certificates/list>
- Profils : <https://developer.apple.com/account/resources/profiles/list>
- Environnements GitHub Actions :
  <https://github.com/ClubInfoInsaT/application-amicale/settings/environments>

## Notes

- Le build iOS de prod passe par GitHub Actions
- Les valeurs sensibles ne doivent jamais etre committees
