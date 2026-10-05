---
date: 2026-10-04
description: Apprenez à créer une pseudo‑transparence java en utilisant Aspose.Page.
  Suivez notre guide étape par étape pour ajouter des graphiques éclatants dans les
  fichiers PostScript.
keywords:
- create pseudo transparency java
- Aspose.Page Java
- PostScript pseudo transparency
lastmod: 2026-10-04
linktitle: Afficher la pseudo‑transparence en Java PostScript
og_description: Créez une pseudo‑transparence java avec Aspose.Page pour générer des
  graphiques PostScript éclatants. Ce guide vous accompagne pas à pas dans l'installation,
  le code et le dépannage en quelques minutes.
og_image_alt: Aspose.Page Java tutorial showing pseudo transparency in PostScript
og_title: Tutoriel – créer une pseudo‑transparence java avec Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to create pseudo transparency java using Aspose.Page. Follow
    our step‑by‑step guide to add vibrant graphics in PostScript files.
  headline: How to create pseudo transparency java with Aspose.Page
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java is available for commercial use. You can purchase
      a license **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: Yes, you can get a free trial **[download free trial](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Detailed documentation is available **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.
    question: Where can I find additional documentation?
  - answer: You can obtain a temporary license **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for testing purposes?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.
    question: Need help or want to discuss Aspose.Page?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- pseudo transparency
- Aspose.Page
- Java PostScript
title: Comment créer une pseudo‑transparence java avec Aspose.Page
url: /fr/java/postscript-transparency/show-pseudo-transparency/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript pseudo-transparence avec Aspose.Page

## Introduction
Dans ce tutoriel complet, vous allez **créer des graphiques pseudo-transparence java** avec Aspose.Page pour Java. Nous parcourrons tout—de l’installation de la bibliothèque à la création de deux rectangles qui se chevauchent et simulent la transparence dans un fichier PostScript. À la fin, vous comprendrez pourquoi la pseudo‑transparence est importante, comment la mettre en œuvre, et comment ajuster les couleurs et les dégradés pour vos propres conceptions.

## Réponses rapides
- **Qu'est-ce que la pseudo‑transparence ?** Elle simule la transparence en mélangeant des dégradés semi‑transparents.
- **Quelle bibliothèque est requise ?** Aspose.Page pour Java.
- **Ai-je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour le développement ; une licence commerciale est nécessaire pour la production.
- **Quel IDE puis‑je utiliser ?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) qui prend en charge Java 8+.
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple de base.

## Qu’est‑ce que la pseudo‑transparence en Java PostScript ?
Pseudo‑transparence est une technique qui utilise des remplissages de dégradés semi‑transparents pour donner l’effet visuel d’objets translucides. Parce que le PostScript traditionnel ne prend pas en charge les vrais canaux alpha, Aspose.Page l’émule en superposant des formes translucides. En ajustant les valeurs d’opacité du dégradé, vous pouvez simuler différents degrés de transparence sans nécessiter de prise en charge native de l’alpha.

## Pourquoi utiliser Aspose.Page pour la pseudo‑transparence ?
Aspose.Page prend en charge **plus de 30 formats de sortie** (y compris EPS, PDF, SVG et PNG) et peut rendre des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire. Son API Java multiplateforme vous offre un contrôle granulaire sur les couleurs, l’opacité et la direction du dégradé, garantissant des résultats cohérents sur n’importe quelle imprimante ou visionneuse.

## Prérequis
- Connaissances de base en Java.  
- Familiarité avec les concepts PostScript.  
- Bibliothèque Aspose.Page pour Java installée. Si vous ne l’avez pas encore téléchargée, obtenez‑la **[download Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- Un IDE Java ou un outil de construction (Maven/Gradle) prêt.

## Importer les packages
Les importations suivantes vous donnent accès aux couleurs, aux dégradés et à l’objet document PostScript.  

La classe `PsDocument` est l’objet de niveau supérieur d’Aspose.Page qui représente un fichier PostScript en mémoire.  

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

## Étape 1 : créer un document ps
Tout d’abord, nous créons un flux de sortie et initialisons un nouveau `PsDocument`. Cet objet sert de canevas pour toutes les opérations de dessin suivantes.  

Le constructeur `PsDocument` prend un `OutputStream` et un `PageSize` pour définir la surface de dessin.  

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "ShowPseudoTransparency_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 2 : définir un rectangle avec un remplissage de dégradé opaque
Nous dessinons le premier rectangle en utilisant un dégradé entièrement opaque. Cela servira de fond pour notre superposition pseudo‑transparente.  

La classe `LinearGradientBrush` fournit un moyen de remplir les formes avec des dégradés de couleur linéaires.  
La classe `LinearGradientBrush` crée un pinceau de dégradé ; ses paramètres `Color` acceptent des valeurs RGBA où la quatrième valeur (alpha) contrôle l’opacité.  

```java
float offsetX = 50;
float offsetY = 100;
float width = 200;
float height = 100;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create opaque gradient fill
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0), new Color(40, 128, 70)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Étape 3 : définir un rectangle avec un remplissage de dégradé translucide
Ensuite, nous plaçons un deuxième rectangle qui utilise un dégradé avec des valeurs alpha. Cela crée l’effet de **pseudo‑transparence** lorsqu’il chevauche la première forme.  

Le constructeur `Color` crée une couleur avec des composantes rouge, vert, bleu et alpha.  
Le constructeur `Color` `new Color(r, g, b, a)` vous permet de spécifier le canal alpha (0‑255), où des valeurs plus faibles augmentent la transparence.  

```java
offsetX = 350;
Rectangle2D.Float rectangle = new Rectangle2D.Float(offsetX, offsetY, width, height);
// Create translucent gradient fill
paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
    new float[] {0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
    MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
    new AffineTransform(width, 0, 0, height, offsetX, offsetY));
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Étape 4 : fermer la page et enregistrer le document
Enfin, nous fermons la page actuelle et écrivons le fichier PostScript sur le disque.  

La méthode `save` écrit le contenu du document dans le flux de sortie fourni.  
Appeler `psDocument.save(outputStream)` finalise le fichier et vide toutes les commandes de dessin vers le flux sous‑jacent.  

```java
document.closePage();
document.save();
```

## Problèmes courants & dépannage
- **FileNotFoundException** – Vérifiez que `dataDir` pointe vers un dossier existant et que votre application possède les permissions d’écriture.  
- **Incorrect colors** – Assurez‑vous d’utiliser le constructeur `Color(int r, int g, int b, int a)` pour les couleurs translucides ; le quatrième paramètre est l’alpha (0‑255).  
- **Gradient not visible** – Vérifiez que les paramètres de `AffineTransform` mappent correctement le dégradé aux dimensions du rectangle.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page pour Java dans des projets commerciaux ?**  
R : Oui, Aspose.Page pour Java est disponible pour une utilisation commerciale. Vous pouvez acheter une licence **[purchase Aspose.Page license](https://purchase.aspose.com/buy)**.

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez obtenir une version d’essai gratuite **[download free trial](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver une documentation supplémentaire ?**  
R : Une documentation détaillée est disponible **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)**.

**Q : Comment obtenir une licence temporaire à des fins de test ?**  
R : Vous pouvez obtenir une licence temporaire **[temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)**.

**Q : Besoin d’aide ou envie de discuter d’Aspose.Page ?**  
R : Visitez le **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**.

---

**Dernière mise à jour :** 2026-10-04  
**Testé avec :** Aspose.Page pour Java 24.12 (latest)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un dégradé radial en PostScript avec Aspose.Page pour Java](/page/java/postscript-gradient-addition/)
- [Créer un motif de texture en PostScript avec Aspose.Page pour Java](/page/java/postscript-texture-patterns/)
- [Comment convertir PostScript en PDF en utilisant l’API Java d’Aspose.Page](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}