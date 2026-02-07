---
date: 2026-02-07
description: Apprenez à redimensionner des fichiers EPS en Java et à modifier les
  dimensions EPS à l’aide d’Aspose.Page. Ce guide pas à pas vous montre comment redimensionner
  un EPS en points, pouces, millimètres ou pourcentages.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Comment redimensionner les fichiers EPS en Java avec Aspose.Page
url: /fr/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner les fichiers EPS en Java avec Aspose.Page

## Introduction
Si vous cherchez une méthode fiable **pour redimensionner les fichiers EPS** de façon programmatique, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons le redimensionnement des images EPS en Java à l’aide de la bibliothèque Aspose.Page. Que vous ayez besoin de doubler la taille, de la réduire à une mesure précise ou de travailler avec des pourcentages, les étapes ci‑dessous vous donnent un contrôle total sur les dimensions de sortie. Comprendre **comment redimensionner les eps** est essentiel lorsque vous devez adapter les graphiques à différents formats d’impression ou résolutions d’écran.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Puis‑je redimensionner en points, pouces ou millimètres ?** Oui – l’API prend en charge les trois unités ainsi que les pourcentages.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure.  
- **Le code est‑il thread‑safe ?** Chaque instance de `PsDocument` est isolée, vous pouvez donc traiter les fichiers en parallèle.  

## Qu’est‑ce que l’EPS et pourquoi le redimensionner ?
Encapsulated PostScript (EPS) est un format de graphiques vectoriels populaire utilisé dans l’édition et l’impression. Parfois, le fichier EPS original est créé à une taille qui ne correspond pas à votre sortie cible – par exemple, un logo conçu à 72 pts peut devoir être à 144 pts pour une brochure plus grande. Savoir **comment redimensionner les eps** vous permet de conserver la qualité vectorielle tout en adaptant les dimensions à n’importe quel flux de travail.

## Pourquoi utiliser Aspose.Page pour redimensionner les EPS ?
- **Contrôle total sur les unités** – points, pouces, millimètres ou pourcentages.  
- **Aucune dépendance externe** – API Java pure, aucune bibliothèque native.  
- **Haute performance** – adaptée au traitement par lots sur les serveurs.  
- **Préserve la fidélité vectorielle** – la sortie reste évolutive sans rasterisation.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Java Development Kit (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Une compréhension de base de la programmation Java.  

## Importer les packages
Dans votre projet Java, incluez les imports nécessaires afin de travailler avec les objets Aspose.Page et les flux d’E/S standards.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Comment modifier les dimensions EPS avec différentes unités
La bibliothèque vous permet de **modifier les dimensions eps** simplement en sélectionnant l’énumération `Units` appropriée. Ci‑dessous, nous parcourrons le même modèle en cinq étapes pour les points, pouces, millimètres et pourcentages. La seule chose qui change est l’unité que vous transmettez à `resizeEps`.

## Comment redimensionner les EPS en points
Voici un exemple complet, étape par étape, qui double la taille d’un fichier EPS en utilisant les points comme unité de mesure.

### Étape 1 : Configurer le flux d’entrée
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Étape 2 : Initialiser l’objet `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Étape 3 : Extraire la taille actuelle de l’image EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Étape 4 : Créer un flux de sortie pour le fichier redimensionné
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Étape 5 : Redimensionner et enregistrer l’EPS en utilisant les points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Comment redimensionner les EPS en pouces
Le même modèle en cinq étapes s’applique ; il suffit de remplacer `Units.Points` par `Units.Inches` et d’ajuster le facteur d’échelle à la valeur en pouces souhaitée.

## Comment redimensionner les EPS en millimètres
Encore une fois, suivez les mêmes étapes, en remplaçant l’unité par `Units.Millimeters`. Cela est pratique lorsque vous avez besoin de dimensions métriques pour les flux de travail d’impression.

## Comment redimensionner les EPS en pourcentages
Pour un redimensionnement basé sur les pourcentages, conservez l’unité `Units.Percent`. Multipliez la largeur et la hauteur originales par le pourcentage souhaité (par ex., `0.5` pour une réduction de 50 %).

## Pièges courants & conseils
- **Fermez toujours les flux** – Dans le code de production, encapsulez les flux dans un try‑with‑resources pour éviter les verrous de fichiers.  
- **Conservez le ratio d’aspect** – Multipliez la largeur et la hauteur par le même facteur sauf si vous souhaitez intentionnellement une distorsion.  
- **Vérifiez le DPI** – Le redimensionnement ne modifie pas le DPI ; si vous avez besoin d’un DPI différent, ajustez‑le séparément après le redimensionnement.  
- **Sécurité des threads** – Créez un nouveau `PsDocument` par thread ; partager la même instance peut entraîner des résultats inattendus.  

## Questions fréquemment posées

**Q : Puis‑je utiliser cette bibliothèque pour d’autres formats d’image ?**  
R : Non, Aspose.Page est spécialisé uniquement pour les fichiers PostScript et EPS.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez explorer l’essai gratuit **[ici](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver de l’aide supplémentaire et des discussions ?**  
R : Visitez le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour le support communautaire.

**Q : Comment obtenir une licence temporaire ?**  
R : Vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Existe‑t‑il des projets d’exemple disponibles ?**  
R : Oui, consultez la documentation **[ici](https://reference.aspose.com/page/java/)**.

---

**Dernière mise à jour :** 2026-02-07  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}