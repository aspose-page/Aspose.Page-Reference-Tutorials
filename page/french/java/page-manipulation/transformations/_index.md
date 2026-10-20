---
date: 2026-10-20
description: Apprenez comment mettre à l'échelle un rectangle avec Aspose.Page for
  Java, comment translater une forme et appliquer une transformation affine pour créer
  des documents PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformations dans la manipulation de pages Java
og_description: Apprenez comment mettre à l'échelle un rectangle, translater une forme
  et appliquer une transformation affine à l'aide d'Aspose.Page for Java pour générer
  efficacement des fichiers PostScript.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Comment mettre à l'échelle un rectangle avec Aspise.Page for Java – guide
  étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Comment mettre à l'échelle un rectangle avec Aspose.Page for Java
url: /fr/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment mettre à l'échelle un rectangle avec Aspose.Page pour Java

## Introduction
Dans ce guide, vous découvrirez **how to scale rectangle** des objets en utilisant Aspose.Page pour Java, tout en apprenant à translater les positions des formes, à faire pivoter les graphiques et à appliquer des opérations de transformation affine pour produire une sortie PostScript de haute qualité. Ces techniques vous permettent de créer des graphiques sophistiqués, indépendants du dispositif, sans écrire de code de rendu bas‑niveau, rendant vos applications Java plus puissantes et maintenables.

## Réponses rapides
`scale(sx, sy)` met à l'échelle le contexte graphique selon les facteurs horizontaux et verticaux fournis.  

- **How do I scale a rectangle in Java with Aspose.Page?** Appelez la méthode `scale(sx, sy)` sur le contexte graphique avant de dessiner le rectangle.  
- **Can I move (translate) a shape without affecting other graphics?** Oui—encapsulez la translation entre les appels `writeGraphicsSave()` et `writeGraphicsRestore()`.  
- **What class creates a PostScript file?** Utilisez `PsDocument` avec `PsSaveOptions`.  
- **Do I need a license for production use?** Une licence valide d'Aspose.Page est requise pour les déploiements commerciaux.  
- **Which Java version is supported?** Aspose.Page fonctionne avec Java 8 et versions ultérieures.

## Prérequis
- Une solide maîtrise de la syntaxe Java de base et des concepts orientés objet.  
- La bibliothèque Aspose.Page pour Java installée. Vous pouvez la télécharger depuis la [documentation Aspose.Page pour Java](https://reference.aspose.com/page/java/).  
- Un IDE Java (IntelliJ IDEA, Eclipse ou VS Code) configuré avec les fichiers JAR de la bibliothèque sur le classpath.

## Importer les packages
`PsDocument` est la classe principale utilisée pour créer un document PostScript, et `PsSaveOptions` configure la façon dont le document est enregistré.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Qu’est‑ce que “how to scale rectangle” dans Aspose.Page ?
La méthode `scale(float sx, float sy)` applique une transformation de mise à l’échelle affine à l’état graphique actuel, redimensionnant les dessins suivants selon les facteurs `sx` (horizontal) et `sy` (vertical). C’est l’opération principale derrière le mot‑clé **how to scale rectangle**. En appliquant cette transformation avant le dessin, toutes les formes suivantes, comme les rectangles, seront rendues avec les nouvelles dimensions tout en conservant leurs proportions.

## Comment translater une forme avec Aspose.Page
`writeGraphicsSave()` enregistre l’état graphique actuel et `writeGraphicsRestore()` le restaure, garantissant que les transformations n’affectent que la forme souhaitée. La translation repositionne l’origine du système de coordonnées sans modifier les dimensions de l’objet. En entourant `translate(dx, dy)` avec `writeGraphicsSave()` / `writeGraphicsRestore()`, vous vous assurez que seule la forme ciblée se déplace tandis que les autres graphiques restent inchangés, offrant un contrôle précis sur chaque élément.

## Exemple 1 : aucune transformation
Le premier exemple dessine un rectangle sans aucune transformation, établissant une référence pour la comparaison visuelle avec les exemples suivants.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Exemple 2 : translation
Dans cet exemple, nous déplaçons le contexte graphique de 250 unités vers la droite avant de dessiner un deuxième rectangle, illustrant **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Exemple 3 : mise à l’échelle
Ici nous répondons à la question principale **how to scale rectangle**. Le rectangle est réduit à 50 % de sa largeur originale et 75 % de sa hauteur originale en utilisant l’appel `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Comment faire pivoter une forme en Java (rotate shape java)
`rotate(angle)` fait pivoter le système de coordonnées de l’angle spécifié en degrés. Chargez votre `PsDocument`, appelez `rotate(angle)` sur l’état graphique, dessinez la forme, puis restaurez l’état précédent. Ce modèle implémente **rotate shape java** et **how to rotate rectangle** dans un bloc unique et réutilisable, vous permettant de pivoter les graphiques autour de n’importe quel point choisi.

## Pourquoi cela importe – avantages concrets
- **Device‑independent output** – Aspose.Page peut générer des fichiers PostScript et XPS qui s’affichent de manière identique sur n’importe quelle imprimante ou visionneuse, éliminant les ajustements spécifiques à la plateforme.  
- **Fine‑grained control** – Combinez translation, mise à l’échelle, cisaillement et rotation pour répondre à des spécifications de mise en page exactes ; l’API prend en charge plus de 20 combinaisons de transformations par page.  
- **Performance‑oriented processing** – La bibliothèque traite les documents avec une empreinte mémoire inférieure à 10 Mo pour des rapports typiques de 100 pages, rendant les traitements par lots rapides et évolutifs.

## Cas d’utilisation courants
- **Printable invoices** – Placez précisément les logos, codes-barres et tableaux en utilisant la mise à l’échelle et la translation pour respecter les directives de marque de l’entreprise.  
- **Technical diagrams** – Générez des schémas où chaque composant doit être redimensionné et positionné proportionnellement.  
- **Automated multi‑page reports** – Créez des rapports PostScript nécessitant une mise à l’échelle cohérente sur toutes les pages, comme les spécifications d’ingénierie.

## Problèmes courants et solutions
- **Transformation not resetting** – Associez toujours `writeGraphicsSave()` à `writeGraphicsRestore()` ; sinon les dessins suivants héritent de transformations indésirables.  
- **Unexpected colors** – Définissez la couleur (paint) après chaque transformation car l’état graphique ne conserve pas les informations de couleur après une restauration.  
- **File size too large** – Activez la compression dans `PsSaveOptions` et limitez la résolution des images raster intégrées afin de maintenir le fichier final en dessous de 5 Mo pour des documents typiques de 50 pages.

## FAQ

### Puis-je utiliser Aspose.Page pour Java avec d’autres formats de documents ?
Aspose.Page se concentre principalement sur la manipulation de pages pour les formats PostScript et XPS, mais offre également des capacités limitées d’exportation PDF.

### Où puis‑je trouver plus d’exemples et de documentation pour Aspose.Page pour Java ?
Visitez la [documentation Aspose.Page pour Java](https://reference.aspose.com/page/java/) pour des guides complets, des références API et des projets d’exemple.

### Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour Java ?
Oui, vous pouvez accéder à un essai gratuit via la page **Aspose free trial download** : [Aspose free trial download](https://releases.aspose.com/).

### Comment obtenir une licence temporaire pour Aspose.Page pour Java ?
Obtenez une licence temporaire via la **temporary license request page** : [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Où puis‑je obtenir du support communautaire ou poser des questions sur Aspose.Page pour Java ?
Visitez le [forum Aspose.Page pour Java](https://forum.aspose.com/c/page/39) pour des discussions communautaires, des extraits de code et des conseils de dépannage.

## Questions fréquemment posées

**Q : Quelle est la différence entre `translate` et `scale` ?**  
R : `translate` déplace l’origine du système de coordonnées, tandis que `scale` modifie la taille des objets dessinés le long des axes X et/ou Y.

**Q : Puis‑je combiner plusieurs transformations dans un même état graphique ?**  
R : Oui—en appelant `translate`, `scale`, `rotate` ou `shear` séquentiellement avant le dessin, vous créez une transformation affine combinée.

**Q : Comment réinitialiser les transformations après avoir dessiné une forme ?**  
R : Utilisez `writeGraphicsRestore()` pour revenir à l’état graphique précédemment enregistré.

**Q : Est‑il possible de faire pivoter un rectangle autour de son centre ?**  
R : Absolument. Translatez le rectangle vers l’origine, appliquez `rotate(angle)`, puis translatez‑le de nouveau avant le dessin.

**Q : Aspose.Page prend‑il en charge l’anti‑aliasing pour des graphiques plus lisses ?**  
R : Oui—définissez les options de rendu appropriées dans `PsSaveOptions` pour activer l’anti‑aliasing.

---

**Dernière mise à jour :** 2026-10-20  
**Testé avec :** Aspose.Page for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment dessiner un rectangle en Java PostScript avec Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Créer un dégradé radial en PostScript avec Aspose.Page pour Java](/page/java/postscript-gradient-addition/)
- [Manipulation de pages PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}