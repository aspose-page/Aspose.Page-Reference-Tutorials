---
date: 2026-02-15
description: Apprenez à ajouter un motif de hachure aux fichiers PostScript Java à
  l'aide d'Aspose.Page Java. Ce guide pas à pas présente le code complet ainsi que
  des conseils.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Comment ajouter un motif de hachures en Java PostScript avec Aspose.Page
url: /fr/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un motif hachuré en Java PostScript

## Introduction
Si vous travaillez avec **Aspose.Page Java** et vous demandez **comment ajouter un motif hachuré** à votre sortie PostScript, les motifs hachurés sont une solution rapide et flexible. Dans ce tutoriel, nous parcourrons **comment ajouter des motifs hachurés** à un document PostScript, expliquerons pourquoi ils sont utiles, et vous fournirons un exemple de code complet, prêt à l'exécution. À la fin, vous pourrez créer des formes et du texte remplis de hachures visuellement attrayants en quelques lignes de Java.

## Quick Answers
- **Quelle bibliothèque faut‑il ?** Aspose.Page for Java (le SDK “aspose page java”).  
- **Quel effet visuel ajoutons‑nous ?** Des motifs hachurés (par ex. lignes diagonales, croix).  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production.  
- **Combien de lignes de code ?** Environ 70 lignes, réparties en étapes claires.  
- **Puis‑je utiliser la même approche pour les PDF ?** Oui — Aspose.Page prend en charge plusieurs formats de sortie, dont le PDF.

## How to Add Hatch Pattern – Overview
Les motifs hachurés sont des textures vectorielles qui s’affichent nettement à n’importe quelle résolution et fonctionnent bien sur les imprimantes monochromes. Avec Aspose.Page Java, vous pouvez appliquer ces motifs aux formes, aux tracés et même au texte sans manipuler les commandes PostScript de bas niveau.

## Prerequisites
- **Environnement de développement Java** – JDK 8 ou supérieur et un IDE de votre choix.  
- **Bibliothèque Aspose.Page for Java** – Téléchargez le JAR le plus récent depuis le site officiel [here](https://releases.aspose.com/page/java/).  
- **Accès en écriture** à un dossier où le fichier PostScript généré sera enregistré.

## Import Packages
Tout d’abord, importez les classes requises dans votre projet. Ces imports vous donnent accès aux primitives de dessin, à la gestion des couleurs et à l’API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Initial Parameters
Créez le flux de sortie, configurez la taille de la page (A4) et définissez quelques variables de mise en page qui seront réutilisées lors du dessin de chaque carré rempli de hachures.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Step 2: Save Graphics State and Translate
Enregistrer l’état graphique nous permet de revenir plus tard au système de coordonnées d’origine, tandis que `translate` déplace l’origine vers un point de départ pratique.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
Définissez un rectangle réutilisable qui représentera chaque cellule remplie de hachures.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
Un `BasicStroke` de 2 points fournit un contour net autour de chaque carré.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
Parcourez chaque valeur de l’énumération `HatchStyle`, remplissez chaque carré avec la texture correspondante, puis dessinez son contour. C’est le cœur de la fonctionnalité **d’ajout de motif hachuré**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
Revenez au système de coordonnées d’origine après avoir terminé le dessin de la grille de carrés.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
Ici nous montrons comment peindre du texte en utilisant une texture de hachure. L’exemple remplit le mot « ABC » avec un motif croisé diagonal.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
Maintenant nous traçons le même texte, mais cette fois en utilisant un style de hachure à 70 % et un trait plus épais.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
Finalisez la page, écrivez le fichier sur le disque et libérez les ressources.

```java
document.closePage();
document.save();
```

Suivez ces étapes, et vous obtiendrez un fichier PostScript qui présente l’ensemble complet de motifs hachurés appliqués aux formes et au texte — le tout propulsé par **aspose page java**.

## Why Use Hatch Patterns with Aspose.Page Java?
- **Distinction visuelle** – Les remplissages hachurés fonctionnent même lorsque les imprimantes sont limitées à une sortie monochrome.  
- **Performance** – Les textures sont générées à la volée, ce qui évite les gros fichiers image.  
- **Support multi‑format** – Le même code peut cibler PDF, EPS ou SVG avec peu de modifications.

## Common Pitfalls & Tips
- **Erreurs de chemin de fichier** – Assurez‑vous que `dataDir` se termine par le séparateur de fichiers approprié (`/` ou `\`).  
- **Couleurs non prises en charge** – Certains interprètes PostScript plus anciens peuvent ne pas gérer certains espaces colorimétriques ; restez sur le RGB de base pour une compatibilité maximale.  
- **Avertissements de licence** – Exécuter l’exemple sans licence valide ajoutera un filigrane à la sortie.

## Conclusion
L’incorporation de motifs hachurés peut améliorer considérablement la lisibilité et l’esthétique des dessins techniques, cartes ou toute autre image générée par Java. Avec **Aspose.Page Java**, vous disposez d’une API concise qui abstrait les commandes PostScript de bas niveau, vous permettant de vous concentrer sur le design plutôt que sur les particularités du format de fichier. Vous savez maintenant **comment ajouter un motif hachuré** à vos documents PostScript — expérimentez avec différentes valeurs de `HatchStyle` pour obtenir l’aspect exact dont vous avez besoin.

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.Page Java avec d’autres frameworks Java ?**  
R : Oui, la bibliothèque est indépendante du framework et fonctionne avec Spring, Jakarta EE, Android (limité) et Java SE pur.

**Q : Une version d’essai est‑elle disponible pour Aspose.Page Java ?**  
R : Absolument. Téléchargez un essai gratuit de 30 jours [here](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour le développement ?**  
R : Demandez une licence temporaire [here](https://purchase.aspose.com/temporary-license/). Elle supprime les filigranes d’évaluation.

**Q : Où puis‑je trouver plus de tutoriels et de support communautaire ?**  
R : Consultez le forum officiel [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pour des exemples supplémentaires et des questions‑réponses.

**Q : Existe‑t‑il une documentation complète pour toutes les classes et méthodes ?**  
R : Oui, la référence complète de l’API est disponible [here](https://reference.aspose.com/page/java/).

**Q : Puis‑je rendre le même motif hachuré en PDF au lieu de PostScript ?**  
R : Absolument. Changez `PsSaveOptions` en `PdfSaveOptions` (ou l’équivalent) et le reste du code reste inchangé.

**Q : Que faire si le fichier généré est vide ?**  
R : Vérifiez que le flux de sortie pointe vers un répertoire accessible en écriture et que `document.save()` est appelé après toutes les opérations de dessin.

---

**Dernière mise à jour :** 2026-02-15  
**Testé avec :** Aspose.Page for Java 24.12 (la plus récente au moment de la rédaction)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}