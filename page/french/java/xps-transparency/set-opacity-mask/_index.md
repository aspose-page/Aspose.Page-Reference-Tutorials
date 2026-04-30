---
date: 2026-04-30
description: Apprenez à créer un document XPS en Java et à ajouter un masque d'opacité
  avec Aspose.Page Java. Guide étape par étape avec des exemples de code.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Définir le masque d'opacité dans Java XPS
second_title: Aspose.Page Java API
title: Créer un document XPS Java – Définir le masque d'opacité avec Aspose.Page
url: /fr/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir un masque d'opacité dans Java XPS avec Aspose.Page Java

## Introduction
Dans ce tutoriel, vous allez **create XPS document Java** et apprendre comment appliquer un masque d'opacité qui donne à vos graphiques un aspect poli et semi‑transparent. Nous parcourrons l’ensemble du processus — depuis l'initialisation d'un document XPS, l'ajout d'un canvas, le dessin d'un rectangle, jusqu'à l'attachement d'un masque d'opacité basé sur une image — en utilisant l'API intuitive Aspose.Page Java. À la fin, vous serez capable de générer des fichiers XPS professionnels de manière programmatique et de réutiliser le masque sur n'importe quelle forme dont vous avez besoin.

## Réponses rapides
- **À quoi sert un masque d'opacité ?** Il définit des niveaux de transparence variables pour une forme, permettant au contenu sous‑jacent de transparaître.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (aspose page java).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire fonctionne pour les tests ; une licence complète est requise pour la production.  
- **Combien de lignes de code ?** Environ 20 lignes de Java plus quelques instructions d'initialisation.  
- **Puis‑je réutiliser le masque sur plusieurs formes ?** Oui, vous pouvez assigner le même `ImageBrush` à plusieurs chemins.

## Qu'est‑ce qu'un masque d'opacité dans XPS ?
Un masque d'opacité est un bitmap ou un vecteur qui contrôle l'alpha (transparence) de chaque pixel d'une forme. Lorsqu'il est appliqué à un rectangle, certaines parties du rectangle deviennent totalement opaques, partiellement transparentes ou totalement transparentes, créant des effets visuels sophistiqués sans couches de dessin supplémentaires.

## Pourquoi utiliser Aspose.Page Java pour **create XPS document java** ?
- **Pure Java API** – Aucune dépendance native, le même code s'exécute sous Windows, Linux ou macOS.  
- **Full XPS spec compliance** – Les masques sont rendus exactement comme défini par la norme XPS.  
- **Object‑oriented design** – Similaire à .NET, ce qui facilite la prise en main si vous avez utilisé Aspose dans d’autres langages.  
- **High performance** – Optimisé pour les gros documents et le traitement par lots.

## Cas d’utilisation courants
- **Watermarking** – Appliquer un logo semi‑transparent sur les pages.  
- **Dynamic theming** – Modifier le style visuel des éléments UI dans les rapports générés.  
- **Print‑ready previews** – Montrer à quoi ressemble un design avec une opacité variable avant de l'envoyer à l'imprimante.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :
- Une compréhension de base de la programmation Java.  
- La bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Une licence valide pour Aspose.Page. Si vous n'en avez pas, obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.  
- Un environnement de développement capable de compiler et d'exécuter des applications Java (par ex., IntelliJ IDEA, Eclipse ou VS Code).

## Importer les packages
Commencez par importer les classes nécessaires depuis la bibliothèque Aspose.Page. Cela garantit que l'API est disponible pour votre projet.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guide étape par étape

### Étape 1 : Créer un nouveau document XPS
Tout d'abord, créez une nouvelle instance d'un document XPS qui contiendra tous nos graphiques.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Étape 2 : Ajouter un canvas
Un canvas sert de surface de dessin à l'intérieur de la page XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Étape 3 : Ajouter un rectangle et appliquer un remplissage uni
Ici, nous créons un chemin de rectangle et lui appliquons un remplissage rouge uni. Ce rectangle recevra plus tard le masque d'opacité.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Étape 4 : Ajouter un masque d'opacité à l'aide d'un ImageBrush
Nous chargeons une image TIFF, définissons les rectangles source et destination, et réglons le pinceau en mode mosaïque afin que le masque se répète si nécessaire.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Étape 5 : Enregistrer le document XPS résultant
Enfin, enregistrez le document sur le disque. Le fichier de sortie contiendra le rectangle avec le masque d'opacité appliqué.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Suivez attentivement ces étapes pour incorporer la fonctionnalité **add opacity mask** dans votre document Java XPS en utilisant Aspose.Page.

## Problèmes courants et dépannage
- **Image not found** – Vérifiez que `dataDir` pointe vers le bon dossier et que `R08SY_NN.tif` existe.  
- **Mask appears solid** – Assurez‑vous que l'image source contient réellement des valeurs alpha variables ; une image totalement opaque ne montrera pas de transparence.  
- **Tile mode not respected** – Le rectangle de destination doit être plus petit que le rectangle source pour que le mode mosaïque soit perceptible.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec tous les environnements de développement Java ?**  
A : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec divers IDE Java et outils de construction.

**Q : Puis‑je utiliser Aspose.Page sans licence ?**  
A : Bien que vous puissiez évaluer la bibliothèque avec une licence temporaire, une licence complète est requise pour une utilisation en production.

**Q : Existe‑t‑il des limitations dans la version d'essai ?**  
A : La version d'essai peut imposer des restrictions de taille ou de fonctionnalités ; consultez la documentation officielle pour plus de détails.

**Q : Comment puis‑je obtenir du support pour Aspose.Page ?**  
A : Visitez le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour obtenir de l'aide communautaire ou achetez une licence pour une assistance premium.

**Q : Existe‑t‑il une garantie de remboursement pour Aspose.Page ?**  
A : Référez‑vous à la **[page d'achat](https://purchase.aspose.com/buy)** pour les informations sur les politiques de remboursement.

---

**Dernière mise à jour :** 2026-04-30  
**Testé avec :** Aspose.Page Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}