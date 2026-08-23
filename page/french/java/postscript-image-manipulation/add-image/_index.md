---
date: 2026-08-23
description: Apprenez comment utiliser la manipulation d'images aspose.page en Java
  pour intégrer et faire pivoter des images dans des fichiers PostScript avec des
  exemples Java clairs.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Ajouter une image en Java PostScript
og_description: Apprenez comment utiliser la manipulation d'images aspose.page en
  Java pour intégrer et faire pivoter des images dans des fichiers PostScript, avec
  des exemples de code Java step‑by‑step.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Comment utiliser la manipulation d'images aspose.page en Java pour ajouter
  une image
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Comment utiliser la manipulation d'images aspose.page en Java pour ajouter
  une image
url: /fr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser aspose.page image manipulation java pour ajouter une image

## Introduction
Dans ce tutoriel, vous apprendrez comment **utiliser aspose.page image manipulation java** pour créer des fichiers PostScript, incorporer des images raster et appliquer des transformations de translation et de rotation. À la fin du guide, vous serez capable de générer une sortie PostScript pixel‑parfait depuis Java — idéal pour les rapports automatisés, les pipelines d’impression ou tout flux de travail nécessitant un placement précis des images dans un document PostScript.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis‑je ajouter plusieurs images ?** Oui – répétez les étapes de transformation et de dessin pour chaque image  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production  
- **Quelle version de Java est prise en charge ?** Java 8 et ultérieure  
- **La rotation d’image est‑elle prise en charge ?** Absolument – utilisez `AffineTransform.rotate()`  

## Qu’est‑ce que aspose.page image manipulation java ?
`aspose.page image manipulation java` est l’API Aspose.Page qui vous permet de créer, modifier et rendre des documents PostScript à partir de code Java, incluant un contrôle complet du placement, du redimensionnement et de la rotation des images. Avec cette API, vous évitez la syntaxe PostScript de bas niveau et laissez la bibliothèque gérer la conversion de format et l’incorporation en interne.

## Pourquoi utiliser aspose.page pour la manipulation d’images ?
Aspose.Page propose **plus de 50 formats d’image** (y compris JPEG, PNG, BMP, TIFF) et peut les incorporer dans le PostScript sans charger l’ensemble du document en mémoire, permettant le traitement de fichiers contenant des centaines de pages tout en maintenant l’utilisation de la mémoire en dessous de 100 Mo sur un serveur type. L’API de haut niveau abstrait les commandes PostScript complexes, ainsi vous écrivez du code Java concis au lieu d’opérateurs PS bruts.

## Prérequis
- Java Development Kit (JDK) 8 ou plus récent installé.  
- Bibliothèque Aspose.Page for Java – téléchargez‑la sur **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Familiarité de base avec la syntaxe Java et la programmation orientée objet.

## Qu’est‑ce que create postscript java ?
Créer un fichier PostScript depuis Java signifie générer de façon programmatique un document `.ps` qui décrit la mise en page, les graphiques vectoriels et les images raster en utilisant le langage PostScript. Aspose.Page traduit vos appels Java en instructions PostScript valides, vous permettant de produire des fichiers prêts à l’impression sans interpréteur PostScript séparé.

## Comment ajouter une image avec translation et rotation étape par étape

Chargez votre image, appliquez un `AffineTransform` et dessinez‑la sur la page. Les étapes suivantes décrivent la séquence exacte à suivre.

### Étape 1 : enregistrer l’état graphique
Enregistrer l’état graphique isole vos transformations afin de pouvoir revenir en arrière plus tard. Cela équivaut à l’opérateur `gsave` en PostScript brut.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Étape 2 : translation et transformation (translation et rotation de l’image)
Tout d’abord, créez un `BufferedImage` à partir du fichier source, puis construisez un `AffineTransform` qui translate l’image aux coordonnées souhaitées et la fait pivoter autour de son centre. `AffineTransform.rotate` attend un angle en radians, donc convertissez les degrés avec `Math.toRadians(degrees)`.

**AffineTransform** est une classe Java qui représente une transformation affine 2‑D telle que la translation, la rotation, le redimensionnement ou le cisaillement.  
**BufferedImage** est une classe Java qui stocke une image en mémoire sous forme de raster de pixels.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Étape 3 : ajouter l’image au document
Après avoir configuré la transformation, dessinez l’image sur la page courante. La bibliothèque convertit automatiquement le `BufferedImage` en un flux d’image PostScript approprié.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Étape 4 : restaurer l’état graphique
Appeler restore (`grestore`) rétablit l’état graphique à celui qui était avant l’enregistrement, garantissant que les commandes de dessin suivantes ne sont pas affectées par la transformation précédente.

```java
document.drawImage(image, transform, null);
```

### Étape 5 : fermer la page courante et enregistrer
Terminez la page, fermez le document et écrivez le fichier de sortie sur le disque.

```java
document.writeGraphicsRestore();
```

Vous pouvez répéter la séquence ci‑dessus pour incorporer d’autres images, en ajustant les coordonnées de translation et l’angle de rotation à chaque fois.

## Problèmes courants et solutions
- **FileNotFoundException** : Vérifiez que le `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) et que le nom du fichier image correspond exactement.  
- **ImageIO.read renvoie null** : Assurez‑vous que le format de l’image fait partie de la liste prise en charge (JPEG, PNG, BMP, GIF, TIFF).  
- **Angle de rotation incorrect** : `AffineTransform.rotate` fonctionne avec des radians ; utilisez `Math.toRadians(degrees)` pour convertir depuis les degrés.  
- **Pics de mémoire sur de grandes pages** : Utilisez `Document.save` avec `saveOptions.setCompress(true)` pour réduire l’empreinte mémoire.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?**  
R : La bibliothèque principale est uniquement Java, mais Aspose propose des API équivalentes pour .NET, C++ et Python, chacune adaptée à sa plateforme.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à l’essai gratuit **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Vous pouvez obtenir une licence temporaire **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q : Où puis‑je trouver le support communautaire et les discussions concernant Aspose.Page for Java ?**  
R : Consultez le **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** pour l’assistance communautaire.

**Q : Existe‑t‑il des ressources supplémentaires pour l’achat d’Aspose.Page for Java ?**  
R : Vous pouvez acheter la bibliothèque **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Conclusion
Vous disposez maintenant d’un exemple complet, de bout en bout, de **aspose.page image manipulation java** qui crée un fichier PostScript, translate et fait pivoter une image, puis enregistre le résultat. Explorez la **[documentation](https://reference.aspose.com/page/java/)** complète pour découvrir des fonctionnalités avancées telles que les graphiques vectoriels, les tailles de page personnalisées et le rendu de texte.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## Tutoriels associés

- [Comment convertir PostScript en PDF en utilisant l’API Aspose.Page Java](/page/java/postscript-conversion/to-pdf/)
- [Comment ajouter un dégradé : dégradé diagonal en Java PostScript avec Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Comment ajouter un motif hachuré en Java PostScript avec Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}