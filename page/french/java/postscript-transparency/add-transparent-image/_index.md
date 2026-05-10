---
date: 2026-03-05
description: Apprenez à définir la couleur d'arrière-plan en Java et à ajouter des
  images transparentes au PostScript à l'aide d'Aspose.Page pour Java. Convertissez
  des PNG en PostScript en toute simplicité.
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'Définir la couleur d''arrière-plan Java : Ajouter une image transparente à
  PS'
url: /fr/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la couleur d'arrière-plan Java : ajouter une image transparente à PS

## Introduction
Si vous devez **set background color java** tout en travaillant avec Java PostScript, l'ajout d'images transparentes peut donner à vos documents un aspect soigné et professionnel. Dans ce tutoriel, nous vous guiderons à travers le processus complet de définition d'un arrière‑plan coloré, de conversion d'un PNG en PostScript, et de dessin d'images opaques et transparentes à l'aide de la bibliothèque Aspose.Page for Java. À la fin, vous serez capable de **add image to postscript** les fichiers avec un contrôle total de l'opacité.

## Réponses rapides
- **Quelle bibliothèque gère la transparence dans Java PostScript ?** Aspose.Page for Java.  
- **Puis-je définir une couleur d'arrière-plan avant de dessiner les images ?** Yes – use `document.setPaint()` and `fill()`.  
- **Comment convertir un PNG en PostScript ?** Load the PNG with `ImageIO.read()` and draw it with `drawImage` or `drawTransparentImage`.  
- **L'opacité est‑elle prise en charge pour les images ?** Use `drawTransparentImage` to specify an opacity value (0‑255).  
- **Ai‑je besoin d'une licence pour une utilisation en production ?** A valid Aspose.Page for Java license is required; a free trial is available.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

1. **Java Development Kit (JDK)** – la dernière version installée.  
2. **Aspose.Page for Java** – téléchargez depuis le [website](https://releases.aspose.com/page/java/).  
3. **Document Directory** – un dossier où vous écrirez les fichiers PostScript.  
4. **Translucent Image File** – par ex., `mask1.png`, que nous utiliserons pour démontrer la transparence.

## Importer les packages
Dans votre projet Java, importez les classes nécessaires. Ce bloc reste inchangé :

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Étape 1 : définir la couleur d'arrière‑plan Java
Ici, nous créons le document, choisissons le format A4 et remplissons un rectangle rouge pour illustrer le contraste d'arrière‑plan.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

## Étape 2 : traduire les coordonnées
Déplacez le curseur de dessin vers un emplacement pratique sur la page avant de placer les images.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Étape 3 : créer l'objet Image
Chargez le fichier PNG (notre étape **convert png to postscript**).

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Étape 4 : ajouter une image opaque
Dessinez l'image normalement—cela montre **add image to postscript** sans transparence.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Étape 5 : ajouter une image transparente (dessiner l'image avec opacité)
Nous utilisons maintenant `drawTransparentImage` pour rendre le même PNG avec une opacité totale (255). Ajustez la valeur pour contrôler la transparence.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Étape 6 : enregistrer et fermer
Finalisez le document et libérez les ressources.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Pourquoi c’est important
Définir une couleur d'arrière‑plan avec Java vous fournit une toile qui peut mettre en valeur les graphiques superposés. En combinant cela avec **draw image with opacity**, vous pouvez créer des filigranes, des logos ou des maquettes UI directement en PostScript sans avoir besoin d'outils d'édition externes.

## Problèmes courants et astuces
- **Image non transparente** : Vérifiez que le PNG contient réellement un canal alpha.  
- **Couleurs incorrectes** : Rappelez‑vous que le rectangle d'arrière‑plan est dessiné avant l'image ; modifiez les valeurs `Color` pour correspondre à votre conception.  
- **Performance** : Pour les gros documents, réutilisez une seule instance `AffineTransform` afin de réduire la surcharge de création d'objets.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for Java avec d'autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java peut être intégré de manière transparente avec d'autres bibliothèques Java pour améliorer les capacités de traitement de documents.

**Q : Une version d'essai gratuite est‑elle disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Page for Java depuis [here](https://releases.aspose.com/).

**Q : Comment puis‑je obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Vous pouvez acquérir une licence temporaire via [this link](https://purchase.aspose.com/temporary-license/).

**Q : Existe‑t‑il des forums pour le support d'Aspose.Page for Java ?**  
R : Oui, visitez le [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

**Q : Où puis‑je trouver la documentation d'Aspose.Page for Java ?**  
R : Reportez‑vous à la documentation complète [documentation](https://reference.aspose.com/page/java/) pour des informations détaillées sur Aspose.Page for Java.

---

**Dernière mise à jour :** 2026-03-05  
**Testé avec :** Aspose.Page for Java 24.11 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}