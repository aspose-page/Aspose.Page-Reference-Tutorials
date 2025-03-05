---
title: Ajouter des propriétés simples dans XMP à l'aide de Java
linktitle: Ajouter des propriétés simples dans XMP à l'aide de Java
second_title: API Java Aspose.Page
description: Libérez le potentiel d'Aspose.Page pour Java avec notre guide sur l'ajout de propriétés aux métadonnées XMP dans les fichiers EPS. Améliorez le traitement des documents sans effort !
type: docs
weight: 14
url: /fr/java/xmp-metadata-manipulation/add-simple-properties/
---
## Introduction
Dans le paysage en constante évolution du traitement des documents, la gestion efficace des métadonnées est cruciale. Aspose.Page pour Java permet aux développeurs de manipuler les données de la plate-forme de métadonnées extensible (XMP) de manière transparente. Dans ce didacticiel, nous explorerons le processus d'ajout de propriétés simples à XMP à l'aide de Java, en vous fournissant un guide complet étape par étape.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Connaissance de base de la programmation Java.
-  Aspose.Page pour la bibliothèque Java installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/java/).
- Un exemple de fichier EPS contenant des métadonnées. Si vous n'en avez pas, n'hésitez pas à utiliser le fichier "xmp3.eps" fourni.
## Importer des packages
Assurez-vous d'importer les packages nécessaires pour démarrer votre projet :
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
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
## Étape 2 : ajouter une propriété de date
```java
// Ajouter la valeur de la propriété de date "xmp:Date1"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Étape 3 : ajouter une propriété entière
```java
// Ajouter la valeur de la propriété entière "xmp: Intg1"
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Étape 4 : ajouter une propriété double
```java
// Ajouter la valeur de la propriété double "xmp:Double1"
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Étape 5 : ajouter une propriété de chaîne
```java
// Ajouter la valeur de la propriété de chaîne "xmp:String1"
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Étape 6 : Enregistrer le document
```java
// Initialiser le flux de fichiers EPS de sortie
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Enregistrer le document avec les métadonnées XMP modifiées
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Étape 7 : Fermer les flux
```java
// Fermer le flux EPS d’entrée
psStream.close();
```
## Conclusion
Aspose.Page pour Java simplifie le processus de manipulation des métadonnées XMP dans les fichiers EPS. En suivant ce guide étape par étape, vous pouvez facilement ajouter des propriétés simples pour améliorer les métadonnées de votre document.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Page pour Java avec d’autres langages de programmation ?
Aspose.Page prend principalement en charge Java, mais des versions sont disponibles pour d'autres langages comme .NET.
### Un essai gratuit est-il disponible pour Aspose.Page pour Java ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.Page en obtenant un essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver une documentation détaillée pour Aspose.Page pour Java ?
 La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 Un permis temporaire peut être acquis[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter Aspose.Page pour Java ?
 Vous pouvez acheter le produit[ici](https://purchase.aspose.com/buy).