---
title: Ajouter un dégradé horizontal dans Java XPS
linktitle: Ajouter un dégradé horizontal dans Java XPS
second_title: API Java Aspose.Page
description: Découvrez comment ajouter un superbe dégradé horizontal aux documents XPS en Java à l'aide d'Aspose.Page. Suivez notre guide étape par étape pour une intégration transparente.
weight: 11
url: /fr/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé horizontal dans Java XPS

## Introduction
Bienvenue dans ce guide étape par étape sur l'ajout d'un dégradé horizontal dans Java XPS à l'aide d'Aspose.Page pour Java. Aspose.Page pour Java est une bibliothèque puissante qui permet aux développeurs de travailler de manière transparente avec des documents XPS (XML Paper Spécification).
Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'une application Java pour ajouter un dégradé horizontal à un document XPS. Suivez les étapes ci-dessous pour y parvenir facilement.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1. Environnement de développement Java : assurez-vous que Java est installé sur votre système. Sinon, téléchargez et installez la dernière version de Java à partir de[java.com](https://www.java.com).
2.  Bibliothèque Aspose.Page pour Java : vous devez disposer de la bibliothèque Aspose.Page pour Java. Vous pouvez le télécharger depuis le[Aspose.Page pour la documentation Java](https://reference.aspose.com/page/java/).
## Importer des packages
Commencez par importer les packages nécessaires à votre application Java. Incluez la bibliothèque Aspose.Page pour Java dans votre projet. Vous pouvez le faire en ajoutant les lignes de code suivantes :
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Étape 1 : initialiser le document
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
//Initialiser le document
XpsDocument doc = new XpsDocument();
```
## Étape 2 : Créer un dégradé horizontal
```java
// Dégradé horizontal
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Étape 3 : ajouter un chemin avec un dégradé
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Étape 4 : Enregistrez le document
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Répétez ces étapes si nécessaire, en ajustant les paramètres en fonction de vos besoins spécifiques.
## Conclusion
Toutes nos félicitations! Vous avez ajouté avec succès un dégradé horizontal à un document XPS à l'aide d'Aspose.Page pour Java. Ce didacticiel a fourni un guide complet aux développeurs cherchant à améliorer leurs applications Java avec des effets de dégradé.
## FAQ
### Q : Puis-je appliquer plusieurs dégradés dans un seul document XPS ?
Oui, vous pouvez ajouter plusieurs tracés avec différents dégradés pour créer des conceptions complexes.
### Q : Aspose.Page est-il compatible avec les dernières versions de Java ?
Aspose.Page pour Java est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions de Java.
### Q : Existe-t-il d'autres types de dégradés disponibles dans Aspose.Page ?
Oui, outre les dégradés linéaires, Aspose.Page prend en charge les dégradés radiaux pour des effets plus diversifiés.
### Q : Puis-je personnaliser les couleurs et les positions des points de dégradé ?
Absolument! Vous avez un contrôle total sur les couleurs et les positions de chaque arrêt de dégradé.
### Q : Existe-t-il un forum communautaire pour Aspose.Page où je peux demander de l'aide ?
 Oui, vous pouvez visiter le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour entrer en contact avec la communauté et obtenir de l'aide.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
