---
date: 2026-09-04
description: Apprenez à créer un dégradé horizontal java dans un fichier PostScript
  en utilisant Linear Gradient Paint Java avec Aspose.Page pour Java. Code étape par
  étape, pièges courants et FAQ.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Créer un dégradé horizontal java dans PostScript avec Aspose
og_description: Créer un dégradé horizontal java dans PostScript avec Linear Gradient
  Paint Java. Ce tutoriel Aspose.Page vous présente les étapes exactes, les prérequis
  et les conseils de dépannage en moins de 15 minutes.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Créer un dégradé horizontal java dans PostScript avec Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Créer un dégradé horizontal java dans PostScript avec Aspose
url: /fr/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé horizontal dans Java PostScript en utilisant Linear Gradient Paint

## Introduction
Dans ce tutoriel complet, vous apprendrez **comment créer un dégradé horizontal java** dans un document PostScript en utilisant la classe **Linear Gradient Paint Java** fournie avec Aspose.Page for Java. Nous parcourrons chaque étape — de la configuration du projet à l’affichage du dégradé sur les formes et le texte — afin que vous puissiez produire des graphiques soignés, prêts à l’impression, en quelques minutes. Que vous construisiez un moteur de reporting, un outil d’automatisation de conception ou un pilote d’imprimante personnalisé, ce guide vous fournit le code exact dont vous avez besoin.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (inclut Linear Gradient Paint Java).  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un dégradé horizontal basique.  
- **Ai-je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production.  
- **Quelle version du JDK fonctionne ?** Java 8 ou supérieure.  
- **Puis-je utiliser le dégradé sur les formes et le texte ?** Oui – la même instance `LinearGradientPaint` peut remplir les formes et être appliquée aux contours ou remplissages de texte.

## Qu’est‑ce qu’un dégradé horizontal et pourquoi l’utiliser ?
Un dégradé horizontal mélange les couleurs du bord gauche d’un objet à son bord droit, créant une transition fluide qui ajoute de la profondeur et de l’intérêt visuel. Il est idéal pour les composants d’interface modernes, les titres mis en évidence ou les ombrages de fond subtils dans les rapports PDF ou PostScript. Utiliser **Linear Gradient Paint Java** vous permet de contrôler précisément les couleurs de départ et d’arrivée, l’opacité et le redimensionnement, garantissant que le résultat reste net sur tout appareil ou imprimante.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Kit de développement Java (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importer les packages
Commencez par importer les packages nécessaires dans votre projet Java. Ces imports vous donnent accès aux primitives graphiques, à la gestion des dégradés et à l’API Aspose.Page.

La classe `PsDocument` représente un document PostScript sur lequel vous pouvez dessiner des graphiques.  

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

## Étape 1 : créer un rectangle
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

## Étape 2 : créer un dégradé linéaire horizontal
`LinearGradientPaint` est la classe principale qui définit une transition de couleur linéaire.  
La classe `LinearGradientPaint` représente un objet de peinture qui rend un dégradé le long d’une ligne droite ; vous spécifiez les points de départ/arrivée, les arrêts de couleur, et un `AffineTransform` optionnel pour l’adapter à votre forme.

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

## Étape 3 : remplir le rectangle
Remplissez maintenant le rectangle avec le dégradé que nous venons de définir.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Étape 4 : remplir un texte avec le dégradé
Vous pouvez également appliquer le même dégradé au texte, créant un effet visuel saisissant.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Étape 5 : tracer le contour d’un texte avec le dégradé
Enfin, tracez le contour du texte en utilisant le dégradé comme couleur de trait.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le dégradé apparaît étiré | Mise à l’échelle incorrecte du `AffineTransform` | Assurez‑vous que la largeur et la hauteur du transform correspondent aux dimensions du rectangle (200 × 100 dans l’exemple). |
| Les couleurs semblent délavées | Valeurs alpha trop faibles | Augmentez le composant alpha (la quatrième valeur dans `new Color(r,g,b,alpha)`). |
| Le texte n’est pas visible | Peinture non définie avant le dessin du texte | Appelez `document.setPaint(paint)` **avant** tout appel à `fillAndStrokeText` ou `outlineText`. |

## Questions fréquentes
**Q :** Puis‑je utiliser Aspose.Page for Java dans des projets commerciaux ?  
**R :** Oui, Aspose.Page for Java peut être utilisé dans des projets commerciaux. Pour les détails de licence, visitez la page [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q :** Existe‑t‑il un essai gratuit ?  
**R :** Oui, vous pouvez accéder à un essai gratuit d’Aspose.Page for Java sur la page [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q :** Où puis‑je trouver de la documentation supplémentaire et du support ?  
**R :** Consultez la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/) pour des ressources complètes. Pour l’aide communautaire, consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q :** Comment obtenir une licence temporaire ?  
**R :** Vous pouvez obtenir une licence temporaire sur la page [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q :** Quelles sont les exigences système pour Aspose.Page for Java ?  
**R :** Consultez la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/) pour les exigences système détaillées.

---

**Dernière mise à jour :** 2026-09-04  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un dégradé PostScript en Java – Ajouter un dégradé vertical](/page/java/postscript-gradient-addition/vertical/)
- [Comment ajouter un dégradé : Dégradé diagonal en Java PostScript avec Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Créer un dégradé PostScript – Dégradé radial en Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}