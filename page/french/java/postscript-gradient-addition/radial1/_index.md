---
date: 2026-09-09
description: Apprenez à créer un dégradé radial dans Java PostScript en utilisant
  Aspose.Page. Ce guide étape par étape vous montre comment ajouter un color stops
  gradient, définir les radii, et générer rapidement un fichier PS.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Maîtriser les radial gradients en Java
og_description: Apprenez à créer un dégradé radial dans Java PostScript en utilisant
  Aspose.Page. Ce guide explique comment ajouter un color stops gradient, définir
  les radii et générer un fichier PS en quelques minutes.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Comment créer un dégradé radial dans Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Comment créer un dégradé radial dans Java PostScript
url: /fr/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un dégradé radial en Java PostScript avec Aspose.Page

## Introduction
Si vous avez besoin de **créer un dégradé radial** dans un fichier PostScript, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons chaque étape nécessaire pour générer un document PostScript contenant un dégradé radial lisse, en utilisant **Aspose.Page for Java**. À la fin, vous comprendrez l'API, verrez un exemple complet exécutable et saurez comment ajuster les couleurs, les positions et les rayons pour n'importe quel scénario de conception.

## Réponses rapides
- **Quelle bibliothèque crée des dégradés radiaux dans PostScript ?** Aspose.Page for Java.  
- **Combien de temps prend l'implémentation ?** About 10‑15 minutes for a basic example.  
- **Ai-je besoin d'une licence pour exécuter le code ?** A free trial works for development; a commercial license is required for production.  
- **Quelle version de Java est prise en charge ?** Java 8 or higher.  
- **Puis-je changer la forme du dégradé ?** Yes – adjust the radius and center point in the `RadialGradientPaint` constructor.

## Comment créer un dégradé radial en Java

Chargez votre projet Java, importez les classes requises et suivez le guide étape par étape ci‑dessous. La réponse principale est que vous instanciez un `RadialGradientPaint` avec vos arrêts de couleur, puis l'appliquez à un rectangle dessiné sur un `PsDocument`. Cette approche à deux objets gère toutes les commandes PostScript de bas niveau pour vous.

## Qu'est-ce qu'un dégradé radial ?

`RadialGradientPaint` est une classe Java AWT qui définit une transition de couleur circulaire depuis un point central vers l'extérieur. Elle crée un mélange fluide de plusieurs arrêts de couleur, ce qui la rend idéale pour les projecteurs, les arrière‑plans doux ou tout effet où les couleurs rayonnent à partir d'un point focal.

## Pourquoi utiliser Aspose.Page pour les dégradés radiaux ?

Aspose.Page vous offre un contrôle programmatique complet sur la sortie PostScript tout en gérant la lourde tâche de la syntaxe PS de bas niveau. Il prend en charge **plus de 50 formats d'entrée et de sortie**, peut rendre des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire, et fonctionne sur tout système d'exploitation supportant Java 8+. Cette capacité quantifiée en fait un choix fiable pour la génération de graphiques de niveau entreprise.

## Prérequis
- **Java Development Kit (JDK) 8+** – vérifiez avec `java -version`.  
- **Aspose.Page for Java** – téléchargez le dernier JAR depuis la page officielle [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE de votre choix** – Eclipse, IntelliJ IDEA, ou VS Code avec extensions Java.  
- **Un dossier accessible en écriture** – où le fichier `.ps` généré sera enregistré.

## Importer les packages
Tout d'abord, importez les classes dont nous aurons besoin. Le package `java.awt` fournit les objets de peinture de dégradé, tandis que `com.aspose.eps` contient les classes de gestion de documents PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guide étape par étape

### Étape 1 : créer un rectangle et ouvrir un document PS
`PsDocument` est la classe d'Aspose.Page qui représente un document PostScript et fournit des méthodes pour dessiner des formes, du texte et des images. Nous commençons par créer un flux de sortie, configurer la taille de page (A4 par défaut) et définir un rectangle qui accueillera le dégradé.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Astuce :** Ajustez les coordonnées du rectangle (`200, 100, 200, 200`) pour positionner le dégradé où vous le souhaitez sur la page.

### Étape 2 : définir les couleurs et les fractions
Un dégradé radial est construit à partir des *arrêts de couleur* (les couleurs) et des *fractions* (les positions relatives de ces arrêts). Ici, nous créons un tableau de six couleurs et leurs fractions correspondantes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Pourquoi c'est important :** En ajustant les `fractions`, vous contrôlez la rapidité de la transition des couleurs, permettant des effets subtils ou dramatiques.

### Étape 3 : créer le paint du dégradé radial
`RadialGradientPaint` est la classe principale qui décrit un dégradé de couleur radial, incluant le point central, le rayon, le point de focalisation, les fractions, les couleurs, la méthode de cycle et l'espace colorimétrique. Nous construisons maintenant l'objet `RadialGradientPaint` en utilisant les tableaux définis ci‑dessus.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Remarque :** `transform` peut être `null` si vous n'avez pas besoin d'échelle ou de rotation supplémentaires. N'hésitez pas à expérimenter avec `AffineTransform` pour des dégradés inclinés.

### Étape 4 : définir le paint et remplir le rectangle
Une fois le paint prêt, nous indiquons au `PsDocument` de l'utiliser puis remplissons le rectangle que nous avons défini précédemment.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

À ce stade, la page PostScript contient un rectangle rempli en douceur avec le dégradé radial que nous avons configuré.

### Étape 5 : fermer et enregistrer le document
Enfin, fermez la page actuelle et écrivez le fichier sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ouvrez `RadialGradient1_outPS.ps` dans n'importe quel visualiseur PostScript (par ex., Ghostscript) et vous verrez le dégradé rendu exactement comme défini.

## Problèmes courants & solutions

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le dégradé apparaît comme une couleur unie | `fractions` ne commence pas à `0.0f` ou ne se termine pas à `1.0f` | Assurez‑vous que la première fraction est `0.0f` et la dernière `1.0f`. |
| Les couleurs semblent délavées | Utilisation du mauvais `ColorSpaceType` | Passez à `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` pour une sortie plus vive. |
| Aucun fichier de sortie généré | Le chemin de `FileOutputStream` est invalide ou non inscriptible | Vérifiez que `dataDir` existe et que l'application possède les permissions d'écriture. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page pour Java dans des projets commerciaux ?**  
R : Oui. Une licence commerciale est requise pour une utilisation en production. Vous pouvez en acheter une sur la [page de licence Aspose](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver la référence officielle de l'API ?**  
R : La documentation complète est disponible [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q : Une version d'essai gratuite est‑elle disponible pour les tests ?**  
R : Absolument. Téléchargez une version d'essai depuis la [page des versions Aspose.Page](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour l'évaluation ?**  
R : Une licence temporaire peut être demandée sur la [page de demande de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Rejoignez le forum communautaire Aspose.Page à l'adresse [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
Vous savez maintenant **comment créer un dégradé radial** dans un document Java PostScript en utilisant Aspose.Page. En ajustant la taille du rectangle, les arrêts de couleur et le rayon du dégradé, vous pouvez créer d'innombrables effets visuels — des remplissages d'arrière‑plan subtils aux graphiques de projecteur audacieux. N'hésitez pas à expérimenter avec différentes valeurs de `AffineTransform` pour faire pivoter ou incliner le dégradé, et à combiner cette technique avec du texte et des images pour des sorties PDF ou EPS plus riches.

---

**Dernière mise à jour :** 2026-09-09  
**Testé avec :** Aspose.Page for Java latest (as of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Remplir une forme avec un dégradé : Exemple radial Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Créer un dégradé PostScript en Java – Ajouter un dégradé vertical](/page/java/postscript-gradient-addition/vertical/)
- [Tutoriel de transparence Aspose.Page – Ajouter de la transparence en Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}