---
date: 2025-12-07
description: Améliorez vos documents Java PostScript avec des dégradés diagonaux grâce
  à Aspose.Page Java. Apprenez à ajouter des effets de dégradé avec LinearGradientPaint
  en Java et créez des transitions de couleur éclatantes en toute simplicité.
language: fr
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Ajouter un dégradé diagonal en Java PostScript avec Aspose.Page Java
url: /java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé diagonal en Java PostScript avec Aspose.Page Java

## Introduction
Si vous souhaitez enrichir un fichier PostScript d’une transition de couleur diagonale fluide, **Aspose.Page Java** le rend étonnamment simple. Dans ce tutoriel, nous parcourrons **comment ajouter un dégradé** étape par étape, en utilisant la classe `LinearGradientPaint` de Java 2D. À la fin, vous disposerez d’un extrait prêt à l’emploi qui crée un document PostScript avec un dégradé diagonal éclatant.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page pour Java.  
- **Quelle classe crée le dégradé ?** `LinearGradientPaint`.  
- **Puis-je changer les couleurs ?** Oui – modifiez le tableau `Color[]`.  
- **Ai-je besoin d'une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible.  
- **Combien de temps prend l'implémentation ?** Environ 10 minutes pour un dégradé de base.

## Qu’est‑ce qu’Aspose.Page Java ?
Aspose.Page Java est une API puissante qui permet aux développeurs de générer, modifier et convertir des fichiers PostScript et PDF sans avoir besoin de logiciel externe. Elle expose toutes les capacités graphiques du langage PostScript via une interface Java propre et orientée objet.

## Pourquoi utiliser un dégradé diagonal ?
Un dégradé diagonal ajoute de la profondeur et de l’intérêt visuel aux graphiques, bannières ou tout élément graphique nécessitant un aspect moderne. Comme le dégradé s’étend d’un coin à l’autre, il convient parfaitement aux arrière‑plans, aux skins de boutons et aux formes décoratives.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Java Development Kit (JDK) 8 ou supérieur.  
- Un IDE tel qu’Eclipse, IntelliJ IDEA ou VS Code.  
- La bibliothèque **Aspose.Page pour Java** – téléchargez la dernière version depuis la [page de téléchargement officielle](https://releases.aspose.com/page/java/).

## Importer les packages
Tout d’abord, importez les classes Java 2D et Aspose dont vous aurez besoin. Ces imports vous donnent accès aux définitions de couleur, aux formes géométriques, à la peinture de dégradé et à l’API du document PostScript.

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

## Étape 1 : Créer le flux de sortie pour le document PostScript
Nous commençons par définir le dossier où le fichier sera enregistré et ouvrir un `FileOutputStream`. Ce flux recevra les données PostScript générées.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Étape 2 : Créer les options d’enregistrement avec le format A4
`PsSaveOptions` vous permet de spécifier la taille de page, la résolution et d’autres paramètres de sortie. Ici, nous utilisons la taille A4 par défaut.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Étape 3 : Créer un nouveau document PS
Instanciez un `PsDocument` en utilisant le flux de sortie et les options d’enregistrement. Le drapeau `false` indique au constructeur de ne pas ouvrir automatiquement une nouvelle page – nous le ferons plus tard.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : Créer un rectangle
Définissez le rectangle qui recevra le remplissage du dégradé. La position du rectangle (200, 100) et sa taille (200 × 100) sont choisies pour rendre le dégradé clairement visible.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Étape 5 : Créer la transformation du dégradé
Un `AffineTransform` nous permet de faire pivoter, mettre à l’échelle et translater le dégradé afin qu’il s’étende diagonalement à travers le rectangle. Le calcul ci‑dessous détermine l’hypoténuse et ajuste le ratio d’échelle en conséquence.

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

## Étape 6 : Créer un `LinearGradientPaint` diagonal
Voici le cœur de **comment ajouter un dégradé** – nous construisons un `LinearGradientPaint` qui s’étend du coin supérieur gauche au coin inférieur droit du rectangle, en utilisant la transformation définie précédemment. `MultipleGradientPaint.CycleMethod.NO_CYCLE` garantit que le dégradé ne se répète pas.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Étape 7 : Appliquer la peinture et remplir le rectangle
Appliquez la peinture de dégradé au document et remplissez la forme du rectangle. Cette étape rend la transition de couleur diagonale sur la page PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Étape 8 : Fermer la page courante et enregistrer le document
Enfin, fermez la page, videz le flux et enregistrez le fichier. Le fichier `DiagonalGradient_outPS.ps` résultant peut être ouvert avec n’importe quel visualiseur PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

En suivant ces huit étapes, vous avez ajouté avec succès un dégradé diagonal à un document PostScript à l’aide de **Aspose.Page Java**. N’hésitez pas à expérimenter avec différentes couleurs, angles et tailles de rectangle pour créer des effets visuels personnalisés.

## Problèmes courants et astuces
- **Le dégradé apparaît plat** – revérifiez l’angle de rotation ; une rotation de 45° crée un vrai diagonal.  
- **Les couleurs semblent délavées** – assurez‑vous d’utiliser `MultipleGradientPaint.ColorSpaceType.SRGB` pour un rendu couleur précis.  
- **Erreur « fichier introuvable »** – vérifiez que `dataDir` pointe vers un dossier existant et que l’application possède les droits d’écriture.

## Questions fréquentes

**Q : Puis‑je utiliser cette bibliothèque pour d’autres opérations graphiques en Java ?**  
R : Oui, Aspose.Page pour Java fournit un ensemble complet de primitives de dessin, de rendu de texte et de gestion d’images.

**Q : Existe‑t‑il un essai gratuit d’Aspose.Page Java ?**  
R : Absolument. Vous pouvez télécharger un essai pleinement fonctionnel depuis la [page d’essai gratuit d’Aspose](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation d’Aspose.Page Java ?**  
R : La référence API officielle est disponible [ici](https://reference.aspose.com/page/java/).

**Q : Comment puis‑je acheter une licence pour Aspose.Page Java ?**  
R : Les licences peuvent être achetées directement via le [portail d’achat d’Aspose](https://purchase.aspose.com/buy).

**Q : Besoin d’assistance ou avez‑vous des questions ?**  
R : Visitez le forum communautaire [Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide des ingénieurs Aspose et d’autres développeurs.

---

**Dernière mise à jour :** 2025-12-07  
**Testé avec :** Aspose.Page pour Java 24.12 (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}