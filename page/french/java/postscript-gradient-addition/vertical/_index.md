---
title: Ajouter un dégradé vertical en Java PostScript
linktitle: Ajouter un dégradé vertical en Java PostScript
second_title: API Java Aspose.Page
description: Explorez le guide étape par étape pour ajouter des dégradés verticaux dans Java PostScript avec Aspose.Page pour Java. Améliorez vos documents sans effort avec des visuels éclatants.
weight: 14
url: /fr/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé vertical en Java PostScript

## Introduction
Bienvenue dans ce guide étape par étape sur l'ajout d'un dégradé vertical dans Java PostScript à l'aide d'Aspose.Page pour Java. Si vous souhaitez agrémenter votre document avec des dégradés accrocheurs, ce tutoriel est fait pour vous. Aspose.Page pour Java fournit des outils puissants pour manipuler les documents PostScript de manière transparente.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé sur votre machine.
-  Aspose.Page pour la bibliothèque Java. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/java/).
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour commencer :
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Maintenant, décomposons le processus d'ajout d'un dégradé vertical dans Java PostScript en plusieurs étapes.
## Étape 1 : Configurez votre répertoire de documents
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
```
## Étape 2 : Créer un flux de sortie pour un document PostScript
```java
// Créer un flux de sortie pour un document PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Étape 3 : Créer des options d'enregistrement au format A4
```java
// Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();
```
## Étape 4 : Créer un nouveau document PS
```java
// Créer un nouveau document PS avec la page ouverte
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Étape 5 : Créer un rectangle
```java
//Créer un rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Étape 6 : Configurer les couleurs et les fractions pour le dégradé
```java
// Créez des tableaux de couleurs et de fractions pour le dégradé.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Étape 7 : Créer la transformation de dégradé
```java
// Créez la transformation de dégradé. Les composants d'échelle dans la transformation doivent être égaux à la largeur et à la hauteur du rectangle.
// Les composants de translation sont des décalages du rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Faire pivoter le dégradé de 90 degrés autour d'une origine
transform.rotate(90 * (Math.PI / 180));
```
## Étape 8 : Créer une peinture à dégradé linéaire vertical
```java
// Créez une peinture à dégradé linéaire vertical.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Étape 9 : définir la peinture et remplir le rectangle
```java
// Définir la peinture
document.setPaint(paint);
// Remplissez le rectangle
document.fill(rectangle);
```
## Étape 10 : Fermez la page actuelle et enregistrez le document
```java
// Fermer la page actuelle
document.closePage();
// Enregistrez le document
document.save();
```
Toutes nos félicitations! Vous avez réussi à ajouter un dégradé vertical à votre document Java PostScript à l'aide d'Aspose.Page pour Java.
## Conclusion
Dans ce didacticiel, nous avons exploré le processus d'amélioration de vos documents avec des dégradés verticaux vibrants à l'aide d'Aspose.Page pour Java. Désormais, vous pouvez faire passer vos manipulations de documents au niveau supérieur en incorporant des visuels époustouflants.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Page pour Java avec d’autres bibliothèques Java ?
Oui, Aspose.Page pour Java est conçu pour fonctionner de manière transparente avec d'autres bibliothèques Java.
### Existe-t-il un essai gratuit disponible pour Aspose.Page pour Java ?
 Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver de la documentation supplémentaire ?
 Une documentation détaillée est disponible[ici](https://reference.aspose.com/page/java/).
### Comment puis-je acheter Aspose.Page pour Java ?
 Vous pouvez acheter Aspose.Page pour Java[ici](https://purchase.aspose.com/buy).
### Existe-t-il un forum pour les discussions sur Aspose.Page ?
 Oui, vous pouvez rejoindre le forum communautaire[ici](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
