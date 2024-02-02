---
title: Ajouter un dégradé horizontal en Java PostScript
linktitle: Ajouter un dégradé horizontal en Java PostScript
second_title: API Java Aspose.Page
description: Découvrez comment ajouter un dégradé horizontal dans Java PostScript avec Aspose.Page pour Java. Créez sans effort des documents visuellement époustouflants.
type: docs
weight: 11
url: /fr/java/postscript-gradient-addition/horizontal/
---
## Introduction
Bienvenue dans ce didacticiel complet sur l'ajout d'un dégradé horizontal dans Java PostScript à l'aide d'Aspose.Page pour Java. Aspose.Page est une puissante bibliothèque Java qui permet aux développeurs de travailler avec PostScript et d'autres formats de documents. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un document PostScript avec un dégradé horizontal à l'aide d'exemples étape par étape.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
- Kit de développement Java (JDK) installé sur votre machine.
- Aspose.Page pour la bibliothèque Java. Vous pouvez le télécharger depuis le[Documentation Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importer des packages
Commencez par importer les packages nécessaires dans votre projet Java. Ces packages sont cruciaux pour travailler avec Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Étape 1 : Créer un rectangle
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer un flux de sortie pour un document PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();
// Créer un nouveau document PS avec la page ouverte
PsDocument document = new PsDocument(outPsStream, options, false);
//Créer un rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Étape 2 : Créer une peinture à dégradé linéaire horizontal
```java
// Créez une peinture à dégradé linéaire horizontal. Les composants d'échelle dans la transformation doivent être égaux à la largeur et à la hauteur du rectangle.
// Les composants de translation sont des décalages du rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Définir la peinture
document.setPaint(paint);
```
## Étape 3 : remplir le rectangle
```java
// Remplissez le rectangle
document.fill(rectangle);
```
## Étape 4 : remplir un texte avec le dégradé
```java
// Remplir un texte avec le dégradé
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Étape 5 : tracer un texte avec le dégradé
```java
// Tracez un texte avec le dégradé
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusion
Toutes nos félicitations! Vous avez ajouté avec succès un dégradé horizontal dans Java PostScript à l'aide d'Aspose.Page pour Java. Ce didacticiel vous a fourni un guide détaillé étape par étape pour vous aider à créer des documents PostScript visuellement attrayants.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Page pour Java dans des projets commerciaux ?
Oui, Aspose.Page pour Java peut être utilisé dans des projets commerciaux. Pour plus de détails sur les licences, visitez[Aspose.Achat](https://purchase.aspose.com/buy).
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez accéder à un essai gratuit d'Aspose.Page pour Java[ici](https://releases.aspose.com/).
### Où puis-je trouver de la documentation et une assistance supplémentaires ?
 Visiter le[Documentation Java Aspose.Page](https://reference.aspose.com/page/java/) pour des ressources complètes. Pour le soutien de la communauté, consultez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39).
### Comment puis-je obtenir un permis temporaire ?
 Vous pouvez obtenir une licence temporaire auprès de[Aspose.Achat](https://purchase.aspose.com/temporary-license/).
### Quelle est la configuration système requise pour Aspose.Page pour Java ?
 Se référer au[Documentation](https://reference.aspose.com/page/java/) pour connaître la configuration système requise détaillée.