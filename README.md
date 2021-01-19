# APK Expansion Files

## But du TD
Quand une application fait plus de 100Mo, Google conseil d'utiliser des fichiers OBB pour externaliser les ressources.
Nous allons voir comment générer une archive OBB et comment l'intégrer dans un projet.

## Etapes
### Créer un projet
Créer un projet basé sur le template *Empty Activity*

### Créer un fichier OBB
* Tu vas [créer un fichier OBB](https://developer.android.com/studio/command-line/jobb) disposant du contenu du fichier zip *content.zip*.
* Le nom du fichier devra respecter le format suivant :
```main.<expansion-version>.<package-name>.obb``` 
* Une fois créé, il faudra le mettre dans le *device* à l'emplacement suivant :
```storage/emulated/0/Android/obb/<package-name>/```

Pour copier un fichier dans le *device* on peut utiliser l'outil [adb](https://developer.android.com/studio/command-line/adb). 
* Voici la ligne à taper dans un terminal pour copier le fichier :
```adb push main.<expansion-version>.<package-name>.obb /storage/emulated/0/Android/obb/<package-name>/```

### StorageManager
* Ensuite, tu devras implémenter un [StorageManager](https://developer.android.com/reference/android/os/storage/StorageManager) pour transformer l'OBB en point de montage.   
* Une fois monté, bascule le contenu du fichier *data.json* de l'OBB vers le TextView de l'Activity.

N'oublie pas d'ajouter les autorisations suivantes dans le fichier AndroidManifest.xml
```java
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>  
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```
## Documentation
* [Create OBB File](https://developer.android.com/studio/command-line/jobb)
* [APK Expansion Files](https://developer.android.com/google/play/expansion-files)
* [StorageManager](https://developer.android.com/reference/android/os/storage/StorageManager)
* [getObbDir](https://developer.android.com/reference/android/content/Context.html#getObbDir())

## TD suivant
* [JSON](https://github.com/boutin-k/dojo-android-audio-07-json)
