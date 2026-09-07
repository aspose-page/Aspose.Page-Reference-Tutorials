---
date: 2026-09-04
description: Apprenez à ajouter un dégradé dans Java PostScript avec Aspose.Page Java,
  en créant des transitions de couleur diagonales à l'aide de LinearGradientPaint
  pour des documents dynamiques.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Comment ajouter un dégradé : dégradé diagonal dans Java PostScript avec
  Aspose.Page Java'
og_description: Apprenez à ajouter un dégradé dans Java PostScript en utilisant Aspose.Page
  Java. Ce guide vous montre comment créer un dégradé diagonal avec LinearGradientPaint
  en quelques étapes.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Comment ajouter un dégradé dans Java PostScript avec Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Comment ajouter un dégradé : dégradé diagonal dans Java PostScript avec Aspose.Page
  Java'
url: /fr/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé diagonal en Java PostScript avec Aspose.Page Java

## Introduction
Si vous cherchez à enrichir un fichier PostScript avec une transition de couleur diagonale fluide, **Aspose.Page Java** le rend étonnamment simple. Dans ce tutoriel, vous apprendrez **comment ajouter des effets de dégradé** étape par étape, en utilisant la classe `LinearGradientPaint` de Java 2D. À la fin, vous disposerez d’un extrait prêt à l’exécution qui crée un document PostScript avec un dégradé diagonal éclatant, et vous comprendrez pourquoi cette approche est plus maintenable que le codage manuel de commandes PostScript brutes.

## Comment ajouter un dégradé en Java PostScript
Ajouter un dégradé peut sembler une tâche réservée aux graphiques, mais avec Aspose.Page vous obtenez un contrôle complet sur les commandes PostScript sous‑jacentes tout en restant en Java pur. Cette section explique pourquoi l’approche fonctionne et ce que vous gagnez par rapport au codage manuel de PostScript brut.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java.  
- **Quelle classe crée le dégradé ?** `LinearGradientPaint`.  
- **Puis-je changer les couleurs ?** Oui – modifiez le tableau `Color[]`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible.  
- **Combien de temps prend l’implémentation ?** Environ 10 minutes pour un dégradé de base.

## Qu’est‑ce qu’Aspose.Page Java ?
Aspose.Page Java est une API complète qui permet aux développeurs de générer, modifier et convertir des fichiers PostScript et PDF sans aucun logiciel externe. La bibliothèque prend en charge **plus de 50 formats d’entrée et de sortie** et peut traiter des documents contenant **plus de 500 pages** tout en maintenant l’utilisation de la mémoire en dessous de 100 Mo.

## Pourquoi utiliser un dégradé diagonal ?
Un dégradé diagonal ajoute de la profondeur et de l’intérêt visuel aux graphiques, bannières ou tout élément graphique nécessitant un aspect moderne. Comme le dégradé s’étend d’un coin à l’autre, il convient parfaitement aux arrière‑plans, aux habillages de boutons et aux formes décoratives, offrant une finition professionnelle sans ressources d’image supplémentaires.

## Prérequis
- Java Development Kit (JDK) 8 ou supérieur.  
- Un IDE tel qu’Eclipse, IntelliJ IDEA ou VS Code.  
- **Aspose.Page for Java** – téléchargez la dernière version depuis la [page de téléchargement officielle](https://releases.aspose.com/page/java/).

## Importer les packages
Le package `java.awt` fournit les classes graphiques de base, tandis que le package `com.aspose.page` vous donne accès aux API spécifiques à PostScript.

La classe `LinearGradientPaint` est le pont d’Aspose.Page vers la fonctionnalité de dégradé de Java 2D.  
`AffineTransform` permet la rotation et le redimensionnement du dégradé afin qu’il s’aligne diagonalement.

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

## Étape 1 : créer le flux de sortie pour le document PostScript
Tout d’abord, définissez le dossier où le fichier sera enregistré et ouvrez un `FileOutputStream`. Ce flux reçoit les données PostScript générées.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Étape 2 : créer les options d’enregistrement avec le format A4
`PsSaveOptions` vous permet de spécifier la taille de la page, la résolution et d’autres paramètres de sortie. Ici nous utilisons la taille A4 par défaut, qui est de 595 × 842 points à 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Étape 3 : créer un nouveau document PS
La classe `PsDocument` représente un document PostScript et fournit des méthodes pour créer des pages et dessiner des graphiques.  
Instanciez un `PsDocument` en utilisant le flux de sortie et les options d’enregistrement. Le drapeau `false` indique au constructeur de ne pas ouvrir automatiquement une nouvelle page – nous le ferons plus tard.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : créer un rectangle
Définissez le rectangle qui recevra le remplissage en dégradé. La position du rectangle (200, 100) et sa taille (200 × 100) sont choisies pour rendre le dégradé clairement visible.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Étape 5 : créer la transformation du dégradé
Un `AffineTransform` nous permet de faire pivoter, redimensionner et translater le dégradé afin qu’il s’étende diagonalement à travers le rectangle. Les calculs ci‑dessous déterminent l’hypoténuse et ajustent le facteur d’échelle en conséquence.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Étape 6 : créer un dégradé linéaire diagonal
`LinearGradientPaint` est la classe principale qui génère la transition de couleur. Elle s’étend du coin supérieur gauche du rectangle au coin inférieur droit, en utilisant la transformation définie précédemment. Le `MultipleGradientPaint.CycleMethod.NO_CYCLE` garantit que le dégradé ne se répète pas.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Étape 7 : appliquer le pinceau et remplir le rectangle
Appliquez le pinceau de dégradé au document et remplissez la forme du rectangle. Cette étape rend la transition de couleur diagonale sur la page PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Étape 8 : fermer la page actuelle et enregistrer le document
Enfin, fermez la page, videz le flux et enregistrez le fichier. Le fichier résultant `DiagonalGradient_outPS.ps` peut être ouvert avec n’importe quel visualiseur PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Problèmes courants et astuces
- **Le dégradé apparaît plat** – vérifiez l’angle de rotation ; une rotation de 45° crée un vrai diagonal.  
- **Les couleurs semblent délavées** – assurez‑vous d’utiliser `MultipleGradientPaint.ColorSpaceType.SRGB` pour un rendu couleur précis.  
- **Erreur fichier non trouvé** – vérifiez que `dataDir` pointe vers un dossier existant et que l’application possède les permissions d’écriture.  
- **Les gros documents provoquent des pics de mémoire** – utilisez `PsSaveOptions.setCompress(true)` pour réduire l’empreinte mémoire.

## Questions fréquemment posées

**Q : Puis‑je utiliser cette bibliothèque pour d’autres opérations graphiques en Java ?**  
R : Oui, Aspose.Page for Java fournit un ensemble complet de primitives de dessin, de rendu de texte et de capacités de gestion d’images.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page Java ?**  
R : Absolument. Vous pouvez télécharger un essai pleinement fonctionnel depuis la [page d’essai gratuite d’Aspose](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation d’Aspose.Page Java ?**  
R : La référence officielle de l’API est disponible [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q : Comment puis‑je acheter une licence pour Aspose.Page Java ?**  
R : Les licences peuvent être achetées directement via le [portail d’achat d’Aspose](https://purchase.aspose.com/buy).

**Q : Besoin d’assistance ou avez‑vous des questions ?**  
R : Visitez le [forum communautaire Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide des ingénieurs Aspose et d’autres développeurs.

---

**Dernière mise à jour :** 2026-09-04  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un dégradé radial en PostScript avec Aspose.Page pour Java](/page/java/postscript-gradient-addition/)
- [Comment ajouter un dégradé en Java PostScript avec Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Créer un dégradé PostScript en Java – Ajouter un dégradé vertical](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}