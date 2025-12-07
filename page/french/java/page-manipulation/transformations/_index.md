---
date: 2025-12-07
description: Apprenez à mettre à l’échelle un rectangle, à translater une forme et
  à appliquer une transformation affine en Java avec Aspose.Page pour créer des documents
  PostScript.
language: fr
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Comment mettre à l’échelle un rectangle et appliquer des transformations avec
  Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment mettre à l’échelle un rectangle et appliquer des transformations avec Aspose.Page

## Introduction
Bienvenue dans ce guide complet sur l’utilisation des puissantes fonctionnalités d’**Aspose.Page for Java** pour effectuer une variété de transformations de page. Dans ce tutoriel, vous apprendrez **comment mettre à l’échelle un rectangle**, déplacer des formes, faire pivoter des objets et **appliquer des transformations affines** tout en créant un **document PostScript**. Ces capacités vous permettent de créer des applications Java riches en graphiques sans gérer du code de rendu bas‑niveau.

## Quick Answers
- **Comment mettre à l’échelle un rectangle en Java avec Aspose.Page ?** Utilisez la méthode `document.scale()` avant de dessiner la forme.  
- **Puis‑je déplacer (traduire) une forme sans affecter les autres graphiques ?** Oui — enregistrez l’état graphique, appelez `document.translate(x, y)`, dessinez, puis restaurez l’état.  
- **Quelle classe crée un fichier PostScript ?** `PsDocument` avec `PsSaveOptions`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence valide d’Aspose.Page est requise pour les déploiements commerciaux.  
- **Quelle version de Java est prise en charge ?** Aspose.Page fonctionne avec Java 8 et les versions ultérieures.

## Prérequis
Avant de plonger dans le guide étape par étape, assurez‑vous d’avoir les prérequis suivants :

- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger depuis la [documentation Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un environnement de développement intégré (IDE) Java installé sur votre machine.

## Import Packages
Dans votre projet Java, importez les packages nécessaires pour exploiter Aspose.Page for Java :

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Qu’est‑ce que « how to scale rectangle » dans Aspose.Page ?
Mettre à l’échelle un rectangle modifie sa taille le long des axes X et Y tout en conservant sa forme. Aspose.Page expose la méthode `scale(float sx, float sy)`, qui applique une **affine transform** à l’état graphique actuel. C’est la technique centrale derrière le mot‑clé **how to scale rectangle**.

## Comment déplacer une forme avec Aspose.Page
Le déplacement (translation) déplace une forme vers une nouvelle position sans en altérer les dimensions. C’est l’essence de **how to translate shape**. En enregistrant l’état graphique, en appliquant `translate(dx, dy)`, en dessinant, puis en restaurant l’état, vous gardez les autres objets intacts.

## Example 1 : No Transformations
Le premier exemple dessine un simple rectangle sans aucune transformation appliquée. Cela sert de référence pour la comparaison avec les exemples suivants.

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

## Example 2 : Translation
Ici nous démontrons **how to translate shape** en déplaçant le contexte graphique de 250 unités vers la droite avant de dessiner un deuxième rectangle.

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

## Example 3 : Scaling
Cet exemple répond à la question principale **how to scale rectangle**. Nous réduisons le rectangle à 50 % de sa largeur originale et à 75 % de sa hauteur.

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

## How to Rotate Shape Java (rotate shape java)
La rotation est une autre opération affine courante. Bien que les extraits de code pour la rotation soient omis pour plus de concision, le schéma est identique : enregistrez l’état graphique, appelez `document.rotate(angle)`, dessinez la forme, puis restaurez. Cela illustre **rotate shape java** et **how to rotate rectangle** en pratique.

## Pourquoi utiliser Aspose.Page pour ces transformations ?
- **Device‑independent** : écrivez une fois, générez du PostScript ou XPS sans code spécifique à la plateforme.  
- **Fine‑grained control** : l’accès direct à l’état graphique vous permet de combiner translation, mise à l’échelle, cisaillement et rotation.  
- **Performance** : API à faible surcharge adaptée au traitement par lots de documents volumineux.  

## Cas d’utilisation courants
- Génération de factures imprimables avec codes‑barres et logos dynamiques.  
- Création de schémas techniques où un dimensionnement et un positionnement précis sont requis.  
- Automatisation de la production de rapports multi‑pages au format PostScript.

## Conclusion
Dans ce tutoriel, nous avons exploré diverses transformations en manipulation de pages Java avec Aspose.Page for Java, en nous concentrant sur **how to scale rectangle**, **how to translate shape** et d’autres opérations affines. En suivant ces exemples, vous pouvez enrichir vos applications Java avec des capacités avancées de manipulation de pages et **créer des documents PostScript** répondant aux normes professionnelles d’édition.

## FAQ
### Puis‑je utiliser Aspose.Page for Java pour d’autres formats de documents ?
Aspose.Page se concentre principalement sur la manipulation de pages pour les formats PostScript et XPS.

### Où puis‑je trouver plus d’exemples et de documentation pour Aspose.Page for Java ?
Visitez la [documentation Aspose.Page for Java](https://reference.aspose.com/page/java/) pour des informations complètes.

### Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?
Oui, vous pouvez accéder à un essai gratuit [ici](https://releases.aspose.com/).

### Comment obtenir une licence temporaire pour Aspose.Page for Java ?
Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Où puis‑je obtenir du support communautaire ou poser des questions sur Aspose.Page for Java ?
Visitez le [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) pour les discussions communautaires.

## Frequently Asked Questions

**Q : Quelle est la différence entre `translate` et `scale` ?**  
R : `translate` déplace l’origine du système de coordonnées, tandis que `scale` modifie la taille des objets dessinés le long des axes X et/ou Y.

**Q : Puis‑je combiner plusieurs transformations dans un même état graphique ?**  
R : Oui—en appelant `translate`, `scale`, `rotate` ou `shear` séquentiellement avant le dessin, vous créez une transformation affine combinée.

**Q : Comment réinitialiser les transformations après avoir dessiné une forme ?**  
R : Utilisez `document.writeGraphicsRestore()` pour revenir à l’état graphique précédemment enregistré.

**Q : Est‑il possible de faire pivoter un rectangle autour de son centre ?**  
R : Absolument. Translatez le rectangle vers l’origine, appliquez `rotate(angle)`, puis translatez‑le de nouveau avant le dessin.

**Q : Aspose.Page prend‑il en charge l’anti‑aliasing pour des graphiques plus lisses ?**  
R : Oui—définissez les options de rendu appropriées dans `PsSaveOptions` pour activer l’anti‑aliasing.

---

**Dernière mise à jour :** 2025-12-07  
**Testé avec :** Aspose.Page for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}