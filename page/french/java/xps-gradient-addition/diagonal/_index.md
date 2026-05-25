---
date: 2026-05-25
description: Apprenez comment ajouter un dégradé aux documents XPS en Java en utilisant
  Aspose.Page. Ce guide étape par étape montre comment ajouter un dégradé diagonal,
  appliquer des pinceaux de dégradé linéaire et produire des fichiers XPS professionnels.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Ajouter un dégradé diagonal en Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Comment ajouter un dégradé : dégradé diagonal en Java XPS'
url: /fr/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé : dégradé diagonal dans Java XPS

## Introduction
Dans le développement Java moderne, maîtriser **how to add gradient** aux documents XPS donne à vos rapports un aspect soigné et accrocheur qui se démarque. Ce tutoriel vous guide pas à pas pour créer un fichier XPS à partir de zéro, ajouter un dégradé diagonal et enregistrer le résultat — le tout avec Aspose.Page pour Java. Vous comprendrez pourquoi les dégradés sont importants, verrez les appels d’API exacts et obtiendrez des conseils pratiques pour éviter les pièges courants.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Page for Java  
- **Quelle méthode ajoute le dégradé ?** `createLinearGradientBrush` with gradient stops  
- **Ai‑je besoin d’une licence ?** Une version d’essai fonctionne pour le développement ; une licence commerciale est requise pour la production  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un dégradé diagonal de base  
- **Puis‑je l’utiliser avec d’autres frameworks Java ?** Oui, l’API est indépendante du framework  

## Qu’est‑ce qu’un dégradé diagonal dans un document XPS ?
Un dégradé diagonal est une transition de couleur fluide qui s’étend d’un coin d’une forme au coin opposé, créant un effet visuel incliné. Dans XPS, cet effet est défini par une brosse de dégradé linéaire contenant des arrêts de dégradé ordonnés qui spécifient les couleurs et les positions relatives le long de la ligne diagonale.

## Pourquoi ajouter un dégradé diagonal avec Aspose.Page ?
Aspose.Page offre **100 % de fidélité de rendu** pour les dégradés sur plus de 20 visionneuses XPS, et il prend en charge **plus de 30 fonctionnalités XPS** telles que le texte, les images et les formes vectorielles. L’API abstrait le balisage XPS complexe, vous permettant de vous concentrer sur la conception tout en garantissant que le même fichier apparaît identiquement sous Windows, macOS et Linux.

## Prérequis
- Connaissances de base en programmation Java.  
- JDK installé sur votre machine.  
- Bibliothèque Aspose.Page pour Java – téléchargez‑la **[ici](https://releases.aspose.com/page/java/)**.  
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.

## Importer les packages
Commencez par importer les classes dont vous avez besoin. Ces importations vous donnent accès à la géométrie, à la gestion des dégradés et à la création de documents XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Étape 1 : Configurer votre projet
Créez un nouveau projet Java dans votre IDE préféré et ajoutez les fichiers JAR d’Aspose.Page au chemin de construction du projet.

## Étape 2 : Définir le répertoire du document
Spécifiez l’endroit où le fichier XPS généré sera enregistré.

```java
String dataDir = "Your Document Directory";
```

## Étape 3 : Créer le document XPS
`XpsDocument` est l’objet principal qui représente un fichier XPS en mémoire. L’instancier vous fournit une toile pour ajouter des pages, des formes et des brosses.

```java
XpsDocument doc = new XpsDocument();
```

## Étape 4 : Ajouter le chemin du dégradé diagonal
Créez un chemin rectangulaire qui recevra le dégradé. La géométrie du chemin utilise une simple commande move‑line‑close.  
XpsPath définit une forme vectorielle dans le document XPS, comme un rectangle ou une géométrie personnalisée.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Étape 5 : Définir les arrêts du dégradé linéaire
Configurez les couleurs et leurs positions. Chaque arrêt définit un point dans le dégradé où une couleur spécifique apparaît.  
XpsGradientStop représente un arrêt de couleur unique dans un dégradé, spécifiant une couleur et son décalage.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Étape 6 : Appliquer le dégradé linéaire au chemin
`XpsLinearGradientBrush` est le type de brosse d’Aspose.Page pour les transitions de couleur linéaires. Il prend deux points qui définissent la direction du dégradé ainsi qu’une collection d’arrêts de dégradé qui déterminent les couleurs le long de cette ligne.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Étape 7 : Enregistrer le document
Enregistrez le fichier XPS sur le disque. Le fichier contiendra le rectangle rempli du dégradé diagonal que vous avez défini.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Comment ajouter un dégradé dans Java XPS ?
Chargez le XpsDocument, créez un `XpsLinearGradientBrush` avec le point de départ `(0,0)` et le point d’arrivée `(width,height)`, ajoutez les arrêts de dégradé, assignez la brosse à la propriété `Fill` d’une forme, puis appelez `save`. Ce flux concis vous permet d’intégrer un dégradé diagonal en quelques appels d’API seulement, en gardant votre code propre et maintenable.

## Pièges courants et astuces
- **Direction du dégradé** – assurez‑vous que les points de départ et d’arrivée de la brosse reflètent la diagonale souhaitée ; les inverser renverse le dégradé.  
- **Précision des couleurs** – Aspose utilise ARGB ; incluez le canal alpha si vous avez besoin de transparence.  
- **Chemin du fichier** – utilisez toujours un chemin absolu ou vérifiez que le chemin relatif pointe vers un répertoire existant et accessible en écriture.

## FAQ supplémentaires

**Q : Comment **how to add gradient** à une forme XPS existante ?**  
A : Créez un `XpsLinearGradientBrush`, définissez les arrêts de dégradé et assignez-le à la propriété `Fill` de la forme comme indiqué à l’étape 6.

**Q : Que fait réellement **apply linear gradient** en arrière‑plan ?**  
A : Il génère une définition de brosse dans le package XPS qui référence les points de départ/arrivée et une collection d’arrêts de dégradé, que le visualiseur rend comme une transition de couleur fluide.

**Q : Existe‑t‑il un moyen rapide de **how to use aspose** pour d’autres fonctionnalités XPS ?**  
A : Oui, l’API Aspose.Page comprend des méthodes pour ajouter des images, du texte et des formes personnalisées — explorez simplement la classe `XpsDocument` pour d’autres assistants.

**Q : Puis‑je **add gradient path** à des formes non rectangulaires ?**  
A : Absolument. Définissez n’importe quelle géométrie avec `createPathGeometry` puis affectez son `Fill` à une brosse de dégradé.

**Q : Le dégradé affecte‑t‑il significativement la taille du fichier ?**  
A : Seulement marginalement ; les définitions de dégradé sont des entrées XML légères dans le package XPS.

---

**Dernière mise à jour :** 2026-05-25  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Ajout de dégradé XPS Aspose Page](/page/java/xps-gradient-addition/)
- [Ajout de texte XPS Java - Tutoriel Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Comment ajouter une image aux documents Java XPS – Guide simple avec Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}