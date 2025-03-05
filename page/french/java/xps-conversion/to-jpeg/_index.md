---
title: Convertir XPS en JPEG en Java
linktitle: Convertir XPS en JPEG en Java
second_title: API Java Aspose.Page
description: Découvrez comment convertir XPS en JPEG en Java à l'aide d'Aspose.Page. Un guide complet avec des instructions étape par étape pour une intégration transparente.
type: docs
weight: 11
url: /fr/java/xps-conversion/to-jpeg/
---
## Introduction
Dans ce didacticiel, nous allons explorer comment convertir des fichiers XPS (XML Paper Spécification) en images JPEG à l'aide d'Aspose.Page pour Java. Aspose.Page est une puissante bibliothèque Java qui permet aux développeurs de travailler de manière transparente avec XPS et d'autres formats de documents. Ce guide étape par étape vous aidera à comprendre le processus et à l'implémenter dans vos applications Java.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Environnement de développement Java : assurez-vous d'avoir configuré un environnement de développement Java sur votre ordinateur.
-  Bibliothèque Aspose.Page pour Java : téléchargez et installez la bibliothèque Aspose.Page pour Java. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/page/java/).
- Exemple de document XPS : disposez d'un exemple de document XPS que vous souhaitez convertir en JPEG.
## Importer des packages
Commencez par importer les packages nécessaires dans votre classe Java :
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Étape 1 : initialiser les chemins et le document XPS
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Initialiser le flux d'entrée XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Étape 2 : définir les options JpegSaveOptions
```java
// Initialisez l'objet d'options avec les paramètres nécessaires.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Étape 3 : Créer un périphérique de rendu
```java
// Créer un périphérique de rendu pour le format PDF
ImageDevice device = new ImageDevice();
```
## Étape 4 : Enregistrez XPS au format JPEG
```java
document.save(device, options);
```
## Étape 5 : Itérer et enregistrer les pages JPEG
```java
//Parcourez les partitions de documents (documents fixes, en termes XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Parcourir les pages de partition
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialiser le flux de sortie d'image
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Écrire une image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //fermer le flux
        imageStream.close();
    }
}
```
Cette série d'étapes convertira efficacement votre document XPS en images JPEG, chacune enregistrée séparément.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment convertir XPS en JPEG en Java à l'aide d'Aspose.Page. Ce processus est inestimable pour les développeurs travaillant sur la conversion de documents dans des applications Java.
## Questions fréquemment posées

### Q : Aspose.Page est-il adapté aux projets commerciaux ?
 R : Oui, Aspose.Page est un produit commercial avec des options de licence disponibles. Vérifier[ici](https://purchase.aspose.com/buy) pour plus de détails.
### Q : Puis-je essayer Aspose.Page avant d'acheter ?
 R : Oui, vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver la documentation Aspose.Page ?
 R : La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Q : Comment puis-je obtenir de l'aide pour Aspose.Page ?
 R : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour un soutien communautaire.
### Q : Ai-je besoin d’une licence temporaire pour effectuer des tests ?
 R : Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).