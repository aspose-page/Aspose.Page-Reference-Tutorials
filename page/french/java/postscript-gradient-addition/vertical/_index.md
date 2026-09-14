---
date: 2026-09-14
description: Apprenez à créer un dégradé PostScript Java avec Aspose.Page. Ce guide
  étape par étape vous montre comment ajouter un dégradé vertical à un fichier PostScript
  en quelques lignes de code Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Ajouter un dégradé vertical en Java PostScript
og_description: Apprenez à créer un dégradé PostScript Java avec Aspose.Page. Ce guide
  étape par étape vous montre comment ajouter un dégradé vertical à un fichier PostScript
  en quelques lignes de code Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Créer un dégradé PostScript Java – dégradé vertical
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Créer un dégradé PostScript Java – dégradé vertical
url: /fr/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un dégradé PostScript Java – dégradé vertical

## Introduction
Aspose.Page for Java est une bibliothèque qui permet la création et la manipulation de fichiers PostScript et PDF de manière programmatique. Dans ce tutoriel complet, vous apprendrez comment **créer un dégradé postscript java** en utilisant cette bibliothèque. Ajouter un dégradé vertical peut rendre vos documents plus dynamiques et professionnels, et avec quelques lignes de code vous pouvez obtenir des effets visuels époustouflants. Nous vous guiderons à chaque étape, expliquerons l’importance de chaque élément et vous donnerons des conseils pratiques pour éviter les pièges courants. À la fin de ce guide, vous serez capable de générer des fichiers PostScript avec des transitions de couleur verticales lisses et accrocheuses.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Puis‑je personnaliser les couleurs ?** Oui, n’importe quel `java.awt.Color` peut être utilisé  
- **La rotation est‑elle prise en charge ?** Oui, vous pouvez faire pivoter le dégradé avec un `AffineTransform`  
- **Quel format de sortie est produit ?** Un fichier PostScript standard (.ps)  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise  

## Pourquoi ajouter un dégradé vertical à un document PostScript ?
Ajouter un dégradé vertical donne de la profondeur à vos pages, améliore la hiérarchie visuelle et maintient la taille du fichier faible, car le dégradé est défini sous forme vectorielle plutôt que comme image raster. Cette technique est idéale pour les en‑têtes de rapports, les manuels techniques ou tout flyer nécessitant un aspect moderne sans sacrifier la scalabilité.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger depuis la [page de diffusion Aspose.Page for Java](https://releases.aspose.com/page/java/).

## Importer les packages
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

Maintenant, parcourons le processus d’ajout d’un dégradé vertical étape par étape.

## Comment créer un dégradé postscript java
Chargez votre environnement Java, créez une instance `PsSaveOptions`, puis appelez `Document.save` – c’est la séquence principale qui crée un fichier PostScript avec un dégradé vertical. L’API gère l’interpolation des couleurs, les transformations de coordonnées et le vidage de la page pour vous, vous n’avez donc qu’à vous concentrer sur la définition du rectangle et des paramètres du dégradé.

### Étape 1 : configurer le répertoire de votre document
Les objets `File` représentent le dossier où la sortie sera écrite. Le répertoire doit exister avant l’ouverture du flux, sinon une `IOException` est levée.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Étape 2 : créer le flux de sortie pour le document PostScript
`FileOutputStream` écrit les données binaires PostScript sur le disque. L’utilisation d’un bloc `try‑with‑resources` garantit que le flux est fermé même en cas d’exception.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Étape 3 : créer les options d’enregistrement avec le format A4
`PsSaveOptions` vous permet de spécifier la taille de page, le DPI et si les polices doivent être incorporées. Définir la taille à A4 (595 × 842 points) correspond à la plupart des documents imprimables.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Étape 4 : créer un nouveau document PS
`Document` est l’objet de haut niveau qui représente un fichier PostScript unique en mémoire. Toutes les commandes de dessin sont émises contre cet objet.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 5 : créer un rectangle
`Rectangle2D.Double` définit la zone qui sera remplie avec le dégradé. Les coordonnées du rectangle sont exprimées en points (1 point = 1/72 pouce).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Étape 6 : définir les couleurs et les fractions du dégradé
Un tableau `float[]` définit la position de chaque arrêt de couleur (de 0.0 à 1.0). Les objets `Color` contiennent les valeurs RVB réelles. Vous pouvez utiliser n’importe quel `java.awt.Color` que vous souhaitez.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Étape 7 : créer la transformation du dégradé
`AffineTransform` met à l’échelle et fait pivoter le dégradé. Pour un dégradé purement vertical, il suffit de mettre à l’échelle l’axe Y ; la rotation peut être ajoutée plus tard si désiré.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Étape 8 : créer le pinceau de dégradé linéaire vertical
`LinearGradientPaint` associe le rectangle, les arrêts de couleur et la transformation. Cet objet est ensuite transmis au contexte graphique.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Étape 9 : définir le pinceau et remplir le rectangle
`Graphics2D.setPaint` applique le dégradé, et `fill` le rend à l’intérieur du rectangle que vous avez défini précédemment.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Étape 10 : fermer la page courante et enregistrer le document
L’appel à `document.save` écrit l’ensemble du flux PostScript dans le fichier de sortie et libère toutes les ressources natives.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Félicitations ! Vous avez ajouté avec succès un dégradé vertical à votre document PostScript Java en utilisant Aspose.Page for Java.

## Problèmes courants et solutions
- **Le dégradé apparaît plat :** Assurez‑vous que l’échelle du `AffineTransform` correspond aux dimensions du rectangle.  
- **Les couleurs semblent délavées :** Vérifiez que vous utilisez le bon `ColorSpaceType` (SRGB) et que le tableau de fractions est ordonné de 0.0 à 1.0.  
- **Le fichier n’est pas généré :** Vérifiez que le répertoire de sortie (`dataDir`) existe et que l’application possède les permissions d’écriture.  

## Questions fréquemment posées
**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçu pour fonctionner de manière transparente avec d’autres bibliothèques Java telles qu’Apache Commons ou Spring.

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.Page for Java ?**  
R : Oui, vous pouvez obtenir un essai gratuit sur la [page de téléchargement d’essai gratuit](https://releases.aspose.com/).

**Q : Où puis‑je trouver une documentation supplémentaire ?**  
R : Une documentation détaillée est disponible dans la [référence API Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q : Comment puis‑je acheter Aspose.Page for Java ?**  
R : Vous pouvez acheter Aspose.Page for Java sur la [page d’achat Aspose.Page](https://purchase.aspose.com/buy).

**Q : Existe‑t‑il un forum de discussion sur Aspose.Page ?**  
R : Oui, vous pouvez rejoindre le forum communautaire [forum communautaire Aspose.Page](https://forum.aspose.com/c/page/39).

## Questions fréquemment posées supplémentaires

**Q : Puis‑je créer d’autres directions de dégradé (horizontal, diagonal) ?**  
R : Absolument. Ajustez les points de départ et d’arrivée dans `LinearGradientPaint` et modifiez l’angle de rotation dans le `AffineTransform`.

**Q : Cette méthode fonctionne‑t‑elle également avec la sortie PDF ?**  
R : La même logique de dégradé peut être appliquée lors de l’enregistrement en PDF en utilisant `PdfSaveOptions` à la place de `PsSaveOptions`.

**Q : Comment changer dynamiquement la taille du dégradé ?**  
R : Calculez les dimensions du rectangle à l’exécution et transmettez ces valeurs à la fois au constructeur `Rectangle2D` et à celui de `AffineTransform`.

---

**Dernière mise à jour :** 2026-09-14  
**Testé avec :** Aspose.Page for Java 24.11 (dernière version)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un dégradé radial en PostScript avec Aspose.Page pour Java](/page/java/postscript-gradient-addition/)
- [Comment convertir un PostScript en PDF avec l’API Aspose.Page Java](/page/java/postscript-conversion/to-pdf/)
- [Tutoriel sur la transparence Aspose.Page – Ajouter de la transparence en PostScript Java](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}