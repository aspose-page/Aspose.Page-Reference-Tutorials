---
title: Ajouter Ellipse dans Java PostScript
linktitle: Ajouter Ellipse dans Java PostScript
second_title: API Java Aspose.Page
description: Maîtrisez la création de superbes documents PostScript en Java avec Aspose.Page. Apprenez à ajouter des points de suspension étape par étape pour un contenu visuellement attrayant.
type: docs
weight: 10
url: /fr/java/postscript-shapes/add-ellipse/
---
## Introduction
Dans le monde dynamique du développement Java, la création de documents visuellement attrayants est une exigence courante. Aspose.Page pour Java est une bibliothèque puissante qui permet aux développeurs de manipuler les fichiers PostScript sans effort. Dans ce didacticiel, nous verrons comment ajouter des points de suspension aux documents PostScript à l'aide d'Aspose.Page pour Java. Suivez-nous pour améliorer vos compétences en création de documents !
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir configuré les conditions préalables suivantes :
1. Environnement de développement Java : assurez-vous qu'un environnement de développement Java fonctionnel est installé sur votre ordinateur.
2.  Bibliothèque Aspose.Page pour Java : téléchargez et incluez la bibliothèque Aspose.Page dans votre projet Java. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/page/java/).
## Importer des packages
Dans votre code Java, importez les packages nécessaires pour utiliser la fonctionnalité Aspose.Page. Voici un exemple :
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Étape 1 : Configurez votre document
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer un flux de sortie pour un document PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();
// Créer un nouveau document PS avec la page ouverte
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Étape 2 : remplir l'ellipse de couleur
```java
// Set de peinture pour remplir l'ellipse
document.setPaint(Color.ORANGE);
// Remplissez la première ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Étape 3 : Décrire l'ellipse avec un trait
```java
// Définir la peinture pour caresser l’ellipse
document.setPaint(Color.RED);
// Définir la course
document.setStroke(new BasicStroke(3));
// Tracer (décrire) la deuxième ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Étape 4 : Fermer et enregistrer le document
```java
// Fermer la page actuelle
document.closePage();
// Enregistrez le document
document.save();
```
Vous avez maintenant ajouté avec succès des points de suspension à votre document PostScript à l'aide d'Aspose.Page pour Java ! Expérimentez avec différentes coordonnées et dimensions pour personnaliser vos visuels.
## Conclusion
 Aspose.Page pour Java simplifie le processus de création et de manipulation de documents PostScript. Ce didacticiel vous a doté des connaissances nécessaires pour ajouter des ellipses, fournissant ainsi une base solide pour des visualisations plus complexes. Plongez dans le[Documentation](https://reference.aspose.com/page/java/) pour plus de détails et de fonctionnalités.
## FAQ
### Q : Puis-je utiliser Aspose.Page pour Java avec d’autres bibliothèques Java ?
: Oui, Aspose.Page pour Java est conçu pour s'intégrer de manière transparente à d'autres bibliothèques Java.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 R : Obtenez une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) à des fins de tests.
### Q : Aspose.Page est-il adapté aux projets commerciaux ?
 R : Absolument ! Visite[ici](https://purchase.aspose.com/buy) pour explorer les options de licence pour une utilisation commerciale.
### Q : Où puis-je demander de l'aide ou discuter des requêtes liées à Aspose.Page ?
 R : Rejoignez la communauté au[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour des discussions et de l'aide.
### Q : Existe-t-il des ressources gratuites pour en savoir plus sur Aspose.Page pour Java ?
 R : Utilisez le[essai gratuit](https://releases.aspose.com/) et explorez des exemples dans la documentation.