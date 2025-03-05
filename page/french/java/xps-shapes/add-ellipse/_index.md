---
title: Ajouter une ellipse de dégradé radial avec Aspose.Page
linktitle: Ajouter Ellipse dans Java XPS
second_title: API Java Aspose.Page
description: Explorez le guide étape par étape sur l'ajout d'une ellipse à dégradé radial dans Java XPS à l'aide d'Aspose.Page pour Java. Améliorez la création de vos documents sans effort.
type: docs
weight: 10
url: /fr/java/xps-shapes/add-ellipse/
---
## Introduction
Bienvenue dans notre guide étape par étape sur l'ajout d'une ellipse dans Java XPS à l'aide d'Aspose.Page pour Java. Aspose.Page est une puissante bibliothèque Java qui permet aux développeurs de travailler sans effort avec des documents XPS. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'une ellipse à dégradé radial et de son enregistrement en tant que document XPS.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé sur votre machine.
-  Aspose.Page pour la bibliothèque Java téléchargée. Tu peux l'avoir[ici](https://releases.aspose.com/page/java/).
- Un éditeur de code de votre choix (Eclipse, IntelliJ, etc.) pour écrire et exécuter du code Java.
## Importer des packages
Assurez-vous d'avoir importé les packages nécessaires dans votre projet Java pour utiliser Aspose.Page. Ajoutez les instructions d'importation suivantes en haut de votre fichier Java :
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
## Étape 1 : configurer le répertoire de documents
Définissez le chemin d'accès à votre répertoire de documents où le document XPS sera enregistré :
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : Créer un document XPS
Initialisez un nouveau document XPS à l'aide du code suivant :
```java
XpsDocument doc = new XpsDocument();
```
## Étape 3 : Définir les arrêts de dégradé radial
Créez une liste de points de dégradé pour l'ellipse à dégradé radial :
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Étape 4 : Créer une géométrie de chemin
Définissez une ellipse à dégradé radial à l'aide de la géométrie du tracé :
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Étape 5 : Ajouter un canevas et un chemin
Ajoutez un nouveau canevas au document et ajoutez le chemin avec la géométrie définie :
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Étape 6 : Définir le trait et le dégradé
Configurez le trait du tracé avec un pinceau à dégradé radial :
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Étape 7 : Définir l'épaisseur du trait
Spécifiez l'épaisseur du trait du tracé :
```java
path.setStrokeThickness(12f);
```
## Étape 8 : Enregistrez le document
Enregistrez le document XPS résultant :
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Toutes nos félicitations! Vous avez ajouté avec succès une ellipse à dégradé radial dans Java XPS à l'aide d'Aspose.Page pour Java.
## Conclusion
Dans ce didacticiel, nous avons exploré les étapes permettant de créer un document XPS avec une ellipse à dégradé radial visuellement attrayante. Aspose.Page pour Java simplifie la manipulation des documents XPS, offrant aux développeurs un ensemble d'outils puissants.
## Questions fréquemment posées
### Puis-je utiliser Aspose.Page pour Java avec d’autres bibliothèques Java ?
Oui, Aspose.Page pour Java peut être intégré de manière transparente à d’autres bibliothèques Java.
### Aspose.Page est-il adapté au traitement de documents à grande échelle ?
Absolument! Aspose.Page est conçu pour gérer efficacement le traitement de documents à grande échelle.
### Où puis-je trouver plus de didacticiels et d’exemples pour Aspose.Page pour Java ?
 Visiter le[Aspose.Page pour la documentation Java](https://reference.aspose.com/page/java/)pour des tutoriels et des exemples complets.
### Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Existe-t-il des forums communautaires pour les discussions sur Aspose.Page ?
 Oui, rejoignez le[Forum communautaire Aspose.Page](https://forum.aspose.com/c/page/39) pour interagir avec d'autres développeurs et obtenir de l'aide.