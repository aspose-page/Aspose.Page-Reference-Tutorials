---
title: Ajouter des métadonnées dans XMP à l'aide de Java
linktitle: Ajouter des métadonnées dans XMP à l'aide de Java
second_title: API Java Aspose.Page
description: Explorez l'intégration transparente d'Aspose.Page pour Java et découvrez comment ajouter facilement des métadonnées XMP à vos fichiers EPS. Améliorez votre jeu de gestion de documents dès aujourd'hui !
type: docs
weight: 11
url: /fr/java/xmp-metadata-manipulation/add-metadata/
---
## Introduction
Cherchez-vous à améliorer les métadonnées de votre document en ajoutant des informations XMP à l'aide de Java ? Cherchez pas plus loin! Ce guide étape par étape vous guidera tout au long du processus d'ajout de métadonnées à un fichier EPS à l'aide de la bibliothèque Aspose.Page pour Java. Aspose.Page est un outil puissant qui simplifie les tâches de manipulation de documents dans les applications Java.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Connaissance de base de la programmation Java.
-  Aspose.Page pour la bibliothèque Java installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/java/).
- Un fichier EPS que vous souhaitez modifier.
## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre programme Java :
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Étape 1 : Obtenez les métadonnées XMP
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Initialiser le flux de fichiers EPS d'entrée
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Obtenez les métadonnées XMP. Si le fichier EPS ne contient pas de métadonnées XMP, une nouvelle est créée en utilisant les valeurs des commentaires de métadonnées PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel où vos documents sont stockés.

## Étape 2 : Récupérer la valeur CreatorTool
```java
// Obtenir la valeur "CreatorTool"
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Étape 3 : Récupérer la valeur CreateDate
```java
// Obtenir la valeur "CreateDate"
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Étape 4 : Récupérer la valeur du titre
```java
// Obtenez la valeur "Titre"
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Étape 5 : Récupérer la valeur du format
```java
//Obtenir la valeur "format"
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Étape 6 : Récupérer la valeur du créateur
```java
// Obtenez la valeur "créateur"
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Étape 7 : Récupérer la valeur MetadataDate
```java
// Obtenir la valeur "MetadataDate"
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Étape 8 : Enregistrer le document avec les nouvelles métadonnées XMP
```java
// Initialiser le flux de fichiers EPS de sortie
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Enregistrer le document avec les nouvelles métadonnées XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Enfin, n'oubliez pas de fermer le flux EPS d'entrée :
```java
// Fermer le flux EPS d’entrée
psStream.close();
```
Vous avez maintenant ajouté avec succès des métadonnées à votre fichier EPS à l’aide d’Aspose.Page pour Java !
## Conclusion
Dans ce didacticiel, nous avons exploré le processus d'ajout de métadonnées XMP à un fichier EPS à l'aide de la bibliothèque Aspose.Page pour Java. Cet outil puissant vous permet de manipuler des documents de manière transparente, améliorant ainsi votre expérience globale de gestion de documents.
## FAQ
### Q : L'utilisation d'Aspose.Page pour Java est-elle gratuite ?
 R : Aspose.Page pour Java est un produit commercial. Vous pouvez explorer ses fonctionnalités grâce à un essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver la documentation d'Aspose.Page pour Java ?
 R : La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 R : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Quels formats de fichiers Aspose.Page pour Java prend-il en charge ?
R : Aspose.Page pour Java prend en charge divers formats, notamment EPS, PDF et XPS.
### Q : Puis-je acheter Aspose.Page pour Java ?
 R : Oui, vous pouvez acheter Aspose.Page pour Java[ici](https://purchase.aspose.com/buy).