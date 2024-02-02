---
title: Manipulation de texte Java Aspose.Page
linktitle: Ajouter du texte en Java PostScript
second_title: API Java Aspose.Page
description: Découvrez la puissance d'Aspose.Page pour Java dans notre didacticiel sur l'ajout de texte aux documents PostScript. Apprenez à utiliser facilement les polices système et personnalisées.
type: docs
weight: 10
url: /fr/java/postscript-text-manipulation/add-text/
---
## Introduction
Bienvenue dans notre guide étape par étape sur l'ajout de texte dans Java PostScript à l'aide d'Aspose.Page pour Java. Aspose.Page pour Java est une bibliothèque puissante qui permet aux développeurs de manipuler facilement des documents PostScript. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout de texte, d'utilisation de polices système et personnalisées, de contour du texte et d'incorporation de traits pour un résultat visuellement attrayant.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
- Connaissance de base de la programmation Java.
-  Aspose.Page pour la bibliothèque Java installée. Vous pouvez le télécharger depuis le[Page de téléchargement d'Aspose.Page pour Java](https://releases.aspose.com/page/java/).
-  Polices nécessaires disponibles dans le dossier spécifié. Vous pouvez trouver des informations supplémentaires dans le[Aspose.Page pour la documentation Java](https://reference.aspose.com/page/java/).
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Page for Java :
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
## Étape 1 : configurer le document
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Créer un flux de sortie pour un document PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Un texte à écrire dans un fichier PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Créer un nouveau document PS d'une page
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Étape 2 : Utilisation de la police système pour remplir le texte
```java
// Utiliser la police système pour remplir le texte
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Remplir le texte avec la couleur par défaut ou déjà définie (noir)
document.fillText(str, font, 50, 100);
// Remplissez le texte avec de la couleur bleue
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Étape 3 : Utilisation d'une police personnalisée pour remplir le texte
```java
// Utiliser une police personnalisée pour remplir le texte
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Remplir le texte avec la couleur par défaut ou déjà définie (noir)
document.fillText(str, drFont, 50, 200);
// Remplissez le texte avec de la couleur bleue
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Étape 4 : Décrire le texte avec la police système
```java
// Utilisation de la police système pour décrire le texte
document.outlineText(str, font, 50, 300);
// Décrire le texte avec un stylo de couleur bleu-violet à 2 points de largeur
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Remplissez le texte avec de la couleur orange et tracez-le avec un stylo bleu à 2 points de largeur.
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Étape 5 : Décrire le texte avec une police personnalisée
```java
// Utilisation d'une police personnalisée pour décrire le texte
document.outlineText(str, drFont, 50, 450);
// Décrire le texte avec un stylo de couleur bleu-violet à 2 points de largeur
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Remplissez le texte avec de la couleur orange et tracez-le avec un stylo bleu à 2 points de largeur.
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Étape 6 : Enregistrez le document
```java
// Fermer la page actuelle
document.closePage();
// Enregistrez le document
document.save();
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter du texte dans Java PostScript à l'aide d'Aspose.Page pour Java. Expérimentez avec différentes polices, couleurs et options de plan pour améliorer davantage votre document.
## Questions fréquemment posées
### Puis-je utiliser mes propres polices personnalisées avec Aspose.Page pour Java ?
 Oui, vous pouvez utiliser des polices personnalisées en spécifiant le nom et la taille de la police dans le champ`DrFont` classe.
### Comment puis-je changer la couleur du texte ?
 Vous pouvez définir la couleur souhaitée à l'aide du`Color` classe lors du remplissage ou du contour du texte.
### Est-il possible d'ajouter plusieurs pages à un document PostScript ?
Absolument! Vous pouvez créer plusieurs pages en répétant les étapes de création et d'enregistrement du document.
###  Quel est le but du`ExternalFontCache` class?
`ExternalFontCache` est utilisé pour récupérer des polices personnalisées, garantissant qu'elles sont disponibles pour la manipulation de texte.
### Puis-je appliquer différents traits au texte souligné ?
 Oui, vous pouvez personnaliser la largeur et la couleur du trait à l'aide du`Stroke` classe et`Color` classe, respectivement.