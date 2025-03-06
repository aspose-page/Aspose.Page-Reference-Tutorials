---
title: Ajouter un dégradé vertical dans Java XPS
linktitle: Ajouter un dégradé vertical dans Java XPS
second_title: API Java Aspose.Page
description: Découvrez comment ajouter un dégradé vertical aux documents Java XPS avec Aspose.Page. Améliorez l’attrait visuel sans effort. Guide étape par étape à l’intérieur.
weight: 12
url: /fr/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé vertical dans Java XPS

## Introduction
Dans ce didacticiel, nous allons explorer comment ajouter un dégradé vertical dans Java XPS à l'aide d'Aspose.Page pour Java. L'ajout de dégradés à vos documents XPS peut améliorer l'attrait visuel de votre contenu, le rendant plus attrayant et esthétique.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Un environnement de développement Java fonctionnel.
-  Aspose.Page pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/java/).
- Une compréhension de base de la programmation Java.
## Importer des packages
Commencez par importer les packages nécessaires à votre projet Java. Assurez-vous d'avoir inclus la bibliothèque Aspose.Page pour Java dans les dépendances de votre projet.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
        
// Importer Aspose.Page pour Java
```
## Étape 1 : initialiser le document
Commencez par initialiser le document XPS. Cela pose les bases de l'ajout d'éléments tels que des chemins et des dégradés à votre document.
```java
// Initialiser le document
XpsDocument doc = new XpsDocument();
```
## Étape 2 : Créer un chemin avec un dégradé vertical
Créons maintenant un chemin avec un dégradé vertical. Cela implique de définir la géométrie du chemin et de spécifier les arrêts du dégradé.
```java
// Créer un chemin avec une géométrie
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Définir des arrêts de dégradé verticaux
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Appliquer le dégradé vertical au chemin
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Étape 3 : Enregistrez le document
Enfin, enregistrez le document XPS avec le dégradé vertical ajouté dans le répertoire de votre choix.
```java
// Enregistrez le document
doc.save(dataDir + "VerticalGradient.xps");
```
Toutes nos félicitations! Vous avez ajouté avec succès un dégradé vertical à votre document Java XPS à l'aide d'Aspose.Page.
## Conclusion
Améliorer vos documents XPS avec des dégradés peut améliorer considérablement leur attrait visuel. Aspose.Page pour Java simplifie ce processus, vous permettant de créer facilement des documents époustouflants.

### FAQ
### Puis-je utiliser Aspose.Page pour Java dans des projets commerciaux ?
 Oui, Aspose.Page pour Java est disponible pour un usage commercial. Vous pouvez l'acheter[ici](https://purchase.aspose.com/buy).
### Existe-t-il un essai gratuit disponible pour Aspose.Page pour Java ?
 Oui, vous pouvez accéder à un essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver la documentation d’Aspose.Page pour Java ?
 La documentation est disponible[ici](https://reference.aspose.com/page/java/).
### Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 Obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Besoin d'aide ou avez des questions ?
 Visitez la communauté Aspose.Page[forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
