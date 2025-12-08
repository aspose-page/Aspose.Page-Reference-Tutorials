---
date: 2025-12-08
description: Apprenez à ajouter un dégradé radial en Java PostScript avec Aspose.Page.
  Ce guide étape par étape vous montre comment créer des effets de dégradé époustouflants
  dans vos documents.
language: fr
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Comment ajouter un dégradé radial en Java PostScript avec Aspose.Page
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé radial dans Java PostScript avec Aspose.Page

## Introduction
Si vous avez déjà eu besoin d’offrir à votre sortie PostScript une transition de couleur douce et accrocheuse, apprendre **comment ajouter un dégradé radial** est le point de départ idéal. Dans ce tutoriel, nous parcourrons chaque étape nécessaire pour générer un fichier PostScript contenant un magnifique dégradé radial, en utilisant la bibliothèque **Aspose.Page for Java**. À la fin, vous comprendrez l’API, verrez un exemple complet exécutable, et saurez comment ajuster les couleurs, les positions et les rayons pour répondre à n’importe quel design.

## Réponses rapides
- **Quelle bibliothèque crée des dégradés radiaux dans PostScript ?** Aspose.Page for Java.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple de base.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur.  
- **Puis‑je modifier la forme du dégradé ?** Oui – ajustez le rayon et le point central dans le constructeur `RadialGradientPaint`.

## Qu’est‑ce qu’un dégradé radial ?
Un dégradé radial peint des couleurs qui rayonnent à partir d’un point central, se fondant progressivement vers les bords. Contrairement aux dégradés linéaires, la transition de couleur suit un motif circulaire (ou elliptique), idéal pour les reflets, les projecteurs ou les remplissages d’arrière‑plan doux.

## Pourquoi utiliser Aspose.Page pour les dégradés radiaux ?
- **Contrôle total sur la sortie PostScript** – pas besoin de rédiger manuellement des commandes PS de bas niveau.  
- **Multiplateforme** – fonctionne sur tout OS exécutant Java.  
- **Gestion riche des couleurs** – prend en charge plusieurs arrêts de couleur, différents espaces colorimétriques et méthodes de cycle.  
- **Prêt à l’intégration** – combinez avec d’autres fonctionnalités d’Aspose.Page telles que le texte, les images et les formes vectorielles.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants prêts :

- **Java Development Kit (JDK) 8+** – vérifiez avec `java -version`.  
- **Aspose.Page for Java** – téléchargez le dernier JAR depuis la [page de téléchargement officielle d’Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE de votre choix** – Eclipse, IntelliJ IDEA ou VS Code avec les extensions Java.  
- **Un dossier accessible en écriture** – où le fichier `.ps` généré sera enregistré.

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin. Le package `java.awt` fournit les objets de peinture de dégradé, tandis que `com.aspose.eps` contient les classes de gestion des documents PostScript.

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

### Étape 1 : Créer un rectangle et ouvrir un document PS
Nous commençons par créer un flux de sortie, configurer la taille de page (A4 par défaut) et définir un rectangle qui accueillera le dégradé.

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

### Étape 2 : Définir les couleurs et les fractions
Un dégradé radial est construit à partir des *arrêts de couleur* (les couleurs) et des *fractions* (les positions relatives de ces arrêts). Ici, nous créons un tableau de six couleurs et leurs fractions correspondantes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Pourquoi c’est important :** En modifiant les `fractions`, vous contrôlez la rapidité de la transition des couleurs, permettant des effets subtils ou spectaculaires.

### Étape 3 : Créer le RadialGradientPaint
Nous construisons maintenant l’objet `RadialGradientPaint`. Le constructeur prend le point central du dégradé, le rayon, le point de focalisation, les fractions, les couleurs, la méthode de cycle, l’espace colorimétrique et une transformation optionnelle.

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

> **Remarque :** `transform` peut être `null` si vous n’avez pas besoin de mise à l’échelle ou de rotation supplémentaire. N’hésitez pas à expérimenter avec `AffineTransform` pour des dégradés inclinés.

### Étape 4 : Appliquer la peinture et remplir le rectangle
Une fois la peinture prête, nous indiquons au `PsDocument` de l’utiliser puis remplissons le rectangle défini précédemment.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

À ce stade, la page PostScript contient un rectangle rempli en douceur avec le dégradé radial que nous avons configuré.

### Étape 5 : Fermer et enregistrer le document
Enfin, fermez la page courante et écrivez le fichier sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ouvrez `RadialGradient1_outPS.ps` dans n’importe quel visualiseur PostScript (par ex., Ghostscript) et vous verrez le dégradé rendu exactement comme défini.

## Problèmes courants & solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Le dégradé apparaît comme une couleur unie | Le tableau `fractions` ne commence pas à `0.0f` ou ne se termine pas à `1.0f` | Assurez‑vous que la première fraction est `0.0f` et la dernière `1.0f`. |
| Les couleurs semblent délavées | Utilisation du mauvais `ColorSpaceType` | Passez à `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` pour une sortie plus vive. |
| Aucun fichier de sortie généré | Le chemin du `FileOutputStream` est invalide ou non inscriptible | Vérifiez que `dataDir` existe et que l’application possède les droits d’écriture. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Page for Java dans des projets commerciaux ?**  
R : Oui. Une licence commerciale est requise pour une utilisation en production. Vous pouvez en acheter une sur la [page de licence Aspose](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver la référence officielle de l’API ?**  
R : La documentation complète est disponible [ici](https://reference.aspose.com/page/java/).

**Q : Une version d’essai gratuite est‑elle disponible pour les tests ?**  
R : Absolument. Téléchargez une version d’essai depuis la [page des releases Aspose.Page](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour l’évaluation ?**  
R : Une licence temporaire peut être demandée [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Rejoignez le forum de la communauté Aspose.Page sur [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
Vous savez maintenant **comment ajouter un dégradé radial** à un document Java PostScript en utilisant Aspose.Page. En ajustant la taille du rectangle, les arrêts de couleur et le rayon du dégradé, vous pouvez créer d’innombrables effets visuels – des remplissages d’arrière‑plan subtils aux graphismes de projecteur audacieux. N’hésitez pas à expérimenter avec différentes valeurs `AffineTransform` pour faire pivoter ou incliner le dégradé, et combinez cette technique avec du texte et des images pour des sorties PDF ou EPS encore plus riches.

---

**Dernière mise à jour :** 2025-12-08  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}