---
date: 2026-02-13
description: Apprenez à créer un dégradé PostScript avec un dégradé radial à arrêts
  de couleur en utilisant Aspose.Page pour Java. Ce guide étape par étape vous montre
  comment ajouter un dégradé à arrêts de couleur dans vos documents.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Créer un dégradé PostScript – dégradé radial en Java
url: /fr/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé radial dans Java PostScript avec Aspose.Page

## Introduction
Si vous avez déjà eu besoin de **créer un dégradé PostScript** avec une transition de couleur fluide et accrocheuse, apprendre à ajouter un dégradé radial est le point de départ idéal. Dans ce tutoriel, nous parcourrons chaque étape nécessaire pour générer un fichier PostScript contenant un magnifique dégradé radial, en utilisant la bibliothèque **Aspose.Page for Java**. À la fin, vous comprendrez l'API, verrez un exemple complet exécutable et saurez comment ajuster les couleurs, les positions et les rayons pour répondre à n'importe quel design.

## Quick Answers
- **Quelle bibliothèque crée des dégradés radiaux dans PostScript ?** Aspose.Page for Java.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple de base.  
- **Ai‑je besoin d'une licence pour exécuter le code ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure.  
- **Puis‑je modifier la forme du dégradé ?** Oui – ajustez le rayon et le point central dans le constructeur `RadialGradientPaint`.

## How to Create PostScript Gradient with Radial Fill
Vous trouverez ci‑dessous un guide concis, étape par étape, qui montre exactement comment **créer du contenu de dégradé PostScript** en utilisant un remplissage radial. Chaque étape comprend une courte explication suivie du bloc de code original (inchangé).

## What is a Radial Gradient?
Un dégradé radial applique des couleurs qui rayonnent à partir d'un point central, se fondant progressivement vers les bords. Contrairement aux dégradés linéaires, la transition de couleur suit un motif circulaire (ou elliptique), idéal pour les reflets, les projecteurs ou les remplissages d'arrière‑plan doux.

## Why Use Aspose.Page for Radial Gradients?
- **Contrôle total sur la sortie PostScript** – aucune nécessité de créer manuellement des commandes PS de bas niveau.  
- **Cross‑platform** – fonctionne sur tout OS exécutant Java.  
- **Gestion riche des couleurs** – prend en charge plusieurs arrêts de couleur, différents espaces colorimétriques et méthodes de cycle.  
- **Prêt à l'intégration** – combine avec d'autres fonctionnalités d'Aspose.Page telles que le texte, les images et les formes vectorielles.

## Prerequisites
Avant de plonger dans le code, assurez‑vous d'avoir les éléments suivants prêts :

- **Java Development Kit (JDK) 8+** – vérifiez avec `java -version`.  
- **Aspose.Page for Java** – téléchargez le JAR le plus récent depuis la [page de téléchargement officielle d'Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE de votre choix** – Eclipse, IntelliJ IDEA ou VS Code avec extensions Java.  
- **Un dossier accessible en écriture** – où le fichier `.ps` généré sera enregistré.

## Import Packages
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

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
Nous commençons par créer un flux de sortie, configurer la taille de la page (A4 par défaut) et définir un rectangle qui accueillera le dégradé.

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

### Step 2: Define Colors and Fractions
Un dégradé radial est construit à partir des *arrêts de couleur* (les couleurs) et des *fractions* (les positions relatives de ces arrêts). Ici, nous créons un tableau de six couleurs et leurs fractions correspondantes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Pourquoi c’est important :** En ajustant les `fractions`, vous contrôlez la rapidité de la transition des couleurs, permettant des effets subtils ou dramatiques.

### Adding Color Stops Gradient to Your Radial Fill
Lorsque vous devez **ajouter un dégradé d’arrêts de couleur**, les tableaux `colors` et `fractions` sont essentiels. N’hésitez pas à réorganiser, ajouter ou supprimer des entrées selon votre conception visuelle.

### Step 3: Create Radial Gradient Paint
Nous créons maintenant l'objet `RadialGradientPaint`. Le constructeur prend le point central du dégradé, le rayon, le point de focalisation, les fractions, les couleurs, la méthode de cycle, l'espace colorimétrique et une transformation optionnelle.

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

> **Note :** `transform` peut être `null` si vous n’avez pas besoin d’échelle ou de rotation supplémentaires. N’hésitez pas à expérimenter avec `AffineTransform` pour des dégradés inclinés.

### Step 4: Set Paint and Fill the Rectangle
Une fois la peinture prête, nous indiquons au `PsDocument` de l’utiliser puis remplissons le rectangle que nous avons défini précédemment.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

À ce stade, la page PostScript contient un rectangle rempli en douceur avec le dégradé radial que nous avons configuré.

### Step 5: Close and Save the Document
Enfin, fermez la page actuelle et écrivez le fichier sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ouvrez `RadialGradient1_outPS.ps` dans n'importe quel visualiseur PostScript (par ex., Ghostscript) et vous verrez le dégradé rendu exactement comme défini.

## Common Issues & Solutions
| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le dégradé apparaît comme une couleur unie | Le tableau `fractions` ne commence pas à `0.0f` ou ne se termine pas à `1.0f` | Assurez‑vous que la première fraction soit `0.0f` et la dernière `1.0f`. |
| Les couleurs semblent délavées | Utilisation du mauvais `ColorSpaceType` | Passez à `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` pour une sortie plus vive. |
| Aucun fichier de sortie généré | Le chemin `FileOutputStream` est invalide ou non inscriptible | Vérifiez que `dataDir` existe et que l'application dispose des permissions d'écriture. |

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.Page for Java dans des projets commerciaux ?**  
R : Oui. Une licence commerciale est requise pour une utilisation en production. Vous pouvez en acheter une sur la [page de licence Aspose](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver la référence officielle de l'API ?**  
R : La documentation complète est disponible [ici](https://reference.aspose.com/page/java/).

**Q : Une version d'essai gratuite est‑elle disponible pour les tests ?**  
R : Absolument. Téléchargez une version d'essai depuis la [page des versions d'Aspose.Page](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour l'évaluation ?**  
R : Une licence temporaire peut être demandée [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Rejoignez le forum communautaire Aspose.Page à [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
Vous savez maintenant **comment ajouter un dégradé radial** à un document Java PostScript en utilisant Aspose.Page. En ajustant la taille du rectangle, les arrêts de couleur et le rayon du dégradé, vous pouvez créer d'innombrables effets visuels – des remplissages d'arrière‑plan subtils aux graphiques de projecteur audacieux. N’hésitez pas à expérimenter avec différentes valeurs `AffineTransform` pour faire pivoter ou incliner le dégradé, et à combiner cette technique avec du texte et des images pour des sorties PDF ou EPS plus riches.

---

**Dernière mise à jour :** 2026-02-13  
**Testé avec :** Aspose.Page for Java latest (as of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}