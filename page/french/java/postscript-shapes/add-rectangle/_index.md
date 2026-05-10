---
date: 2026-02-18
description: Apprenez à dessiner des formes rectangulaires en Java PostScript avec
  Aspose.Page. Ce guide étape par étape montre comment définir la peinture, définir
  la couleur du rectangle en Java, et créer des graphiques éclatants tout en expliquant
  comment dessiner un rectangle efficacement.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Comment dessiner un rectangle en Java PostScript avec Aspose.Page
url: /fr/java/postscript-shapes/add-rectangle/
weight: 11
---

 keep all shortcodes exactly as original.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment dessiner un rectangle en Java PostScript avec Aspose.Page

## Introduction
Si vous avez besoin de **how to draw rectangle** formes à l'intérieur d'un fichier Java PostScript, vous êtes au bon endroit. Dans ce tutoriel, nous allons parcourir l'utilisation d'Aspose.Page pour Java afin d'ajouter des rectangles colorés, de contrôler leur remplissage et leur contour, et d'enregistrer le résultat sous forme de document PostScript. Vous verrez exactement **how to set paint**, comment définir la géométrie du rectangle, et pourquoi cette approche est idéale pour générer des graphiques imprimables de manière programmatique. À la fin du guide, vous comprendrez également le contexte plus large des techniques **draw rectangle java** et comment elles s'intègrent aux flux de travail **java awt rectangle drawing**.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis-je changer les couleurs du rectangle ?** Oui – utilisez `setPaint` avec n'importe quel `java.awt.Color`  
- **Ai-je besoin d'une licence pour le développement ?** Une version d'essai gratuite fonctionne pour les tests ; une licence est requise pour la production  
- **Quelle taille de page est utilisée dans l'exemple ?** A4 (par défaut `PsSaveOptions`)  
- **Le code est-il compatible avec Java 8+ ?** Absolument – il utilise les classes standard AWT  

## Qu’est‑ce que “How to Draw Rectangle” en PostScript ?
Dessiner un rectangle dans un document PostScript signifie définir une région rectangulaire et soit la remplir, soit tracer son contour, ou les deux. Avec Aspose.Page, vous pouvez le faire en utilisant les classes familières de **java awt rectangle drawing**, ce qui rend le code facile à lire et à maintenir.

## Pourquoi utiliser Aspose.Page pour les graphiques de rectangles ?
- **Cross‑platform** : Génère du PostScript standard qui fonctionne sur n'importe quelle imprimante.  
- **Fine‑grained control** : Vous pouvez définir les couleurs de remplissage, les couleurs de contour et les épaisseurs de ligne de façon indépendante.  
- **No external dependencies** : Utilise uniquement les classes de géométrie AWT intégrées, vous n'avez donc pas besoin de bibliothèques graphiques supplémentaires.  

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d'avoir les prérequis suivants en place :
- Compréhension de base de la programmation Java.  
- Bibliothèque Aspose.Page pour Java installée. Sinon, téléchargez‑la depuis la [documentation Aspose.Page pour Java](https://reference.aspose.com/page/java/).  
- Un environnement de développement Java configuré sur votre machine.

## Importer les packages
Dans votre projet Java, commencez par importer les packages nécessaires. Ces imports vous donnent accès aux classes `Color`, `BasicStroke` et `Rectangle2D` d'AWT, ainsi qu'aux classes de gestion de documents du cœur d'Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guide étape par étape pour dessiner un rectangle en Java PostScript

### Étape 1 : Définir la peinture pour remplir le rectangle  
**How to set paint** – nous choisissons une couleur de remplissage orange pour le premier rectangle. Cela montre la capacité **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Étape 2 : Définir la peinture pour le contour du rectangle  
**Set rectangle color java** – maintenant nous changeons la peinture en rouge et définissons une épaisseur de contour. Cette partie de l'exemple montre comment **draw rectangle java** avec une épaisseur de ligne personnalisée.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Étape 3 : Fermer la page actuelle et enregistrer le document  
Après le dessin, nous fermons la page et persistons le fichier. Fermer la page garantit que toutes les commandes de dessin sont vidées dans le flux PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Cas d’utilisation courants pour le dessin de rectangles
- **Génération de factures ou de reçus** – les rectangles servent de bordures ou mettent en évidence des sections.  
- **Création d'étiquettes** – dessinez des boîtes colorées pour séparer les informations produit.  
- **Graphiques simples** – utilisez des rectangles remplis comme éléments de diagrammes à barres.  
- **Formulaires imprimables personnalisés** – combinez des rectangles avec du texte pour créer des champs de formulaire.  

## Problèmes courants et astuces
- **Erreurs de chemin de fichier** – assurez‑vous que `dataDir` se termine par un séparateur de fichier (`/` ou `\\`).  
- **Exceptions de licence** – la version d'essai ajoute un filigrane ; obtenez une licence complète pour une utilisation en production.  
- **Visibilité des couleurs** – certaines imprimantes peuvent interpréter différemment certaines valeurs RVB ; testez d'abord avec un simple rectangle noir.  
- **Utilisation de la mémoire** – pour les gros documents, envisagez de vider le flux après chaque page (`document.closePage()`).  

## Questions fréquemment posées

**Q :** *Puis-je utiliser Aspose.Page pour Java avec d'autres langages de programmation ?*  
**R :** Aspose.Page prend principalement en charge Java, mais des bibliothèques similaires sont disponibles pour d'autres langages.

**Q :** *Existe‑t‑il une version d'essai d'Aspose.Page pour Java disponible ?*  
**R :** Oui, vous pouvez explorer les fonctionnalités d'Aspose.Page pour Java avec la [version d'essai gratuite](https://releases.aspose.com/).

**Q :** *Où puis‑je trouver de l'aide supplémentaire et des discussions ?*  
**R :** Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour interagir avec la communauté et obtenir de l'aide.

**Q :** *Comment obtenir une licence temporaire pour Aspose.Page pour Java ?*  
**R :** Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q :** *Où puis‑je acheter une version sous licence d'Aspose.Page pour Java ?*  
**R :** Achetez une version sous licence [ici](https://purchase.aspose.com/buy).

### Q&A supplémentaires

**Q :** *Puis‑je changer la taille du rectangle dynamiquement ?*  
**R :** Oui – modifiez simplement les paramètres `Rectangle2D.Float(x, y, width, height)` avant d'appeler `fill` ou `draw`.

**Q :** *Est‑il possible d'ajouter du texte à l'intérieur du rectangle ?*  
**R :** Absolument. Après avoir dessiné le rectangle, utilisez `document.drawString(...)` avec la police et la position souhaitées.

**Q :** *Aspose.Page prend‑il en charge d'autres formes comme des cercles ou des polygones ?*  
**R :** Oui, l'API fournit des méthodes telles que `drawEllipse` et `drawPolygon` pour une variété de graphiques vectoriels.

## Conclusion
Dans ce guide, nous avons démontré comment **how to draw rectangle** des formes dans un document Java PostScript, couvert **how to set paint**, et montré comment **set rectangle color java** en utilisant Aspose.Page. Vous disposez désormais d'une base solide pour créer des graphiques imprimables vibrants, que vous construisiez des factures, des étiquettes ou des formulaires personnalisés. N'hésitez pas à expérimenter avec différentes couleurs, styles de ligne et formes AWT supplémentaires pour enrichir votre sortie.

---

**Dernière mise à jour :** 2026-02-18  
**Testé avec :** Aspose.Page for Java 24.12 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}