# APK Expansion Files

## But du TD
Quand une application fait plus de 100Mo, Google conseil d'utiliser des fichiers OBB pour externaliser les ressources.
Nous allons voir comment générer un OBB et comment l'intégrer dans le projet.

## Etapes
### Créer un projet
Créer un projet basé sur le template *Empty Activity*

### Créer un fichier OBB
1. Tu vas créer un fichier OBB disposant du contenu du zip content/content.zip.
2. Ensuite, tu devras implémenter un *StorageManager* pour transformer l'OBB en point de montage.   
3. Bacule le contenu du fichier *data.json* se trouvant dans l'OBB vers le TextView de l'Activity.

## Documentation
* [Create OBB File](https://developer.android.com/studio/command-line/jobb)
* [APK Expansion Files](https://developer.android.com/google/play/expansion-files)
* [StorageManager](https://developer.android.com/reference/android/os/storage/StorageManager)
* [getObbDir](https://developer.android.com/reference/android/content/Context.html#getObbDir())
