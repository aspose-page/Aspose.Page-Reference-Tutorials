---
date: 2025-12-09
description: Apprenez à créer un dégradé PostScript en Java avec Aspose.Page. Ce guide
  étape par étape vous montre comment ajouter facilement un dégradé vertical à vos
  documents PostScript.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Créer un dégradé PostScript en Java – Ajouter un dégradé vertical
url: /fr/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}

# Créer un dégradé PostScript en Java – Ajouter un dégradé vertical

## Introduction
Dans ce tutoriel complet, vous apprendrez comment **créer un dégradé PostScript en Java** avec Aspose.Page for Java. Ajouter un dégradé vertical peut rendre vos documents plus dynamiques et professionnels, et avec seulement quelques lignes de code vous pouvez obtenir des effets visuels époustouflants. Nous vous guiderons à travers chaque étape, expliquerons pourquoi chaque élément est important, et vous donnerons des conseils pratiques pour éviter les pièges courants.  
Dans ce guide nous allons **créer un dégradé postscript java** étape par étape.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## Prerequisites
Avant de plonger dans le tutoriel, assurez-vous d'avoir les prérequis suivants en place :
- Java Development Kit (JDK) installé sur votre machine.  
- Aspose.Page for Java library. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).

## Import Packages
Dans votre projet Java, importez les packages nécessaires pour commencer :
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

Maintenant, détaillons le processus d'ajout d'un dégradé vertical dans le PostScript Java en plusieurs étapes.

## How to create PostScript gradient Java
Voici un guide étape par étape qui montre exactement comment **créer un dégradé PostScript en Java** en utilisant l'API Aspose.Page.

### Step 1: Set up Your Document Directory
Étape 1 : Configurer le répertoire de votre document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
Étape 2 : Créer le flux de sortie pour le document PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
Étape 3 : Créer les options d'enregistrement avec la taille A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
Étape 4 : Créer un nouveau document PS
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
Étape 5 : Créer un rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
Étape 6 : Configurer les couleurs et les fractions pour le dégradé
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
Étape 7 : Créer la transformation du dégradé
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
Étape 8 : Créer la peinture de dégradé linéaire vertical
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
Étape9 : Définir la peinture et remplir le rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
Étape 10 : Fermer la page actuelle et enregistrer le document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Félicitations ! Vous avez ajouté avec succès un dégradé vertical à votre document PostScript Java en utilisant Aspose.Page for Java.

## Why use vertical gradients in PostScript?
Pourquoi utiliser des dégradés verticaux dans le PostScript ?
- En‑têtes et pieds de page de rapports  
- Remplissages d'arrière‑plan pour graphiques ou diagrammes  
- Mise en évidence de sections dans les documents techniques  

## Common Issues and Solutions
Problèmes courants et solutions
- **Gradient appears flat:** Le dégradé apparaît plat : assurez‑vous que le redimensionnement `AffineTransform` correspond aux dimensions du rectangle.  
- **Colors look washed out:** Les couleurs semblent délavées : vérifiez que vous utilisez le bon `ColorSpaceType` (SRGB) et que le tableau des fractions est ordonné de 0.0 à 1.0.  
- **File not generated:** Le fichier n'est pas généré : vérifiez que le répertoire de sortie (`dataDir`) existe et que l'application possède les permissions d'écriture.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Oui, Aspose.Page for Java est conçu pour fonctionner de manière transparente avec d'autres bibliothèques Java.

### Is there a free trial available for Aspose.Page for Java?
Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Where can I find additional documentation?
La documentation détaillée est disponible [ici](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
Vous pouvez acheter Aspose.Page for Java [ici](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Oui, vous pouvez rejoindre le forum communautaire [ici](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
R : Absolument. Ajustez les points de départ et d'arrivée dans `LinearGradientPaint` et modifiez l'angle de rotation dans `AffineTransform`.

**Q: Does this work with PDF output as well?**  
R : La même logique de dégradé peut être appliquée lors de l'enregistrement en PDF en utilisant `PdfSaveOptions` au lieu de `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
R : Calculez les dimensions du rectangle à l'exécution et transmettez ces valeurs à la fois au constructeur `Rectangle2D` et à celui de `AffineTransform`.

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Page for Java 24.11 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}