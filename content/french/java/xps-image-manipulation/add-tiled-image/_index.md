---
title: Ajouter une image en mosaïque dans Java XPS
linktitle: Ajouter une image en mosaïque dans Java XPS
second_title: API Java Aspose.Page
description: Explorez la manipulation transparente de documents Java XPS avec Aspose.Page. Apprenez à ajouter des images en mosaïque sans effort à l'aide de ce guide étape par étape.
type: docs
weight: 11
url: /fr/java/xps-image-manipulation/add-tiled-image/
---
## Introduction
Dans le monde dynamique du développement Java, le besoin d’une manipulation et d’une création efficaces de documents ne cesse de croître. Aspose.Page pour Java apparaît comme un outil puissant, offrant aux développeurs la possibilité de travailler de manière transparente avec des documents XPS. Ce didacticiel se concentre sur une tâche spécifique : ajouter une image en mosaïque à un document Java XPS.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Page pour Java : téléchargez et installez Aspose.Page pour Java à partir du[site web](https://releases.aspose.com/page/java/).
3. Votre répertoire de documents : choisissez ou créez un répertoire dans lequel vous souhaitez enregistrer votre document XPS.
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour utiliser les fonctionnalités Aspose.Page :
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Décomposons maintenant le processus d'ajout d'une image en mosaïque à un document Java XPS en étapes claires et gérables.
## Étape 1 : Configurez votre projet
Commencez par configurer votre projet Java, en vous assurant qu'Aspose.Page for Java est correctement intégré.
## Étape 2 : Créer un document XPS
Initialisez un nouveau document XPS à l'aide du code suivant :
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```
## Étape 3 : Définir le chemin de l'image en mosaïque
Spécifiez le chemin d'accès à l'image en mosaïque que vous souhaitez ajouter au document XPS.
## Étape 4 : ajouter une image en mosaïque
Utilisez l'extrait de code ci-dessous pour ajouter une image en mosaïque au document XPS :
```java
// Image de tuile
// Rectangle rempli d'ImageBrush en haut à droite ci-dessous
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Étape 5 : Enregistrez le document
Enfin, enregistrez le document XPS résultant en utilisant le code ci-dessous :
```java
// Enregistrer le document XPS résultant
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Répétez ces étapes pour incorporer sans effort une image en mosaïque dans votre document Java XPS à l'aide d'Aspose.Page.
## Conclusion
Aspose.Page pour Java rationalise le processus de travail avec les documents XPS, offrant aux développeurs une solution efficace pour la manipulation de documents. En suivant ce guide étape par étape, vous pouvez facilement ajouter une image en mosaïque à votre document Java XPS.

## FAQ
### Aspose.Page est-il compatible avec toutes les versions de Java ?
 Aspose.Page est conçu pour fonctionner avec différentes versions de Java. Assurez la compatibilité en vérifiant la documentation[ici](https://reference.aspose.com/page/java/).
### Puis-je utiliser Aspose.Page pour des projets commerciaux ?
Oui, Aspose.Page propose des licences commerciales. Achetez-les[ici](https://purchase.aspose.com/buy).
### Existe-t-il un essai gratuit disponible ?
 Oui, explorez les fonctionnalités d'Aspose.Page avec un essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver le soutien et les discussions de la communauté ?
 Engagez-vous avec la communauté Aspose.Page sur le[forum](https://forum.aspose.com/c/page/39).
### Comment puis-je obtenir une licence temporaire pour Aspose.Page ?
 Acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).