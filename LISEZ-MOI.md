# HES CHECK : APK (site inclus dans l'appli)

```
hescheck-apk/
├─ www/
│  ├─ index.html        ← route « / » : le site Check Ban complet (c'est ici qu'on le modifie)
│  ├─ offline.html      ← page « Problème de connexion » (+ offline.webp)
├─ capacitor.config.json  (appId com.hescheck.app · nom HES CHECK · webDir = www)
├─ package.json
└─ .github/workflows/build-apk.yml   (compile HESCHECK.apk)
```

- L'appli ouvre `www/index.html` : le site est dans l'APK. Pour le changer, remplace `www/index.html` puis relance le build.
- Les vérifications appellent `https://he-s-shop-v2.skyhost.tech/api/checkban` (constante `API` en haut du script de `www/index.html`).
- Pour d'autres pages, ajoute-les dans `www/` (ex. `www/aide.html` → lien `aide.html`).
- Variante en ligne (le site se met à jour sans rebuild) : dans `capacitor.config.json`, remplace `"server"` par
  `{"url":"https://check-hes.vercel.app/","androidScheme":"https","allowNavigation":["check-hes.vercel.app","he-s-shop-v2.skyhost.tech"],"errorPath":"offline.html"}`.

## Compiler
1. Envoie tout ce dossier sur GitHub (avec `.github`).
2. Actions → Build APK → Run workflow.
3. Télécharge `HESCHECK.apk` dans Releases.
