---
date: 2026-08-18
description: Découvrez comment ajouter un motif hachuré aux fichiers Java PostScript
  en utilisant Aspose.Page Java. Ce guide pas à pas montre le code complet et des
  conseils.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Ajouter un motif hachuré dans Java PostScript
og_description: Découvrez comment ajouter un motif hachuré dans Java PostScript en
  utilisant Aspose.Page. Suivez ce tutoriel pas à pas pour créer rapidement des graphiques
  remplis de hachures.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Comment ajouter un motif hachuré dans Java PostScript – guide Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Comment ajouter un motif hachuré dans Java PostScript
url: /fr/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un motif hachuré en Java PostScript

## Introduction
Si vous travaillez avec **Aspose.Page Java** et vous demandez **comment ajouter un motif hachuré** à votre sortie PostScript, les motifs hachurés sont une solution rapide et flexible. Dans ce tutoriel, nous passerons en revue **comment ajouter des hachures** à un document PostScript, expliquerons pourquoi ils sont utiles, et vous fournirons un exemple de code complet, prêt à l'exécution. À la fin, vous pourrez créer des formes et du texte remplis de hachures visuellement attrayants en quelques lignes de Java.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Quel effet visuel ajoutons‑nous ?** Motifs hachurés (p. ex., lignes diagonales, croix).  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production.  
- **Combien de lignes de code ?** Environ 70 lignes, réparties en étapes claires.  
- **Puis‑je utiliser la même approche pour les PDF ?** Oui—Aspose.Page prend en charge plusieurs formats de sortie, dont le PDF.

## Qu’est‑ce qu’un motif hachuré ?
Un motif hachuré est un remplissage vectoriel composé de lignes ou de formes répétées qui crée un effet de texture. Comme il est défini mathématiquement, le motif s’agrandit sans perte de qualité, ce qui le rend idéal pour l’impression haute résolution et les sorties monochromes.

## Pourquoi utiliser des motifs hachurés avec Aspose.Page Java ?
Aspose.Page prend en charge **plus de 10 formats de sortie** (dont PostScript, PDF, EPS, SVG et XPS) et peut rendre des remplissages hachurés sur des documents allant jusqu’à **500 pages** sans charger le fichier complet en mémoire. Cela signifie que vous bénéficiez d’une performance rapide, d’une faible empreinte mémoire et de résultats visuels cohérents sur tous les formats pris en charge.

## Comment ajouter un motif hachuré – aperçu
Les motifs hachurés sont des textures vectorielles qui s’affichent proprement à n’importe quelle résolution et fonctionnent bien sur les imprimantes monochromes. Avec Aspose.Page Java, vous pouvez appliquer ces motifs à des formes, des tracés et même du texte sans manipuler les commandes PostScript de bas niveau.

## Prérequis
- **Environnement de développement Java** – JDK 8 ou supérieur et un IDE de votre choix.  
- **Bibliothèque Aspose.Page for Java** – Téléchargez le dernier JAR depuis la page officielle **Aspose.Page for Java download page** [here](https://releases.aspose.com/page/java/).  
- Vous pouvez également parcourir d’autres versions d’Aspose [here](https://releases.aspose.com/).  
- **Accès en écriture** à un dossier où le fichier PostScript généré sera enregistré.

## Importer les packages
Les importations ci‑dessous incluent les classes Java AWT standard pour les primitives graphiques telles que les couleurs, les traits et les formes géométriques, ainsi que les classes Aspose.Page qui fournissent le modèle de document, les définitions de style hachuré et les options d’enregistrement nécessaires pour générer un fichier PostScript.  
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

## Qu’est‑ce que la classe `Document` ?
La classe `Document` est l’objet de niveau supérieur d’Aspose.Page qui représente un fichier PostScript unique en mémoire. Toutes les opérations de dessin sont effectuées via cet objet.

## Comment configurer le flux de sortie ?
Pour écrire la sortie, créez un `FileOutputStream` pointant vers le chemin de fichier souhaité ; ce flux gère l’écriture d’octets de bas niveau. `PsSaveOptions` configure la façon dont le document est enregistré, y compris la taille de la page et la compression. Ensuite, instanciez un `Document` avec un objet `PsSaveOptions` qui spécifie la taille de la page, la compression et d’autres paramètres spécifiques à PostScript.  
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

## Comment enregistrer l’état graphique et translater l’origine ?
Enregistrer l’état graphique capture la matrice de transformation actuelle, la région de découpage et les attributs de dessin, vous permettant de revenir en arrière plus tard. Après l’enregistrement, appelez `translate(x, y)` sur l’objet graphique pour déplacer l’origine vers un emplacement pratique afin de dessiner la grille de carrés hachurés.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Comment créer un carré réutilisable pour chaque motif ?
`Rectangle2D` représente une forme rectangulaire définie par sa position et sa taille. En créant une seule instance correspondant aux dimensions de la cellule, vous pouvez la réutiliser pour chaque carré rempli de hachures, réduisant ainsi l’allocation d’objets et maintenant la boucle de dessin efficace.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Comment configurer un crayon pour le contour du carré de motif ?
`BasicStroke` décrit l’épaisseur du contour, le motif de tirets et les extrémités pour les formes vectorielles. Utiliser un `BasicStroke` de 2 points fournit une bordure nette autour de chaque cellule remplie de hachures, garantissant que le remplissage est visuellement séparé des carrés adjacents.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Comment itérer à travers les motifs hachurés ?
`HatchStyle` est une énumération qui répertorie tous les motifs hachurés prédéfinis tels que diagonal, croisé et pointillé. Parcourir `HatchStyle.values()` vous permet d’appliquer chaque motif à tour de rôle, de remplir le rectangle avec un `HatchBrush`, puis de dessiner son contour.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Comment restaurer l’état graphique après le dessin ?
Appeler `restore()` sur l’objet graphique rétablit la matrice de transformation et les paramètres de dessin à l’état enregistré précédemment, empêchant les translations ou mises à l’échelle cumulatives d’affecter les opérations de dessin suivantes. Cela garantit que le contenu ultérieur commence à partir du système de coordonnées original et utilise les attributs par défaut.  
```java
document.writeGraphicsRestore();
```

## Comment remplir du texte avec un motif hachuré ?
`TextFragment` représente un morceau de texte qui peut être positionné et stylisé indépendamment. En assignant un `HatchBrush` avec un `HatchStyle` choisi au remplissage du fragment, les caractères du texte sont rendus en utilisant la texture hachurée au lieu d’une couleur unie.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Comment tracer le contour du texte avec un style hachuré différent ?
`HatchBrush` peut également être utilisé pour le tracé. Pour dessiner un contour, définissez le trait du fragment sur un `HatchBrush` avec un `HatchStyle` différent (p. ex., hachure à 70 %), et augmentez la largeur du trait via `setStrokeWidth`. Cela rend le bord du texte avec son propre motif hachuré tout en préservant l’intérieur rempli.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Comment fermer et enregistrer le document ?
`document.save()` écrit le document en mémoire dans le flux de sortie spécifié. Après avoir terminé toutes les commandes de dessin, appelez cette méthode puis fermez le `FileOutputStream` pour libérer les ressources système et garantir que le fichier est correctement vidé sur le disque.  
```java
document.closePage();
document.save();
```

Suivez ces étapes, et vous disposerez d’un fichier PostScript qui présente un ensemble complet de motifs hachurés appliqués à la fois aux formes et au texte—le tout propulsé par **aspose page java**.

## Pièges courants & conseils
- **Erreurs de chemin de fichier** – Assurez‑vous que `dataDir` se termine par le séparateur de fichier approprié (`/` ou `\`).  
- **Couleurs non prises en charge** – Certains interprètes PostScript plus anciens peuvent ne pas gérer certains espaces colorimétriques ; restez sur le RGB de base pour une compatibilité maximale.  
- **Avertissements de licence** – Exécuter l’exemple sans licence valide incorporera un filigrane dans la sortie.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page Java avec d’autres frameworks Java ?**  
R : Oui, la bibliothèque est indépendante du framework et fonctionne avec Spring, Jakarta EE, Android (limité) et Java SE standard.

**Q : Une version d’essai est‑elle disponible pour Aspose.Page Java ?**  
R : Absolument. Téléchargez un essai gratuit de 30 jours [Aspose trial download page](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour le développement ?**  
R : Demandez une licence temporaire [temporary license request page](https://purchase.aspose.com/temporary-license/). Elle supprime les filigranes d’évaluation.

**Q : Où puis‑je trouver plus de tutoriels et de support communautaire ?**  
R : Visitez le forum officiel [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pour des exemples supplémentaires et des Q&R.

**Q : Existe‑t‑il une documentation complète pour toutes les classes et méthodes ?**  
R : Oui, la référence complète de l’API est disponible [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q : Puis‑je rendre le même motif hachuré en PDF au lieu de PostScript ?**  
R : Absolument. Changez le `PsSaveOptions` en `PdfSaveOptions` (ou l’équivalent) et le reste du code reste inchangé.

**Q : Que faire si le fichier généré est vide ?**  
R : Vérifiez que le flux de sortie pointe vers un répertoire accessible en écriture et que `document.save()` est appelé après toutes les opérations de dessin.

---

**Dernière mise à jour :** 2026-08-18  
**Testé avec :** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un motif de texture en PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Comment ajouter un dégradé : dégradé diagonal en Java PostScript avec Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Comment convertir PostScript en PDF en utilisant l’API Aspose.Page Java](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}