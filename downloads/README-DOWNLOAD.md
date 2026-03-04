# Télécharger Locally pour Android

## Lien à ouvrir sur ton Android

Ouvre **cette page** sur ton téléphone Android pour afficher le bouton de téléchargement :

| Où tu ouvres la page | URL à taper (exemple) |
|----------------------|------------------------|
| **Même Wi‑Fi que ton ordinateur** (serveur local) | `http://192.168.1.XX:8080/download-locally-android.html` |
| **Site hébergé** (GitHub Pages, Netlify…) | `https://ton-domaine.com/download-locally-android.html` |

Remplace `192.168.1.XX` par l’IP de ton Mac/PC (Paramètres réseau) et `8080` par le port si tu en utilises un autre.

Ensuite, appuie sur **« Télécharger l’APK pour Android »** pour télécharger puis installer l’app.

---

## Mettre l’APK en place pour le bouton

1. **Générer l’APK** (sur un Mac/PC avec Android Studio ou JDK + Android SDK) :
   ```bash
   cd locally-android/android
   ./gradlew assembleDebug
   ```
   Fichier produit : `locally-android/android/app/build/outputs/apk/debug/app-debug.apk`

2. **Le rendre téléchargeable** :
   - Copie `app-debug.apk` dans le dossier **`downloads/`** de ce projet.
   - Renomme-le en **`locally-android.apk`**.
   - La page `download-locally-android.html` pointe déjà vers `downloads/locally-android.apk`.

3. **Servir la page** pour tester sur ton Android :
   - Depuis la racine du projet :  
     `npx serve -p 8080`  
     puis sur ton téléphone : `http://IP_DE_TON_PC:8080/download-locally-android.html`
   - Ou héberge le dossier (GitHub Pages, etc.) et ouvre l’URL du site sur ton Android.

---

## Installer l’APK sur Android

Après le téléchargement : ouvre le fichier (Notifications ou Gestionnaire de fichiers).  
Si Android demande d’autoriser les « sources inconnues », accepte pour cette installation.
