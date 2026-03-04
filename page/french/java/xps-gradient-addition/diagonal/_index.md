---
date: 2025-12-25
description: Apprenez à créer des documents XPS en Java et à ajouter un magnifique
  dégradé diagonal à l'aide d'Aspose.Page. Ce guide explique comment ajouter un dégradé,
  appliquer un dégradé linéaire et utiliser Aspose efficacement.
linktitle: Add Diagonal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Comment créer un document XPS avec un dégradé diagonal en Java
url: /fr/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé diagonal dans Java XPS

## Introduction
Dans le développement Java moderne, créer des documents XPS au rendu soigné est un facteur différenciant clé. Dans ce tutoriel, vous apprendrez **how to create XPS document** et comment les améliorer avec un dégradé diagonal en utilisant Aspose.Page for Java. Nous passerons en revue chaque étape, expliquerons pourquoi chaque élément est important, et vous montrerons comment **add gradient path**, **apply linear gradient**, et obtenir rapidement un résultat visuel professionnel.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Page for Java  
- **Quelle méthode ajoute le dégradé ?** `createLinearGradientBrush` avec des arrêts de dégradé  
- **Ai-je besoin d'une licence ?** Un essai fonctionne pour le développement ; une licence commerciale est requise pour la production  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un dégradé diagonal basique  
- **Puis-je l'utiliser avec d'autres frameworks Java ?** Oui, l'API est indépendante du framework  

## Qu'est-ce qu'un dégradé diagonal dans un document XPS ?
Un dégradé diagonal passe en douceur d'une couleur à une autre le long d'une ligne inclinée, apportant profondeur et intérêt visuel aux formes. Dans XPS, les dégradés sont définis par un pinceau contenant plusieurs arrêts de dégradé, chacun spécifiant une couleur et sa position relative.

## Pourquoi ajouter un dégradé diagonal avec Aspose.Page ?
- **Qualité visuelle riche** – les dégradés sont rendus avec précision dans le format XPS.  
- **Cohérence multiplateforme** – le même fichier XPS apparaît identique sur les visionneuses Windows, macOS et Linux.  
- **API simple** – Aspose.Page abstrait les spécifications XPS de bas niveau, vous permettant de vous concentrer sur le design.  

## Prérequis
- Connaissances de base en programmation Java.  
- JDK installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger **[here](https://releases.aspose.com/page/java/)**.  
- Un IDE tel qu'IntelliJ IDEA ou Eclipse.

## Importer les packages
Commencez par importer les classes dont vous aurez besoin. Ces imports vous donnent accès à la géométrie, à la gestion des dégradés et à la création de documents XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Étape 1 : Configurer votre projet
Créez un nouveau projet Java dans votre IDE préféré et ajoutez les fichiers JAR Aspose.Page au chemin de construction du projet.

## Étape 2 : Définir le répertoire du document
Spécifiez où le fichier XPS généré sera enregistré.

```java
String dataDir = "Your Document Directory";
```

## Étape 3 : Créer le document XPS
Instanciez l'objet `XpsDocument` – c’est l’objet central avec lequel vous travaillerez pour **create XPS document**.

```java
XpsDocument doc = new XpsDocument();
```

## Étape 4 : Ajouter le chemin du dégradé diagonal
Créez un chemin rectangulaire qui recevra le dégradé. La géométrie du chemin utilise une simple commande move‑line‑close.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Étape 5 : Définir les arrêts du dégradé linéaire
Configurez les couleurs et leurs positions. Chaque arrêt définit un point dans le dégradé où une couleur spécifique apparaît.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Étape 6 : Appliquer le dégradé linéaire au chemin
Maintenant **apply linear gradient** au chemin que vous avez créé. Le pinceau est défini par deux points qui déterminent la direction du dégradé, et les arrêts sont attachés au pinceau.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Étape 7 : Enregistrer le document
Persistez le fichier XPS sur le disque. Le fichier contiendra le rectangle rempli avec le dégradé diagonal que vous avez défini.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Pièges courants & conseils
- **Direction du dégradé** – assurez-vous que les points de départ et d'arrivée du pinceau reflètent la diagonale souhaitée ; les inverser renverse le dégradé.  
- **Précision des couleurs** – Aspose utilise ARGB ; si vous avez besoin de transparence, incluez le canal alpha lors de la création des couleurs.  
- **Chemin du fichier** – utilisez toujours un chemin absolu ou vérifiez que le chemin relatif pointe vers un répertoire existant et accessible en écriture.  

## FAQ supplémentaire

**Q : Comment **how to add gradient** à une forme XPS existante ?**  
R : Créez un `XpsLinearGradientBrush`, définissez les arrêts de dégradé, et assignez‑le à la propriété `Fill` de la forme comme indiqué à l'étape 6.

**Q : Que fait réellement **apply linear gradient** en arrière‑plan ?**  
R : Il génère une définition de pinceau dans le package XPS qui référence les points de départ/arrivée et une collection d’arrêts de dégradé, que le visualiseur rend comme une transition de couleur fluide.

**Q : Existe‑t‑il un moyen rapide de **how to use aspose** pour d’autres fonctionnalités XPS ?**  
R : Oui, l’API Aspose.Page comprend des méthodes pour ajouter des images, du texte et des formes personnalisées — explorez simplement la classe `XpsDocument` pour découvrir d’autres assistants.

**Q : Puis‑je **add gradient path** à des formes non rectangulaires ?**  
R : Bien sûr. Définissez n’importe quelle géométrie avec `createPathGeometry` puis affectez‑lui un pinceau dégradé.

**Q : Le dégradé affecte‑t‑il significativement la taille du fichier ?**  
R : Seulement marginalement ; les définitions de dégradé sont des entrées XML légères dans le package XPS.

**Dernière mise à jour :** 2025-12-25  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}