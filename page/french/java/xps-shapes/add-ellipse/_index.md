---
date: 2026-04-24
description: Apprenez à créer un document XPS en Java avec une ellipse à dégradé radial.
  Ce guide étape par étape montre comment définir l'épaisseur du trait et la géométrie
  du chemin en utilisant Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Ajouter une ellipse en Java XPS
second_title: Aspose.Page Java API
title: Créer un document XPS en Java – Ajouter une ellipse à dégradé radial
url: /fr/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ellipse à dégradé radial avec Aspose.Page

## Introduction
Dans ce tutoriel, vous apprendrez à **create XPS document Java** avec une belle ellipse à contour dégradé radial en utilisant Aspose.Page pour Java. Aspose.Page est une bibliothèque robuste qui abstrait les détails bas‑niveau du XPS, vous permettant de vous concentrer sur la conception plutôt que sur les subtilités du format de fichier. À la fin de ce guide, vous disposerez d’un fichier XPS prêt à l’emploi que vous pourrez intégrer dans des rapports, factures ou tout flux de génération de documents.

## Réponses rapides
- **What does this code produce?** Un fichier XPS d’une seule page contenant une ellipse bordée d’un dégradé radial multicolore.  
- **Which primary API is used?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Do I need a license to run the sample?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise pour la production.  
- **What are the key properties we set?** Pinceau du trait (dégradé radial), méthode de diffusion, arrêts du dégradé et épaisseur du trait.  
- **Can I change the ellipse size?** Oui – modifiez la chaîne de géométrie du chemin ou les coordonnées du pinceau de dégradé.

## Qu’est‑ce que « create XPS document Java » ?
Créer un document XPS en Java signifie générer de façon programmatique un fichier XML Paper Specification (XPS) — un format de document à mise en page fixe similaire au PDF — directement à partir du code Java. Aspose.Page fournit un modèle d’objets de haut niveau (`XpsDocument`, `XpsCanvas`, etc.) qui abstrait le balisage XML, rendant le processus aussi simple que de travailler avec des objets Java standards.

## Pourquoi utiliser une ellipse à dégradé radial ?
Un dégradé radial confère une impression tridimensionnelle, idéal pour les mises en évidence visuelles, les logos ou les éléments décoratifs dans les rapports. Comparé à un trait de couleur unie, le dégradé ajoute de la profondeur sans augmenter significativement la taille du fichier, et le format XPS préserve la qualité vectorielle quel que soit le redimensionnement.

## Prérequis
Avant de commencer, assurez‑vous que les prérequis suivants sont en place :
- Java Development Kit (JDK) installé sur votre machine.
- Bibliothèque Aspose.Page pour Java téléchargée. Vous pouvez l’obtenir [ici](https://releases.aspose.com/page/java/).
- Un éditeur de code de votre choix (Eclipse, IntelliJ, etc.) pour écrire et exécuter du code Java.

## Importer les packages
Assurez‑vous d’avoir les packages nécessaires importés dans votre projet Java pour utiliser Aspose.Page. Ajoutez les déclarations d’importation suivantes en haut de votre fichier Java :

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Étape 1 : Configurer le répertoire du document
Définissez le chemin vers le répertoire de votre document où le fichier XPS sera enregistré :

```java
String dataDir = "Your Document Directory";
```

## Étape 2 : Créer le document XPS
Initialisez un nouveau document XPS en utilisant le code suivant :

```java
XpsDocument doc = new XpsDocument();
```

## Étape 3 : Définir les arrêts du dégradé radial
Créez une liste d’arrêts de dégradé pour l’ellipse à contour dégradé radial :

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Étape 4 : Créer la géométrie du chemin
Définissez une ellipse à contour dégradé radial en utilisant la géométrie du chemin :

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Étape 5 : Ajouter le canevas et le chemin
Ajoutez un nouveau canevas au document et ajoutez le chemin avec la géométrie définie :

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Étape 6 : Définir le trait et le dégradé
Configurez le trait du chemin avec un pinceau de dégradé radial :

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Étape 7 : Définir l’épaisseur du trait
Spécifiez l’**épaisseur du trait** du chemin :

```java
path.setStrokeThickness(12f);
```

## Étape 8 : Enregistrer le document
Enregistrez le document XPS résultant :

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Félicitations ! Vous avez ajouté avec succès une ellipse à contour dégradé radial tout en **creating an XPS document Java** avec Aspose.Page.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **L’ellipse apparaît plate** | Utilisation de `XpsSpreadMethod.Pad` au lieu de `Reflect` | Modifiez la méthode de diffusion en `XpsSpreadMethod.Reflect` comme indiqué à l’étape 6. |
| **Aucun fichier de sortie** | `dataDir` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou utilisez un chemin absolu. |
| **Les couleurs du dégradé sont incorrectes** | Ordre incorrect des arrêts du dégradé | Vérifiez que les valeurs `offset` (0 → 1) augmentent de façon monotone. |
| **Erreurs de compilation** | JARs Aspose.Page manquants dans le classpath | Ajoutez `aspose-page-xx.jar` aux dépendances de votre projet. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Page pour Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Page pour Java peut être intégré de manière transparente avec d’autres bibliothèques Java.

**Q : Aspose.Page convient‑il au traitement de documents à grande échelle ?**  
R : Absolument ! Aspose.Page est conçu pour gérer efficacement le traitement de documents à grande échelle.

**Q : Où puis‑je trouver plus de tutoriels et d’exemples pour Aspose.Page pour Java ?**  
R : Consultez la [documentation Aspose.Page pour Java](https://reference.aspose.com/page/java/) pour des tutoriels et exemples complets.

**Q : Comment obtenir une licence temporaire pour Aspose.Page pour Java ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Existe‑t‑il des forums communautaires pour les discussions sur Aspose.Page ?**  
R : Oui, rejoignez le [forum communautaire Aspose.Page](https://forum.aspose.com/c/page/39) pour échanger avec d’autres développeurs et obtenir de l’aide.

**Dernière mise à jour :** 2026-04-24  
**Testé avec :** Aspose.Page pour Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}