---
date: 2026-02-20
description: Apprenez à définir la couleur du texte en Java avec Aspose.Page for Java,
  à modifier la taille de la police en Java, à générer un fichier PostScript, à remplir
  et tracer le texte, et à utiliser des polices personnalisées en Java lors de la
  création d’un document PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Définir la couleur du texte en Java avec Aspose.Page – Guide de manipulation
  de texte
url: /fr/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la couleur du texte Java avec Aspose.Page – Guide de manipulation de texte

## Introduction
Bienvenue dans notre guide étape par étape sur **set text color java** tout en travaillant avec des fichiers PostScript à l'aide d'Aspose.Page pour Java. Aspose.Page pour Java est une bibliothèque puissante qui permet aux développeurs **create postscript document**, de manipuler les polices et de styliser le texte avec précision. Dans ce tutoriel, vous apprendrez comment ajouter du texte, changer sa couleur, **change font size java**, et même **apply fill and stroke text** pour un rendu soigné.

## Réponses rapides
- **Quelle bibliothèque me permet de définir la couleur du texte en Java ?** Aspose.Page for Java.  
- **Puis-je utiliser des polices système et des polices personnalisées ?** Oui, les deux sont prises en charge, et vous pouvez **use custom fonts java** facilement.  
- **Comment changer la taille du texte ?** En spécifiant la taille de la police lors de la création du `Font` ou du `DrFont`.  
- **Est-il possible de tracer et remplir le texte simultanément ?** Absolument – utilisez `fillAndStrokeText`.  
- **Quel format de sortie ce tutoriel produit‑il ?** Un document PostScript (`.ps`), que vous pouvez **generate postscript file** programmétiquement.

## Qu’est‑ce que “set text color java” ?
Définir la couleur du texte en Java signifie définir l'objet `Color` que le moteur de rendu (ici, Aspose.Page) utilise lors du dessin des caractères sur une page. Cette opération est essentielle pour créer des documents visuellement distincts, surtout lorsque vous devez **generate postscript file** de manière programmatique.

## Pourquoi utiliser Aspose.Page pour Java ?
- **Contrôle total** sur la génération de PostScript sans nécessiter d’interpréteur natif.  
- **Prise en charge des polices système et externes**, vous permettant d’intégrer n’importe quelle typographie dont vous avez besoin.  
- **API simple** pour remplir, tracer et **fill and stroke text**, vous offrant une flexibilité de style.  
- **Compatibilité multiplateforme** – écrivez une fois, exécutez partout où Java fonctionne.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page pour Java installée. Vous pouvez la télécharger depuis la [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Polices nécessaires disponibles dans le dossier spécifié. Des détails supplémentaires sont dans la [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Importer les packages
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

## Étape 1 : Configurer le document
Tout d'abord, nous créons un nouveau **PostScript document** et configurons les options de sortie.

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

## Comment définir la couleur du texte Java en utilisant une police système
Nous allons maintenant démontrer **set text color java** avec une police fournie par le système.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Astuce :** La méthode `fillText` utilise automatiquement la couleur actuelle si vous ne passez pas d’argument `Color`, qui par défaut est noir.

## Utilisation d’une police personnalisée et modification de la taille du texte
Vous pouvez également **change font size java** et utiliser une police personnalisée stockée dans votre dossier de polices.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Contour (Trait) du texte – Appliquer le trait du texte
Tracer le texte lui donne un bord net. Ici, nous **apply stroke text** en utilisant un `BasicStroke`.

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

## Contour du texte avec police personnalisée
La même technique fonctionne avec des polices personnalisées.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Étape 6 : Enregistrer le document
Enfin, fermez la page et écrivez le fichier sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Pourquoi cela importe
Pouvoir **set text color java** et combiner remplissage et contour vous donne un contrôle artistique complet sur la sortie PostScript finale. Que vous génériez des factures, des certificats ou des graphiques personnalisés, la capacité de **create postscript document** avec un style précis réduit le besoin de post‑traitement dans les éditeurs graphiques.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Police non trouvée** | Assurez‑vous que le fichier de police est placé dans `necessary_fonts` et que le chemin du dossier est correctement ajouté via `options.setAdditionalFontsFolders`. |
| **Couleur non appliquée** | Vérifiez que vous appelez la surcharge de `fillText` ou `outlineText` qui inclut un argument `Color`. |
| **Le trait apparaît trop fin** | Augmentez la largeur du `BasicStroke` (par ex., `new BasicStroke(3)`). |
| **Document qui ne s’ouvre pas** | Confirmez que le fichier `.ps` généré est enregistré avec la bonne extension et que votre visualiseur supporte le PostScript. |

## Questions fréquemment posées

**Q :** Puis‑je utiliser mes propres polices personnalisées avec Aspose.Page pour Java ?  
**R :** Oui, vous pouvez **use custom fonts java** en spécifiant le nom et la taille de la police dans la classe `DrFont`.

**Q :** Comment puis‑je changer la couleur du texte ?  
**R :** Vous pouvez définir la couleur souhaitée en utilisant la classe `Color` lors du remplissage ou du contour du texte.

**Q :** Est‑il possible d’ajouter plusieurs pages à un document PostScript ?  
**R :** Absolument ! Vous pouvez créer plusieurs pages en répétant les étapes de création et d’enregistrement du document.

**Q :** Quel est le but de la classe `ExternalFontCache` ?  
**R :** `ExternalFontCache` est utilisée pour récupérer des polices personnalisées, garantissant qu’elles sont disponibles pour la manipulation du texte.

**Q :** Puis‑je appliquer différents traits au texte contourné ?  
**R :** Oui, vous pouvez personnaliser la largeur et la couleur du trait en utilisant respectivement les classes `Stroke` et `Color`.

## Conclusion
Félicitations ! Vous savez maintenant comment **set text color java**, **change font size java**, **apply fill and stroke text**, et **create postscript document** à l’aide d’Aspose.Page pour Java. Expérimentez avec différentes polices, couleurs et styles de contour pour produire une sortie PostScript d’aspect professionnel.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}