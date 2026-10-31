# HES CHECK : APK

Même méthode que HES STORE : l'appli ouvre https://check-hes.vercel.app/ (rien à reconstruire quand tu modifies le site).

1. Crée un dépôt GitHub et envoie tout ce dossier (y compris `.github`).
2. Onglet **Actions** → **Build APK** → **Run workflow** (se lance aussi à chaque push).
3. Une fois fini (~5 min), télécharge `HESCHECK.apk` dans **Releases** (lien direct) ou dans les artefacts de l'exécution.

Inclus, comme HES STORE : page « Problème de connexion » avec retour automatique, fenêtres du site ouvertes dans l'appli, téléchargements, confirmation en quittant, message WhatsApp au premier lancement.
Plus : le plugin presse-papiers Capacitor, pour que **Autofill** colle le pseudo sans blocage.
