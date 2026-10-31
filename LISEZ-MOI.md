# HES CHECK : APK

Même méthode que HES STORE : l'appli ouvre https://check-hes.vercel.app/ (rien à reconstruire quand tu modifies le site).

1. Crée un dépôt GitHub et envoie tout ce dossier (y compris `.github`).
2. Onglet **Actions** → **Build APK** → **Run workflow** (se lance aussi à chaque push).
3. Une fois fini (~5 min), télécharge `HESCHECK.apk` dans **Releases** (lien direct) ou dans les artefacts de l'exécution.

Inclus, comme HES STORE : page « Problème de connexion » avec retour automatique, fenêtres du site ouvertes dans l'appli, téléchargements, confirmation en quittant, message WhatsApp au premier lancement.
Plus : le plugin presse-papiers Capacitor, pour que **Autofill** colle le pseudo sans blocage.

## Intro vidéo
L'appli joue d'abord `www/hescheck-intro.mp4` (bouton « Passer »), puis ouvre https://check-hes.vercel.app/. Pour cela, `server.url` a été retiré de `capacitor.config.json` : `www/index.html` se lance en premier.

## Bouton S'abonner
Au premier lancement, la fenêtre « Abonne-toi à la chaîne WhatsApp » a un bouton **S'abonner** au style de « Ajouter maintenant » (dégradé bleu-vert → vert, texte sombre gras), en plus petit (200 × 44 dp). Modifié dans `.github/workflows/build-apk.yml` (méthode `showFollowGate`).

## Liens
Les liens web s'ouvrent dans l'appli (fenêtre interne avec ✕), sans montrer le navigateur. Les liens WhatsApp (chaîne, wa.me) ouvrent directement l'appli WhatsApp : si WhatsApp et WhatsApp Business sont installés, Android propose de choisir. Les liens Telegram ouvrent l'appli Telegram.
