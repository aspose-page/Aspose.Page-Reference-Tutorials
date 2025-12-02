---
date: 2025-12-02
description: Apprenez à redimensionner les fichiers EPS en Java sans effort avec Aspose.Page.
  Ce guide étape par étape vous montre comment redimensionner les EPS en utilisant
  des points, des pouces, des millimètres ou des pourcentages.
language: fr
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Comment redimensionner les fichiers EPS en Java avec Aspose.Page
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner les fichiers EPS en Java avec Aspose.Page

## Introduction
Si vous cherchez un moyen fiable **comment redimensionner les fichiers EPS** de façon programmatique, vous êtes au bon endroit. Dans ce tutoriel, nous allons parcourir le redimensionnement des images EPS en Java à l'aide de la bibliothèque Aspose.Page. Que vous ayez besoin de doubler la taille, de la réduire à une mesure spécifique, ou de travailler avec des pourcentages, les étapes ci‑dessous vous donnent un contrôle complet sur les dimensions de sortie.

## Quick Answers
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Puis‑je redimensionner en points, pouces ou millimètres ?** Oui – l’API prend en charge les trois unités ainsi que les pourcentages.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise en production.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure.  
- **Le code est‑il thread‑safe ?** Chaque instance de `PsDocument` est isolée, vous pouvez donc traiter les fichiers en parallèle.

## Prerequisites
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Une compréhension de base de la programmation Java.  

## Import Packages
Dans votre projet Java, incluez les imports requis afin de travailler avec les objets Aspose.Page et les flux d’E/S standard.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Resize EPS Using Points
Voici un exemple complet, étape par étape, qui double la taille d’un fichier EPS en utilisant les points comme unité de mesure.

### Step 1: Set up the input stream
Étape 1 : Configurer le flux d’entrée
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
Étape 2 : Initialiser l’objet `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
Étape 3 : Extraire la taille actuelle de l’image EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
Étape 4 : Créer un flux de sortie pour le fichier redimensionné
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
Étape 5 : Redimensionner et enregistrer l’EPS en utilisant les points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
Comment redimensionner les EPS en pouces  
Le même schéma en cinq étapes s’applique ; il suffit de remplacer `Units.Points` par `Units.Inches` et d’ajuster le facteur d’échelle selon les besoins.

## How to Resize EPS Using Millimeters
Comment redimensionner les EPS en millimètres  
Encore une fois, suivez les mêmes étapes en remplaçant l’unité par `Units.Millimeters`. Cela est pratique lorsque vous avez besoin de dimensions métriques pour les flux de travail d’impression.

## How to Resize EPS Using Percentages
Comment redimensionner les EPS en pourcentages  
Pour un redimensionnement basé sur les pourcentages, conservez l’unité `Units.Percent`. Multipliez la largeur et la hauteur d’origine par le pourcentage souhaité (par ex., `0.5` pour une réduction de 50 %).

## Common Pitfalls & Tips
Pièges courants et conseils
- **Fermez toujours les flux** – Dans le code de production, encapsulez les flux dans un try‑with‑resources pour éviter les verrous de fichiers.  
- **Conservez le ratio d’aspect** – Multipliez la largeur et la hauteur par le même facteur sauf si vous souhaitez intentionnellement une distorsion.  
- **Vérifiez le DPI** – Le redimensionnement ne change pas le DPI ; si vous avez besoin d’un DPI différent, ajustez‑le séparément après le redimensionnement.

## Conclusion
Vous savez maintenant **comment redimensionner les fichiers EPS** en Java avec Aspose.Page, que vous préfériez les points, les pouces, les millimètres ou les pourcentages. Cette flexibilité vous permet d’intégrer la manipulation d’EPS dans des pipelines automatisés, des utilitaires de bureau ou des services côté serveur.

## Frequently Asked Questions

**Q : Puis‑je utiliser cette bibliothèque pour d’autres formats d’image ?**  
R : Non, Aspose.Page est spécialisé uniquement pour les fichiers PostScript et EPS.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez explorer l’essai gratuit **[ici](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver de l’aide supplémentaire et des discussions ?**  
R : Consultez le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour le support communautaire.

**Q : Comment obtenir une licence temporaire ?**  
R : Vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Existe‑t‑il des projets d’exemple disponibles ?**  
R : Oui, consultez la documentation **[ici](https://reference.aspose.com/page/java/)**.

---

**Dernière mise à jour :** 2025-12-02  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}