---
title: Convertir XPS en PNG en Java
linktitle: Convertir XPS en PNG en Java
second_title: API Java Aspose.Page
description: Convertissez sans effort XPS en PNG en Java à l’aide d’Aspose.Page. Rationalisez les tâches documentaires avec cette solution fiable et conviviale pour les développeurs.
type: docs
weight: 13
url: /fr/java/xps-conversion/to-png/
---
## Introduction
Dans le monde dynamique du développement de logiciels, le besoin de convertir des documents XPS (XML Paper Spécification) en images PNG (Portable Network Graphics) se pose fréquemment. Pour accomplir cette tâche de manière transparente en Java, Aspose.Page fournit une solution puissante. Dans ce didacticiel, nous allons parcourir le processus de conversion de XPS en PNG à l'aide d'Aspose.Page pour Java.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont configurées :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Page pour Java : téléchargez et installez la bibliothèque Aspose.Page. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/page/java/).
3. Environnement de développement intégré (IDE) : choisissez un IDE compatible Java comme IntelliJ IDEA ou Eclipse.
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour utiliser les fonctionnalités Aspose.Page. Ajoutez les instructions d'importation suivantes au début de votre fichier Java :
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Étape 1 : Définir le répertoire des documents
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
```
## Étape 2 : Charger le document XPS
```java
// Charger un document XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Étape 3 : initialiser les options
```java
// Initialisez l'objet d'options avec les paramètres nécessaires.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Étape 4 : Créer un périphérique de rendu
```java
// Créer un périphérique de rendu pour le format PDF
ImageDevice device = new ImageDevice();
```
## Étape 5 : Enregistrer et itérer
```java
// Enregistrer le document XPS au format PNG à l'aide des options et du périphérique
document.save(device, options);
//Parcourez les partitions de documents (documents fixes, en termes XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Parcourir les pages de partition
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialiser le flux de sortie d'image
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Écrire une image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Fermer le flux
        imageStream.close();
    }
}
```
En suivant ces étapes, vous pouvez facilement convertir des documents XPS en images PNG à l'aide d'Aspose.Page pour Java.
## Conclusion
En conclusion, Aspose.Page pour Java simplifie le processus de conversion XPS en PNG, offrant aux développeurs un outil fiable et efficace. Intégrez cette bibliothèque à vos projets Java pour rationaliser les tâches de manipulation de documents.
## FAQ
### Puis-je utiliser Aspose.Page pour Java dans des projets commerciaux ?
 Oui, Aspose.Page est un produit commercial. Vous pouvez trouver des informations sur les licences[ici](https://purchase.aspose.com/buy).
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez explorer un essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver la documentation d’Aspose.Page pour Java ?
 La documentation complète est disponible[ici](https://reference.aspose.com/page/java/).
### Comment puis-je obtenir une licence temporaire à des fins de test ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Existe-t-il des forums communautaires pour les discussions sur Aspose.Page ?
 Oui, visitez les forums communautaires[ici](https://forum.aspose.com/c/page/39).