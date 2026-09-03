---
date: 2026-05-30
description: Apprenez à créer un document XPS en Java en utilisant Aspose.Page et
  à ajouter une image en mosaïque sans effort grâce à ce guide étape par étape. Comment
  créer rapidement des fichiers XPS.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Ajouter une image en mosaïque dans XPS Java
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Comment créer un document XPS avec une image en mosaïque en Java
url: /fr/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un document XPS avec une image en mosaïque en Java

## Introduction
Créer des documents XPS de façon programmatique est une compétence essentielle pour les développeurs Java qui ont besoin d’une sortie imprimable, indépendante du dispositif. **Comment créer XPS** efficacement est résolu par Aspose.Page for Java, qui abstrait les détails bas‑niveau de la XML Paper Specification et vous permet de vous concentrer sur la conception visuelle. Dans ce guide, vous verrez exactement comment créer un document XPS, ajouter une image en mosaïque comme arrière‑plan ou motif, et enregistrer le résultat — le tout avec du code concis, prêt pour la production.

## Réponses rapides
- **Que fait Aspose.Page ?** Il fournit une API de haut niveau pour générer et manipuler des documents XPS en Java.  
- **Puis-je répéter une image en mosaïque ?** Oui – utilisez `XpsImageBrush` avec `XpsTileMode.Tile`.  
- **Ai-je besoin d’une licence ?** Une licence temporaire ou commerciale est requise pour une utilisation en production.  
- **Quelle version de Java est prise en charge ?** Tout JDK 8+ est compatible.  
- **Combien de temps prend l’implémentation ?** Environ 10–15 minutes pour un scénario d’image en mosaïque basique.

## Qu’est‑ce que « créer un document XPS » ?
`XpsDocument` est l’objet de niveau supérieur d’Aspose.Page qui représente un fichier XPS unique en mémoire. Il encapsule les pages, les ressources et les métadonnées, vous permettant de construire le document de façon programmatique. Créer un document XPS signifie instancier cette classe, ajouter des éléments visuels, puis appeler `save` pour écrire le fichier à mise en page fixe sur le disque. Cette approche élimine la manipulation manuelle du XML et garantit la conformité à la XML Paper Specification.

## Pourquoi ajouter une image en mosaïque ?
La mosaïque répète un graphique sur une zone définie, ce qui est idéal pour les arrière‑plans, filigranes ou remplissages de motifs. En utilisant `XpsTileMode.Tile`, l’image se répète automatiquement sans duplication manuelle, économisant du temps de développement et assurant un rendu cohérent sur tout dispositif. Les images en mosaïque maintiennent également la taille du fichier basse car la même ressource bitmap est réutilisée plutôt qu’incorporée plusieurs fois.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – JDK 8 ou plus récent installé.  
2. **Aspose.Page for Java** – téléchargez depuis le [site web](https://releases.aspose.com/page/java/).  
3. **Un répertoire accessible en écriture** – où le fichier XPS généré sera enregistré.

## Import Packages
Dans votre projet Java, importez les classes nécessaires :

`XpsDocument` est l’objet principal représentant un fichier XPS.  
`XpsImageBrush` peint les formes en utilisant une source d’image.  
`XpsTileMode` spécifie comment une image est répétée en mosaïque.  
`Rectangle2D` décrit une région rectangulaire pour le positionnement.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guide étape par étape

### Étape 1 : Configurer votre projet
Ajoutez les fichiers JAR d’Aspose.Page au classpath de votre projet et vérifiez que les déclarations d’importation se compilent sans erreurs.

### Étape 2 : Créer le document XPS
`XpsDocument` est le conteneur principal qui contient les pages, chemins et ressources. Instanciez‑le avec la taille de page souhaitée, puis vous pouvez commencer à ajouter des éléments graphiques.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Étape 3 : Définir le chemin de l’image en mosaïque
Placez l’image que vous souhaitez répéter (par ex., `R08LN_NN.jpg`) dans le répertoire référencé par `dataDir`. L’image sera utilisée comme motif de pinceau.

### Étape 4 : Ajouter l’image en mosaïque
Créez un chemin rectangulaire et remplissez‑le avec un `XpsImageBrush`. En définissant le mode de mosaïque sur `Tile`, l’image se répète sur tout le rectangle. Ajustez les rectangles source et destination pour contrôler la taille et le positionnement de la mosaïque.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Étape 5 : Enregistrer le document
Persistez le fichier XPS sur le disque. Le fichier de sortie contiendra l’image en mosaïque que vous venez de définir et pourra être ouvert avec n’importe quel visualiseur XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Répétez ces étapes chaque fois que vous devez **ajouter une image en mosaïque** à d’autres pages ou formes dans le même document XPS.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| L’image ne s’affiche pas | Vérifiez que le chemin du fichier (`dataDir + "R08LN_NN.jpg"`) est correct et que l’image est accessible. |
| Le motif en mosaïque apparaît étiré | Ajustez les valeurs `Rectangle2D` source et destination pour contrôler la taille de la mosaïque. |
| L’opacité n’a aucun effet | Assurez‑vous que l’opacité du pinceau est définie **après** la configuration du mode de mosaïque. |

## Questions fréquemment posées

**Q :** Aspose.Page est‑il compatible avec toutes les versions de Java ?  
**A :** Aspose.Page prend en charge Java 8 à Java 21 ; vous pouvez consulter la matrice de compatibilité complète [ici](https://reference.aspose.com/page/java/).

**Q :** Puis‑je utiliser Aspose.Page pour des projets commerciaux ?  
**A :** Oui, une licence commerciale est requise pour une utilisation en production. Les options d’achat sont répertoriées [ici](https://purchase.aspose.com/buy).

**Q :** Existe‑t‑il un essai gratuit disponible ?  
**A :** Un essai gratuit pleinement fonctionnel peut être téléchargé depuis la page des versions Aspose [ici](https://releases.aspose.com/).

**Q :** Où puis‑je obtenir du support communautaire ?  
**A :** Rejoignez le forum communautaire Aspose.Page à [forum](https://forum.aspose.com/c/page/39) pour poser des questions et partager des exemples.

**Q :** Comment obtenir une licence temporaire pour l’évaluation ?  
**A :** Les licences temporaires sont fournies sur demande via le portail Aspose [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous disposez maintenant d’un flux de travail complet, prêt pour la production, pour **comment créer des documents XPS** avec des images en mosaïque en utilisant Aspose.Page for Java. En tirant parti de `XpsImageBrush` et `XpsTileMode.Tile`, vous pouvez générer des graphiques riches et répétables sans gonfler la taille du fichier. Expérimentez avec différentes tailles de mosaïque, niveaux d’opacité et formes pour créer des mises en page de documents sophistiquées. Pour l’étape suivante, explorez l’ajout de formes vectorielles ou de superpositions de texte afin d’enrichir davantage vos fichiers XPS.

---

**Dernière mise à jour :** 2026-05-30  
**Testé avec :** Aspose.Page for Java 24.12 (latest)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ajouter une image aux documents XPS Java – Guide simple avec Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java – Ajouter des pages au tutoriel XPS](/page/java/xps-page-manipulation/add-page/)
- [Convertir XPS en PDF en Java avec Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}