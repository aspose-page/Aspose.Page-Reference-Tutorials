---
title: Redimensionner les fichiers EPS en Java avec Aspose.Page
linktitle: Redimensionner le fichier EPS en Java
second_title: API Java Aspose.Page
description: Apprenez à redimensionner des fichiers EPS en Java sans effort avec Aspose.Page pour Java. Suivez notre guide complet pour des instructions étape par étape.
weight: 11
url: /fr/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Redimensionner les fichiers EPS en Java avec Aspose.Page

## Introduction
Bienvenue dans notre guide étape par étape sur le redimensionnement des fichiers EPS en Java à l'aide de la puissante bibliothèque Aspose.Page. Si vous avez déjà eu besoin d'ajuster les dimensions de vos images EPS par programmation, vous êtes au bon endroit. Dans ce didacticiel, nous explorerons diverses options de redimensionnement, notamment les points, les pouces, les millimètres et les pourcentages, vous offrant ainsi la flexibilité dont vous avez besoin pour répondre à vos besoins spécifiques.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé sur votre machine.
-  Aspose.Page pour la bibliothèque Java. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/java/).
- Une compréhension de base de la programmation Java.
## Importer des packages
Dans votre projet Java, assurez-vous de disposer des importations nécessaires pour utiliser les fonctionnalités Aspose.Page. Voici un exemple :
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Maintenant, décomposons le didacticiel en plusieurs étapes pour chaque option de redimensionnement :
## Redimensionner l'EPS à l'aide de points
### Étape 1 : Configurer le flux d'entrée
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Étape 2 : initialiser l'objet PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Étape 3 : Extraire la taille actuelle de l'image EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Étape 4 : Créer un flux de sortie
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Étape 5 : Redimensionner et enregistrer en points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Redimensionner l'EPS en utilisant les pouces
Suivez des étapes similaires à celles de l'exemple 1, en remplaçant « Points » par « Pouces » et en ajustant la nouvelle taille en conséquence.
## Redimensionner l'EPS en utilisant des millimètres
Suivez des étapes similaires à celles de l'exemple 1, en remplaçant « Points » par « Millimètres » et en ajustant la nouvelle taille en conséquence.
## Redimensionner l'EPS à l'aide de pourcentages
Suivez des étapes similaires à celles de l'exemple 1, en remplaçant « Points » par « Pourcentages » et en ajustant la nouvelle taille en conséquence.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment redimensionner des fichiers EPS en Java à l'aide d'Aspose.Page. Ce guide vous propose des options polyvalentes, vous permettant d'adapter le processus de redimensionnement pour répondre à vos besoins spécifiques.

## FAQ
### Puis-je utiliser cette bibliothèque pour d’autres formats d’image ?
Non, Aspose.Page est spécialement conçu pour gérer les fichiers PostScript et EPS.
### Existe-t-il un essai gratuit disponible pour Aspose.Page pour Java ?
Oui, vous pouvez explorer l'essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je trouver de l’aide et des discussions supplémentaires ?
 Visiter le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien de la communauté.
### Comment puis-je obtenir un permis temporaire ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Existe-t-il des exemples de projets disponibles ?
 Oui, vérifiez la documentation[ici](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
