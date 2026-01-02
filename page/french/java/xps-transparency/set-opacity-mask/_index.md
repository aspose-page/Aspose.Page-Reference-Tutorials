---
date: 2026-01-02
description: Apprenez à ajouter un masque d’opacité aux documents XPS avec Aspose.Page
  Java. Guide étape par étape pour créer un rectangle de masque d’opacité et améliorer
  la qualité visuelle.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Définir le masque d'opacité dans Java XPS avec Aspose.Page Java
url: /fr/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir un masque d'opacité dans Java XPS avec Aspose.Page Java

## Introduction
Bienvenue dans notre guide complet sur les masques d'opacité **aspose page java**. Dans ce tutoriel, vous apprendrez à créer un document XPS, ajouter un canvas, et appliquer un masque d'opacité à un rectangle — le tout avec la puissante API Aspose.Page Java. À la fin, vous serez capable d'ajouter des rectangles avec masque d'opacité qui donnent à vos fichiers XPS un aspect soigné et semi‑transparent.

## Réponses rapides
- **Que fait un masque d'opacité ?** Il définit des niveaux de transparence variables pour une forme, laissant le contenu sous‑jacent transparaître.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (aspose page java).  
- **Ai-je besoin d'une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Combien de lignes de code ?** Environ 20 lignes de Java plus quelques instructions d'initialisation.  
- **Puis-je réutiliser le masque sur plusieurs formes ?** Oui, vous pouvez assigner le même ImageBrush à plusieurs chemins.

## Qu'est‑ce qu'un masque d'opacité dans XPS ?
Un masque d'opacité est un bitmap ou un vecteur qui contrôle l'alpha (transparence) de chaque pixel d'une forme. Lorsqu'il est appliqué à un rectangle, certaines parties du rectangle deviennent totalement opaques, partiellement transparentes ou totalement transparentes, créant des effets visuels sophistiqués.

## Pourquoi utiliser Aspose.Page Java pour les masques d'opacité ?
- **API complète de style .NET en Java** – modèle d'objets intuitif.  
- **Aucune dépendance externe** – fonctionne avec du Java pur.  
- **Rendu haute fidélité** – les masques sont rendus exactement comme dans la spécification XPS.  
- **Multi‑plateforme** – s'exécute sous Windows, Linux ou macOS sans modifications.

## Prérequis
- Une compréhension de base de la programmation Java.  
- Bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Une licence valide pour Aspose.Page. Si vous n'en avez pas, obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.  
- Un environnement de développement capable de compiler et d'exécuter des applications Java (par ex., IntelliJ IDEA, Eclipse ou VS Code).

## Importer les packages
Commencez par importer les classes nécessaires de la bibliothèque Aspose.Page. Cela rend l'API disponible pour votre projet.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guide étape par étape

### Étape 1 : créer un nouveau document XPS
Instanciez d'abord un nouveau document XPS qui contiendra tous nos graphiques.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Étape 2 : ajouter un canvas
Un canvas agit comme une surface de dessin à l'intérieur de la page XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Étape 3 : ajouter un rectangle et appliquer un remplissage uni
Ici nous créons un chemin de rectangle et lui appliquons un remplissage rouge uni. Ce rectangle recevra plus tard le masque d'opacité.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Étape 4 : ajouter un masque d'opacité à l'aide d'un ImageBrush
Nous chargeons une image TIFF, définissons les rectangles source et destination, et réglons le pinceau en mode tuile afin que le masque se répète si nécessaire.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Étape 5 : enregistrer le document XPS résultant
Enfin, persistez le document sur le disque. Le fichier de sortie contiendra le rectangle avec le masque d'opacité appliqué.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Suivez attentivement ces étapes pour intégrer la fonctionnalité **add opacity mask** dans votre document Java XPS à l'aide d'Aspose.Page.

## Problèmes courants et dépannage
- **Image non trouvée** – Vérifiez que `dataDir` pointe vers le bon dossier et que `R08SY_NN.tif` existe.  
- **Le masque apparaît solide** – Assurez-vous que l'image source contient réellement des valeurs alpha variables ; une image totalement opaque ne montrera pas de transparence.  
- **Le mode tuile n'est pas respecté** – Le rectangle de destination doit être plus petit que le rectangle source pour que le carrelage soit perceptible.

## Foire aux questions

**Q : Aspose.Page est‑il compatible avec tous les environnements de développement Java ?**  
R : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec divers IDE Java et outils de construction.

**Q : Puis‑je utiliser Aspose.Page sans licence ?**  
R : Bien que vous puissiez évaluer la bibliothèque avec une licence temporaire, une licence complète est requise pour une utilisation en production.

**Q : Y a‑t‑il des limitations dans la version d'essai ?**  
R : La version d'essai peut imposer des restrictions de taille ou de fonctionnalités ; consultez la documentation officielle pour plus de détails.

**Q : Comment obtenir du support pour Aspose.Page ?**  
R : Visitez le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour obtenir de l'aide de la communauté ou achetez une licence pour une assistance premium.

**Q : Existe‑t‑il une garantie de remboursement pour Aspose.Page ?**  
R : Référez‑vous à la **[page d'achat](https://purchase.aspose.com/buy)** pour les informations sur les politiques de remboursement.

**Dernière mise à jour** : 2026-01-02  
**Testé avec** : Aspose.Page Java 24.11 (dernière version au moment de la rédaction)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}