---
title: Dégradé radial Java PostScript avec Aspose.Page
linktitle: Dégradé radial Java PostScript avec Aspose.Page
second_title: API Java Aspose.Page
description: Explorez le guide étape par étape pour ajouter un dégradé radial dans Java PostScript à l'aide d'Aspose.Page pour des graphismes époustouflants dans vos applications Java.
type: docs
weight: 13
url: /fr/java/postscript-gradient-addition/radial2/
---
## Introduction
Bienvenue dans notre guide étape par étape sur l'ajout de Radial Gradient 2 dans Java PostScript à l'aide d'Aspose.Page pour Java. Ce didacticiel vous guidera tout au long du processus de création d'un document PostScript avec un magnifique dégradé radial, améliorant ainsi vos applications Java avec des graphiques visuellement attrayants.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une connaissance pratique de la programmation Java.
- Kit de développement Java (JDK) installé sur votre ordinateur.
-  Bibliothèque Aspose.Page pour Java, que vous pouvez télécharger à partir du[Documentation Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Page :
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Étape 1 : configurer le répertoire de documents
Définissez le chemin d'accès à votre répertoire de documents :
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : Créer un flux de sortie
Créez un flux de sortie pour le document PostScript :
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Étape 3 : Créer des options de sauvegarde
Créez des options de sauvegarde au format A4 :
```java
PsSaveOptions options = new PsSaveOptions();
```
## Étape 4 : Créer un document PS
Créez un nouveau document PS avec la page ouverte :
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Étape 5 : Créer un cercle
Définissez un cercle à l'aide de la classe Ellipse2D.Float :
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Étape 6 : Définir les couleurs du dégradé
Créez des tableaux de couleurs et de fractions pour le dégradé radial :
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Étape 7 : Créer AffineTransform
Créez un AffineTransform pour le dégradé radial :
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Étape 8 : Créer une peinture à dégradé radial
Créez un RadialGradientPaint avec les paramètres spécifiés :
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Étape 9 : Définir le cercle de peinture et de remplissage
Fixez la peinture et remplissez le cercle avec le dégradé radial :
```java
document.setPaint(paint);
document.fill(circle);
```
## Étape 10 : Fermer la page et enregistrer le document
Fermez la page actuelle et enregistrez le document :
```java
document.closePage();
document.save();
```
Toutes nos félicitations! Vous avez ajouté avec succès Radial Gradient 2 dans Java PostScript à l'aide d'Aspose.Page pour Java.
## Conclusion
Dans ce didacticiel, nous avons exploré comment améliorer vos applications Java avec des dégradés radiaux dans les documents PostScript. Aspose.Page pour Java fournit un ensemble d'outils puissants pour créer des graphiques époustouflants, vous permettant de faire passer vos projets Java au niveau supérieur.
## FAQ
### Q : Où puis-je trouver la documentation d'Aspose.Page pour Java ?
 R : La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Q : Comment puis-je télécharger Aspose.Page pour Java ?
 R : Vous pouvez le télécharger à partir du[page des versions](https://releases.aspose.com/page/java/).
### Q : Existe-t-il un essai gratuit ?
 R : Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 R : Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je rechercher le soutien de la communauté et participer aux discussions ?
 R : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39).