---
date: 2025-12-28
description: Apprenez à créer un document XPS en Java avec Aspose.Page et à ajouter
  une image en mosaïque sans effort grâce à ce guide étape par étape.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Comment créer un document XPS avec une image en mosaïque en Java
url: /fr/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS et ajouter une image en mosaïque en Java

## Introduction
Dans le développement Java moderne, la capacité de **créer des fichiers de document XPS** de manière programmatique est une compétence précieuse, surtout lorsque vous devez les enrichir avec des graphiques tels que des images en mosaïque. Aspose.Page for Java rend ce processus simple, vous permettant de vous concentrer sur la conception visuelle plutôt que sur la gestion de fichiers de bas niveau. Dans ce tutoriel, vous apprendrez exactement comment créer un document XPS, **ajouter une image en mosaïque**, et enregistrer le résultat, le tout avec des exemples de code clairs, étape par étape.

## Quick Answers
- **Que fait Aspose.Page ?** Il fournit une API de haut niveau pour générer et manipuler des documents XPS en Java.  
- **Puis‑je mettre une image en mosaïque ?** Oui – utilisez `XpsImageBrush` avec `XpsTileMode.Tile`.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou commerciale est requise pour une utilisation en production.  
- **Quelle version de Java est prise en charge ?** Toute version JDK 8+ est compatible.  
- **Combien de temps prend l’implémentation ?** Environ 10–15 minutes pour un scénario d’image en mosaïque basique.

## Qu’est‑ce que « créer un document XPS » ?
Un fichier XPS (XML Paper Specification) est un format de document à mise en page fixe similaire au PDF. Créer un document XPS de façon programmatique vous permet de générer des fichiers imprimables, indépendants du dispositif, directement depuis du code Java.

## Pourquoi ajouter une image en mosaïque ?
Mettre une image en mosaïque répète le graphique sur une zone définie, ce qui est parfait pour les arrière‑plans, les filigranes ou les remplissages de motifs. En utilisant `XpsTileMode.Tile` d’Aspose.Page, vous pouvez obtenir cela en quelques lignes de code seulement.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – JDK 8 ou version supérieure installé.  
2. **Aspose.Page for Java** – téléchargez depuis le [site web](https://releases.aspose.com/page/java/).  
3. **Un répertoire accessible en écriture** – où le fichier XPS généré sera enregistré.

## Import Packages
Dans votre projet Java, importez les classes nécessaires :

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guide étape par étape

### Étape 1 : Configurer votre projet
Ajoutez les fichiers JAR d’Aspose.Page à votre classpath et vérifiez que les déclarations d’importation se compilent sans erreurs.

### Étape 2 : Créer le document XPS
Instanciez un nouvel objet `XpsDocument`. C’est le conteneur principal qui contiendra toutes les pages, chemins et ressources.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Étape 3 : Définir le chemin de l’image en mosaïque
Placez l’image que vous souhaitez mettre en mosaïque (par ex., `R08LN_NN.jpg`) dans le répertoire référencé par `dataDir`. L’image sera utilisée comme motif de brosse.

### Étape 4 : Ajouter l’image en mosaïque
Créez un chemin rectangulaire et remplissez‑le avec un `XpsImageBrush`. En définissant le mode de mosaïque sur `Tile`, l’image se répète sur tout le rectangle.

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
Persistez le fichier XPS sur le disque. Le fichier de sortie contiendra l’image en mosaïque que vous venez de définir.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Répétez ces étapes chaque fois que vous devez **ajouter une image en mosaïque** à d’autres pages ou formes au sein du même document XPS.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| L’image n’apparaît pas | Vérifiez que le chemin du fichier (`dataDir + "R08LN_NN.jpg"`) est correct et que l’image est accessible. |
| Le motif de mosaïque apparaît étiré | Ajustez les valeurs `Rectangle2D` source et destination pour contrôler la taille de la mosaïque. |
| L’opacité n’a aucun effet | Assurez‑vous que l’opacité de la brosse est définie **après** la configuration du mode de mosaïque. |

## Foire aux questions

### Aspose.Page est‑il compatible avec toutes les versions de Java ?
Aspose.Page est conçu pour fonctionner avec diverses versions de Java. Assurez‑vous de la compatibilité en consultant la documentation [ici](https://reference.aspose.com/page/java/).

### Puis‑je utiliser Aspose.Page pour des projets commerciaux ?
Oui, Aspose.Page propose des licences commerciales. Achetez‑les [ici](https://purchase.aspose.com/buy).

### Existe‑t‑il une version d’essai gratuite ?
Oui, explorez les fonctionnalités d’Aspose.Page avec un essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver le support communautaire et les discussions ?
Rejoignez la communauté Aspose.Page sur le [forum](https://forum.aspose.com/c/page/39).

### Comment obtenir une licence temporaire pour Aspose.Page ?
Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2025-12-28  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version)  
**Auteur :** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
