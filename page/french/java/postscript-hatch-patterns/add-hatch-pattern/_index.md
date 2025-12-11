---
date: 2025-12-08
description: Apprenez à ajouter des motifs hachurés aux documents PostScript Java
  en utilisant Aspose.Page Java. Ce guide étape par étape vous montre comment ajouter
  efficacement des graphiques à motifs hachurés.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java : Ajouter un motif de hachure dans le PostScript Java'
url: /fr/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un motif hachuré en Java PostScript

## Introduction
Si vous travaillez avec **Aspose.Page Java** et que vous devez enrichir votre sortie PostScript avec des graphiques texturés, les motifs hachurés sont une solution rapide et flexible. Dans ce tutoriel, nous vous montrerons **comment ajouter des motifs hachurés** à un document PostScript, expliquerons pourquoi ils sont utiles et vous fournirons un exemple de code complet, prêt à être exécuté. À la fin, vous pourrez créer des formes et du texte remplis de hachures visuellement attrayants en quelques lignes de Java seulement.

## Réponses rapides
- **Quelle bibliothèque est‑t‑il nécessaire ?** Aspose.Page for Java (le SDK “aspose page java”).  
- **Quel effet visuel ajoutons‑nous ?** Motifs hachurés (par ex., lignes diagonales, croix).  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production.  
- **Combien de lignes de code ?** Environ 70 lignes, réparties en étapes claires.  
- **Puis‑je utiliser la même approche pour les PDF ?** Oui — Aspose.Page prend en charge plusieurs formats de sortie, dont le PDF.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- **Environnement de développement Java** – JDK 8 ou supérieur et un IDE de votre choix.  
- **Bibliothèque Aspose.Page for Java** – Téléchargez le JAR le plus récent depuis le site officiel [ici](https://releases.aspose.com/page/java/).  
- **Accès en écriture** à un dossier où le fichier PostScript généré sera enregistré.

## Importer les packages
Tout d’abord, ajoutez les classes requises à votre projet. Ces imports vous donnent accès aux primitives de dessin, à la gestion des couleurs et à l’API Aspose.Page.

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

## Étape 1 : Configurer les paramètres initiaux
Créez le flux de sortie, configurez la taille de page (A4) et définissez quelques variables de mise en page qui seront réutilisées lors du dessin de chaque carré rempli de hachures.

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

## Étape 2 : Enregistrer l’état graphique et translater
Enregistrer l’état graphique nous permet de revenir au système de coordonnées d’origine plus tard, tandis que `translate` déplace l’origine vers un point de départ pratique.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Étape 3 : Créer un carré pour chaque motif
Définissez un rectangle réutilisable qui représentera chaque cellule remplie de hachures.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Étape 4 : Configurer le stylo pour le contour du carré de motif
Un `BasicStroke` de 2 points offre un contour net autour de chaque carré.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Étape 5 : Parcourir les motifs hachurés
Parcourez chaque valeur de l’énumération `HatchStyle`, remplissez chaque carré avec la texture correspondante, puis dessinez son contour. C’est le cœur de la fonctionnalité **d’ajout de motif hachuré**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Étape 6 : Restaurer l’état graphique
Revenez au système de coordonnées d’origine après avoir terminé le dessin de la grille de carrés.

```java
document.writeGraphicsRestore();
```

## Étape 7 : Remplir le texte avec un motif hachuré
Nous montrons ici comment peindre du texte en utilisant une texture hachurée. L’exemple remplit le mot « ABC » avec un motif diagonal‑croisé.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Étape 8 : Tracer le contour du texte avec un motif hachuré
Maintenant, nous traçons le contour du même texte, mais cette fois‑ci en utilisant un style de hachure à 70 % et un trait plus épais.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Étape 9 : Fermer et enregistrer le document
Finalisez la page, écrivez le fichier sur le disque et libérez les ressources.

```java
document.closePage();
document.save();
```

Suivez ces étapes, et vous obtiendrez un fichier PostScript qui présente l’ensemble complet des motifs hachurés appliqués à la fois aux formes et au texte—le tout propulsé par **aspose page java**.

## Pourquoi utiliser les motifs hachurés avec Aspose.Page Java ?
- **Distinction visuelle** – Les remplissages hachurés fonctionnent même lorsque les imprimantes sont limitées à une sortie monochrome.  
- **Performance** – Les textures sont générées à la volée, ce qui évite les gros fichiers image.  
- **Support multi‑format** – Le même code peut cibler PDF, EPS ou SVG avec peu de modifications.

## Pièges courants et conseils
- **Erreurs de chemin de fichier** – Assurez‑vous que `dataDir` se termine par le séparateur de fichier approprié (`/` ou `\`).  
- **Couleurs non prises en charge** – Certains interprètes PostScript plus anciens peuvent ne pas gérer certains espaces colorimétriques ; restez sur le RGB de base pour une compatibilité maximale.  
- **Avertissements de licence** – Exécuter l’exemple sans licence valide ajoutera un filigrane à la sortie.

## Conclusion
L’incorporation de motifs hachurés peut améliorer considérablement la lisibilité et l’esthétique des dessins techniques, cartes ou toute autre graphique générée par Java. Avec **Aspose.Page Java**, vous bénéficiez d’une API concise qui abstrait les commandes PostScript de bas niveau, vous permettant de vous concentrer sur le design plutôt que sur les particularités du format de fichier.

## Foire aux questions

**Q : Puis‑je utiliser Aspose.Page Java avec d’autres frameworks Java ?**  
R : Oui, la bibliothèque est indépendante du framework et fonctionne avec Spring, Jakarta EE, Android (limité) et Java SE pur.

**Q : Une version d’essai est‑elle disponible pour Aspose.Page Java ?**  
R : Absolument. Téléchargez un essai gratuit de 30 jours [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour le développement ?**  
R : Demandez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/). Elle supprime les filigranes d’évaluation.

**Q : Où puis‑je trouver plus de tutoriels et de support communautaire ?**  
R : Visitez le forum officiel [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pour des exemples supplémentaires et des Q&R.

**Q : Existe‑t‑il une documentation complète pour toutes les classes et méthodes ?**  
R : Oui, la référence API complète est disponible [ici](https://reference.aspose.com/page/java/).

---

**Dernière mise à jour :** 2025-12-08  
**Testé avec :** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
