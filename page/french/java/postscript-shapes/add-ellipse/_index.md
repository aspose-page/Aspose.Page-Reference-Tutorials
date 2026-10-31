---
date: 2026-10-31
description: Apprenez à définir la couleur de peinture et à remplir une ellipse dans
  Java PostScript en utilisant Aspose.Page. Ce guide montre comment remplir une ellipse,
  tracer le contour de l'ellipse et définir l'épaisseur du trait avec des étapes de
  code claires.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Ajouter une ellipse dans Java PostScript
og_description: Apprenez à remplir une ellipse et à définir la couleur de peinture
  dans Java PostScript en utilisant Aspose.Page. Suivez un code étape par étape pour
  dessiner des ellipses remplies et contournées en quelques secondes.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Comment remplir une ellipse et définir la couleur de peinture dans Java
  PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Comment remplir une ellipse et définir la couleur de peinture dans Java PostScript
url: /fr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment remplir une ellipse et définir la couleur de peinture en Java PostScript

## Introduction
Si vous devez **définir la couleur de peinture** lors du dessin de graphiques vectoriels, la bibliothèque Aspose.Page for Java vous offre un contrôle complet sur chaque trait et remplissage. Dans ce tutoriel, vous découvrirez comment **définir la couleur de peinture**, **remplir une ellipse** et **dessiner le contour d’une ellipse** grâce à une approche simple, étape par étape. À la fin, vous pourrez ajouter des ellipses PostScript de haute qualité à des factures, rapports ou tout document imprimable.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour dessiner des graphiques PostScript en Java ?** Aspose.Page for Java.  
- **Puis-je remplir une ellipse avec une couleur unie ?** Oui – utilisez `document.setPaint(Color.YOUR_COLOR)` avant `fill`.  
- **Comment dessiner uniquement le contour d’une ellipse ?** Définissez la couleur et le trait, puis appelez `document.draw(...)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise ; une licence temporaire est disponible pour les tests.  
- **Quelle version de Java est prise en charge ?** Tout environnement d’exécution Java 8+ fonctionne avec la version actuelle d’Aspose.Page.

## Qu’est‑ce qu’une ellipse PostScript ?
Une ellipse PostScript est une forme vectorielle définie par un rectangle englobant. Contrairement aux images raster, elle s’agrandit sans perte de qualité, ce qui la rend idéale pour l’impression haute résolution et la conversion PDF. Comme la forme est décrite mathématiquement, elle peut être rendue à n’importe quelle taille ou résolution tout en conservant des bords nets et des courbes lisses.

## Pourquoi utiliser Aspose.Page pour créer une ellipse PostScript ?
Aspose.Page vous offre un contrôle déterministe sur chaque primitive de dessin. Elle prend en charge **3 systèmes d’exploitation majeurs (Windows, Linux, macOS)**, **0 dépendance native**, et peut rendre **plus de 50 primitives vectorielles** par seconde sur un serveur typique. La bibliothèque est pure Java, vous pouvez donc l’intégrer dans n’importe quelle application Java 8+ sans bibliothèques natives supplémentaires.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. Un environnement de développement Java fonctionnel (JDK 8 ou supérieur).  
2. La bibliothèque Aspose.Page for Java ajoutée à votre projet. Vous pouvez la télécharger **[à partir de la page de version Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## Importer les packages
Dans votre fichier source Java, importez les classes nécessaires au dessin et à l’enregistrement du contenu PostScript.

Le package `java.awt` fournit les types graphiques de base tels que `Color`, `Ellipse2D` et `BasicStroke`. Le package `com.aspose.page` fournit la classe `PsDocument` qui écrit la sortie PostScript.

- **`Color`** – représente une couleur sRGB utilisée pour la peinture.  
- **`Ellipse2D`** – décrit une forme d’ellipse définie par un rectangle englobant.  
- **`BasicStroke`** – spécifie la largeur de ligne, le motif de tirets et le style d’extrémité pour le dessin des contours.  
- **`PsDocument`** – représente un document PostScript et fournit des méthodes pour dessiner des graphiques et gérer les pages.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Comment définir la couleur de peinture pour une ellipse
La première étape consiste à indiquer au document quelle couleur utiliser pour l’opération de dessin suivante. La méthode `setPaint` définit une couleur unie qui sera appliquée soit à un remplissage, soit à un trait, selon l’appel suivant.

### Étape 1 : Configurer le document PostScript
Créez un flux de sortie, configurez la taille de la page et instanciez un `PsDocument`.

`PsDocument` est la classe principale qui représente un fichier PostScript en mémoire. Toutes les commandes de dessin sont acheminées via cet objet, qui gère la mise en page, la gestion des ressources et la génération finale du fichier.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 2 : Remplir l’ellipse – utiliser set paint color
Pour **remplir une ellipse**, vous devez d’abord appeler `setPaint` avec la couleur de remplissage souhaitée, puis invoquer `fill` avec une instance `Ellipse2D`.

`setPaint` définit la couleur de dessin actuelle utilisée pour les opérations de remplissage ou de trait suivantes.  
`Ellipse2D` définit les limites géométriques de l’ellipse ; son constructeur prend les coordonnées X‑Y du coin supérieur gauche ainsi que la largeur et la hauteur.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Étape 3 : Dessiner le contour de l’ellipse et définir l’épaisseur du trait
Après le remplissage, vous pouvez changer la couleur de peinture, définir un `BasicStroke` pour contrôler la largeur de ligne, puis dessiner le contour de l’ellipse.

`BasicStroke` spécifie la largeur de ligne, le motif de tirets et le style d’extrémité pour le dessin des contours. En ajustant sa propriété `width`, vous contrôlez l’épaisseur du bord de l’ellipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Étape 4 : Fermer et enregistrer le document
Finalisez la page et écrivez le fichier PostScript sur le disque.

L’appel à `document.close()` vide toutes les commandes de dessin en attente et libère les ressources. Le fichier `.ps` résultant peut être ouvert avec n’importe quel visualiseur PostScript ou converti en PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Vous avez maintenant un fichier PostScript contenant deux ellipses — une remplie d’orange et une autre tracée en rouge. N’hésitez pas à expérimenter avec différentes coordonnées, tailles et couleurs pour répondre à vos besoins de conception.

## Pièges courants et dépannage
- **Chemin de fichier incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur (`/` ou `\\`) adapté à votre OS.  
- **Licence manquante** – Sans licence valide, la bibliothèque fonctionne en mode d’évaluation et peut ajouter des filigranes.  
- **Couleur non appliquée** – N’oubliez pas d’appeler `document.setPaint(...)` *avant* chaque appel `fill` ou `draw` ; le paramètre de peinture ne persiste pas automatiquement entre les opérations séparées.

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçue pour s’intégrer de façon transparente avec d’autres bibliothèques Java.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Obtenez une licence temporaire **[à partir de la page de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/)** à des fins de test.

**Q : Aspose.Page convient‑elle aux projets commerciaux ?**  
R : Absolument ! Consultez **[la page d’achat Aspose](https://purchase.aspose.com/buy)** pour explorer les options de licence commerciale.

**Q : Où puis‑je obtenir de l’aide ou discuter des questions liées à Aspose.Page ?**  
R : Rejoignez la communauté sur le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour des discussions et de l’assistance.

**Q : Existe‑t‑il des ressources gratuites pour en savoir plus sur Aspose.Page for Java ?**  
R : Utilisez la **[page d’essai gratuit Aspose](https://releases.aspose.com/)** et explorez les exemples dans la documentation.

## Conclusion
Aspose.Page for Java simplifie la **définition de la couleur de peinture**, le **remplissage d’une ellipse** et le **dessin du contour d’une ellipse**—que vous ayez besoin d’une forme remplie simple ou d’un graphique tracé complexe. Avec les étapes ci‑dessus, vous pouvez rapidement ajouter des graphiques vectoriels de qualité professionnelle à tout document imprimable. Pour aller plus loin—comme combiner plusieurs formes, appliquer des dégradés ou convertir en PDF—référez‑vous à la documentation officielle **[Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Dernière mise à jour :** 2026-10-31  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Comment dessiner un rectangle en Java PostScript avec Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Comment ajouter du texte Unicode en Java PostScript avec Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Créer un dégradé radial en PostScript avec Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}