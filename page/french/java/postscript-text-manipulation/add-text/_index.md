---
date: 2025-12-14
description: Apprenez à définir la couleur du texte en Java avec Aspose.Page for Java,
  à ajouter du texte au PostScript et à appliquer un contour de texte pour un style
  de document riche.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Définir la couleur du texte en Java avec Aspose.Page – Guide de manipulation
  du texte
url: /fr/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la couleur du texte Java avec Aspose.Page – Guide de manipulation de texte

## Introduction
Bienvenue dans notre guide étape par étape sur **set text color java** lors de la manipulation de fichiers PostScript avec Aspose.Page pour Java. Aspose.Page pour Java est une bibliothèque puissante qui permet aux développeurs de créer et **générer des fichiers postscript**, de manipuler les polices et de styliser le texte avec précision. Dans ce tutoriel, vous apprendrez comment ajouter du texte, changer sa couleur, ajuster la taille et même **appliquer un texte en contour** pour un rendu soigné.

## Quick Answers
- **Quelle bibliothèque me permet de définir la couleur du texte en Java ?** Aspose.Page pour Java.  
- **Puis‑je utiliser des polices système et des polices personnalisées ?** Oui, les deux sont prises en charge.  
- **Comment modifier la taille du texte ?** En spécifiant la taille de la police lors de la création du `Font` ou du `DrFont`.  
- **Est‑il possible de tracer et remplir le texte simultanément ?** Absolument – utilisez `fillAndStrokeText`.  
- **Quel format de sortie ce tutoriel produit‑il ?** Un document PostScript (`.ps`).

## What is “set text color java”?
Définir la couleur du texte en Java signifie créer l’objet `Color` que le moteur de rendu (ici, Aspose.Page) utilise lors du dessin des caractères sur une page. Cette opération est essentielle pour créer des documents visuellement distincts, notamment lorsqu’on génère des **postscript documents** de façon programmatique.

## Why use Aspose.Page for Java?
- **Contrôle complet** sur la génération de PostScript sans besoin d’un interpréteur PostScript natif.  
- **Prise en charge des polices système et externes**, vous permettant d’incorporer n’importe quelle typographie.  
- **API simple** pour remplir, tracer et **remplir et tracer du texte**, offrant une grande flexibilité de style.  
- **Compatibilité multiplateforme** – écrivez une fois, exécutez partout où Java fonctionne.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en programmation Java.  
- La bibliothèque Aspose.Page pour Java installée. Vous pouvez la télécharger depuis la [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Les polices nécessaires disponibles dans le dossier spécifié. Des détails supplémentaires se trouvent dans la [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Page pour Java :

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Step 1: Set Up the Document
Tout d’abord, nous créons un nouveau **document PostScript** et configurons les options de sortie.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## How to Set Text Color Java Using System Font
Nous démontrons maintenant **set text color java** avec une police fournie par le système.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Astuce :** La méthode `fillText` utilise automatiquement la couleur courante si vous ne transmettez pas d’argument `Color`, qui est noir par défaut.

## Using Custom Font and Changing Text Size
Vous pouvez également **changer la taille du texte** et utiliser une police personnalisée stockée dans votre dossier de polices.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
Tracer le texte lui donne un bord net. Ici nous **appliquons un texte en contour** à l’aide d’un `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Outlining Text with Custom Font
La même technique fonctionne avec des polices personnalisées.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
Enfin, fermez la page et écrivez le fichier sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Issues & Solutions
| Problème | Solution |
|----------|----------|
| **Police non trouvée** | Vérifiez que le fichier de police est placé dans `necessary_fonts` et que le chemin du dossier est correctement ajouté via `options.setAdditionalFontsFolders`. |
| **Couleur non appliquée** | Assurez‑vous d’appeler la surcharge de `fillText` ou `outlineText` qui inclut un argument `Color`. |
| **Le contour apparaît trop fin** | Augmentez la largeur du `BasicStroke` (par ex., `new BasicStroke(3)`). |
| **Document qui ne s’ouvre pas** | Confirmez que le fichier `.ps` généré est enregistré avec la bonne extension et que votre visionneuse prend en charge le format PostScript. |

## Frequently Asked Questions

**Q :** Puis‑je utiliser mes propres polices personnalisées avec Aspose.Page pour Java ?  
**R :** Oui, vous pouvez utiliser des polices personnalisées en spécifiant le nom et la taille de la police dans la classe `DrFont`.

**Q :** Comment changer la couleur du texte ?  
**R :** Vous pouvez définir la couleur souhaitée à l’aide de la classe `Color` lors du remplissage ou du tracé du texte.

**Q :** Est‑il possible d’ajouter plusieurs pages à un document PostScript ?  
**R :** Absolument ! Vous pouvez créer plusieurs pages en répétant les étapes de création et d’enregistrement du document.

**Q :** Quel est le rôle de la classe `ExternalFontCache` ?  
**R :** `ExternalFontCache` sert à récupérer les polices personnalisées, garantissant leur disponibilité pour la manipulation du texte.

**Q :** Puis‑je appliquer différents contours au texte tracé ?  
**R :** Oui, vous pouvez personnaliser la largeur et la couleur du contour à l’aide de la classe `Stroke` et de la classe `Color`, respectivement.

## Conclusion
Félicitations ! Vous savez maintenant comment **set text color java**, modifier les tailles de police, **appliquer un texte en contour**, et **créer des fichiers de document postscript** à l’aide d’Aspose.Page pour Java. Expérimentez avec différentes polices, couleurs et styles de contour pour produire des sorties PostScript d’aspect professionnel.

---

**Dernière mise à jour :** 2025-12-14  
**Testé avec :** Aspose.Page pour Java 23.12 (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}