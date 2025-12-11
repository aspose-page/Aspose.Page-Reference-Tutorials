---
date: 2025-12-07
description: Apprenez à ajouter un dégradé horizontal dans Java PostScript en utilisant
  Linear Gradient Paint Java avec Aspose.Page pour Java.
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Ajouter un dégradé dans Java PostScript en utilisant Linear Gradient Paint
  Java
url: /fr/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé en Java PostScript avec Linear Gradient Paint Java

## Introduction
Dans ce tutoriel complet, vous découvrirez comment créer un magnifique dégradé horizontal dans un document PostScript en exploitant **Linear Gradient Paint Java**. Aspose.Page for Java simplifie le travail avec PostScript, PDF et d’autres formats vectoriels, et la classe `LinearGradientPaint` vous offre un contrôle précis sur les transitions de couleur. À la fin de ce guide, vous serez capable de rendre des dégradés sur des formes **et** du texte, donnant à vos documents un aspect professionnel et accrocheur.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (prend en charge Linear Gradient Paint Java).  
- **Combien de temps faut‑il pour implémenter ?** Environ 10‑15 minutes pour un dégradé de base.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production.  
- **Quelle version du JDK fonctionne ?** Java 8 ou supérieur.  
- **Puis‑je utiliser le dégradé sur les formes et le texte ?** Oui – vous pouvez remplir des formes et tracer ou remplir du texte avec le même dégradé.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importer les packages
Commencez par importer les packages nécessaires dans votre projet Java. Ces imports vous donnent accès aux primitives graphiques, à la gestion des dégradés et à l’API Aspose.Page.

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

## Étape 1 : Créer un rectangle
Tout d’abord, configurez le flux de sortie, le document et un rectangle qui accueillera le dégradé.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Étape 2 : Créer un Linear Gradient Paint horizontal
Ici nous construisons l’objet **Linear Gradient Paint Java** qui définit une transition de couleur horizontale. L’`AffineTransform` met à l’échelle le dégradé pour correspondre à la largeur et à la hauteur du rectangle.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Étape 3 : Remplir le rectangle
Remplissez maintenant le rectangle avec le dégradé que nous venons de définir.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Étape 4 : Remplir du texte avec le dégradé
Vous pouvez également appliquer le même dégradé au texte, créant ainsi un effet visuel saisissant.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Étape 5 : Tracer du texte avec le dégradé
Enfin, contournez le texte en utilisant le dégradé comme couleur de trait.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le dégradé apparaît étiré | Échelle `AffineTransform` incorrecte | Assurez‑vous que la largeur et la hauteur du transform correspondent aux dimensions du rectangle (200 × 100 dans l’exemple). |
| Les couleurs semblent délavées | Valeurs alpha trop faibles | Augmentez le composant alpha (la quatrième valeur dans `new Color(r,g,b,alpha)`). |
| Le texte n’est pas visible | Paint non défini avant le dessin du texte | Appelez `document.setPaint(paint)` **avant** tout appel à `fillAndStrokeText` ou `outlineText`. |

## Foire aux questions
### Puis‑je utiliser Aspose.Page for Java dans des projets commerciaux ?
Oui, Aspose.Page for Java peut être utilisé dans des projets commerciaux. Pour les détails de licence, consultez [Aspose.Purchase](https://purchase.aspose.com/buy).

### Existe‑t‑il un essai gratuit disponible ?
Oui, vous pouvez accéder à un essai gratuit d’Aspose.Page for Java [ici](https://releases.aspose.com/).

### Où puis‑je trouver une documentation supplémentaire et du support ?
Visitez la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/) pour des ressources complètes. Pour le support communautaire, consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39).

### Comment obtenir une licence temporaire ?
Vous pouvez obtenir une licence temporaire depuis [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Quelles sont les exigences système pour Aspose.Page for Java ?
Reportez‑vous à la [documentation](https://reference.aspose.com/page/java/) pour les exigences système détaillées.

---

**Dernière mise à jour :** 2025-12-07  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}