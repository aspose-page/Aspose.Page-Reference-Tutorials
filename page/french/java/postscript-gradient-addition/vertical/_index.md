---
date: 2026-02-13
description: Apprenez à créer un dégradé PostScript en Java avec Aspose.Page. Ce guide
  pas à pas vous montre comment ajouter facilement un dégradé vertical à vos documents
  PostScript.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Créer un dégradé PostScript en Java – Ajouter un dégradé vertical
url: /fr/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un dégradé PostScript en Java – Ajouter un dégradé vertical

## Introduction
Dans ce tutoriel complet, vous apprendrez à **créer un dégradé PostScript en Java** avec Aspose.Page for Java. Ajouter un dégradé vertical peut rendre vos documents plus vivants et professionnels, et avec seulement quelques lignes de code vous pouvez obtenir des effets visuels époustouflants. Nous vous guiderons à chaque étape, expliquerons pourquoi chaque élément est important et vous donnerons des conseils pratiques pour éviter les pièges courants. À la fin de ce guide, vous serez capable de générer des fichiers PostScript avec des transitions de couleur verticales fluides et accrocheuses.

## Réponses rapides
- **Quelle bibliothèque est‑elle nécessaire ?** Aspose.Page for Java  
- **Puis‑je personnaliser les couleurs ?** Oui, n’importe quel `java.awt.Color` peut être utilisé  
- **La rotation est‑elle prise en charge ?** Oui, vous pouvez faire pivoter le dégradé avec un `AffineTransform`  
- **Quel format de sortie est produit ?** Un fichier PostScript standard (.ps)  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise  

## Pourquoi ajouter un dégradé vertical à un document PostScript ?
Les dégradés verticaux donnent de la profondeur à vos pages sans augmenter la taille du fichier. Ils sont parfaits pour :

* En‑têtes ou pieds de page de rapports nécessitant une légère touche de fond.  
* Mise en évidence de sections dans des manuels techniques ou des livres blancs.  
* Offrir un aspect moderne aux graphiques, diagrammes ou flyers promotionnels.

Comme le dégradé est défini sous forme vectorielle, la sortie reste nette à n’importe quelle résolution.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).

## Importer les packages
Dans votre projet Java, importez les packages nécessaires pour commencer :
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

Maintenant, parcourons le processus d’ajout d’un dégradé vertical étape par étape.

## Comment créer un dégradé PostScript en Java
Voici un guide étape par étape qui montre exactement comment **créer un dégradé PostScript en Java** en utilisant l’API Aspose.Page.

### Étape 1 : Configurer le répertoire de votre document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Étape 2 : Créer le flux de sortie pour le document PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Étape 3 : Créer les options d’enregistrement avec le format A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Étape 4 : Créer un nouveau document PS
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 5 : Créer un rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Étape 6 : Configurer les couleurs et les fractions pour le dégradé
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Étape 7 : Créer la transformation du dégradé
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Étape 8 : Créer le Paint de dégradé linéaire vertical
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Étape 9 : Définir le Paint et remplir le rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Étape 10 : Fermer la page actuelle et enregistrer le document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Félicitations ! Vous avez ajouté avec succès un dégradé vertical à votre document PostScript Java en utilisant Aspose.Page for Java.

## Problèmes courants et solutions
- **Le dégradé apparaît plat :** Assurez‑vous que le redimensionnement du `AffineTransform` correspond aux dimensions du rectangle.  
- **Les couleurs semblent délavées :** Vérifiez que vous utilisez le bon `ColorSpaceType` (SRGB) et que le tableau de fractions est ordonné de 0.0 à 1.0.  
- **Le fichier n’est pas généré :** Vérifiez que le répertoire de sortie (`dataDir`) existe et que l’application possède les droits d’écriture.  

## Foire aux questions
### Puis‑je utiliser Aspose.Page for Java avec d’autres bibliothèques Java ?
Oui, Aspose.Page for Java est conçu pour fonctionner de manière transparente avec d’autres bibliothèques Java.

### Existe‑t‑il un essai gratuit pour Aspose.Page for Java ?
Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver une documentation supplémentaire ?
Une documentation détaillée est disponible [ici](https://reference.aspose.com/page/java/).

### Comment puis‑je acheter Aspose.Page for Java ?
Vous pouvez acheter Aspose.Page for Java [ici](https://purchase.aspose.com/buy).

### Existe‑t‑il un forum pour les discussions sur Aspose.Page ?
Oui, vous pouvez rejoindre le forum communautaire [ici](https://forum.aspose.com/c/page/39).

## Questions fréquentes supplémentaires

**Q : Puis‑je créer d’autres directions de dégradé (horizontal, diagonal) ?**  
**R :** Absolument. Ajustez les points de départ et d’arrivée dans `LinearGradientPaint` et modifiez l’angle de rotation dans le `AffineTransform`.

**Q : Cela fonctionne‑t‑il également avec la sortie PDF ?**  
**R :** La même logique de dégradé peut être appliquée lors de l’enregistrement en PDF en utilisant `PdfSaveOptions` au lieu de `PsSaveOptions`.

**Q : Comment changer dynamiquement la taille du dégradé ?**  
**R :** Calculez les dimensions du rectangle à l’exécution et transmettez ces valeurs à la fois au `Rectangle2D` et au constructeur du `AffineTransform`.

---

**Dernière mise à jour :** 2026-02-13  
**Testé avec :** Aspose.Page for Java 24.11 (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}