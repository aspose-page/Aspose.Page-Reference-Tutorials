---
title: Ajouter des éléments de tableau dans les métadonnées XMP à l'aide de Java
linktitle: Ajouter des éléments de tableau dans les métadonnées XMP à l'aide de Java
second_title: API Java Aspose.Page
description: Améliorez les fichiers EPS avec Aspose.Page pour Java. Apprenez à ajouter des éléments de tableau aux métadonnées XMP sans effort. Suivez notre guide étape par étape dès maintenant !
type: docs
weight: 10
url: /fr/java/xmp-metadata-manipulation/add-array-items/
---
## Introduction
Bienvenue dans notre guide étape par étape sur l'utilisation d'Aspose.Page pour Java pour ajouter des éléments de tableau dans les métadonnées XMP. Aspose.Page est une puissante bibliothèque Java qui vous permet de manipuler et de travailler avec différents formats de documents, y compris les fichiers EPS. Dans ce didacticiel, nous nous concentrerons sur la tâche spécifique consistant à ajouter des éléments de tableau dans les métadonnées XMP à l'aide de Java.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Aspose.Page pour la bibliothèque Java installée.
- Compréhension de base de la programmation Java.
- Un fichier EPS valide avec des métadonnées XMP existantes ou des commentaires sur les métadonnées PS.
## Importer des packages
Pour commencer, vous devez importer les packages nécessaires pour travailler avec Aspose.Page. Incluez les lignes suivantes au début de votre fichier Java :
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Étape 1 : Obtenez les métadonnées XMP
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Initialiser le flux de fichiers EPS d'entrée
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Obtenez les métadonnées XMP. Si le fichier EPS ne contient pas de métadonnées XMP, nous en obtenons une nouvelle remplie de valeurs provenant des commentaires de métadonnées PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Dans cette étape, nous récupérons les métadonnées XMP existantes du fichier EPS. Si le fichier EPS ne contient pas déjà de métadonnées XMP, Aspose.Page en génère une nouvelle et le remplit avec les valeurs des commentaires de métadonnées PS.
## Étape 2 : Ajouter un élément de tableau « dc:title »
```java
// Ajouter un autre élément de tableau "dc:title"
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Maintenant, nous ajoutons un nouvel élément de tableau à la propriété « dc:title » dans les métadonnées XMP. Remplacez "NewTitle" par le titre souhaité.
## Étape 3 : ajouter un élément de tableau « dc:creator »
```java
// Ajouter un autre élément de tableau "dc:creator"
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
De même, nous ajoutons un nouvel élément de tableau à la propriété « dc:creator » dans les métadonnées XMP. Remplacez "NewCreator" par les informations de créateur souhaitées.
## Étape 4 : initialiser le flux de fichiers EPS de sortie
```java
// Initialiser le flux de fichiers EPS de sortie
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Préparez le flux de fichier EPS de sortie dans lequel le document modifié avec les métadonnées XMP mises à jour sera enregistré.
## Étape 5 : Enregistrer le document avec les métadonnées XMP modifiées
```java
//Enregistrer le document avec les métadonnées XMP modifiées
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Enregistrez le document avec les métadonnées XMP mises à jour dans le fichier EPS de sortie.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter des éléments de tableau dans les métadonnées XMP à l'aide d'Aspose.Page pour Java. Cette puissante bibliothèque simplifie le processus de manipulation des fichiers EPS et fournit des fonctionnalités étendues pour le traitement des documents.
## Questions fréquemment posées

### Puis-je utiliser Aspose.Page pour Java avec d’autres formats de document ?
Oui, Aspose.Page prend en charge divers formats de documents, notamment EPS, PDF et XPS.
### Existe-t-il un essai gratuit disponible pour Aspose.Page pour Java ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver la documentation d’Aspose.Page pour Java ?
 La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Comment puis-je acheter Aspose.Page pour Java ?
 Vous pouvez acheter le produit[ici](https://purchase.aspose.com/buy).
### Des licences temporaires sont-elles disponibles pour Aspose.Page pour Java ?
 Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).