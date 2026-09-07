---
date: 2026-08-29
description: Apprenez à redimensionner des fichiers EPS vectoriels en Java en utilisant
  Aspose.Page. Ce guide étape par étape vous montre comment redimensionner les EPS
  avec des points, des pouces, des millimètres ou des pourcentages.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Redimensionner un fichier EPS en Java
og_description: Le redimensionnement vectoriel Java vous permet d'ajuster les dimensions
  d'un fichier EPS directement en Java. Avec Aspose.Page, vous pouvez redimensionner
  avec des points, des pouces, des millimètres ou des pourcentages tout en préservant
  la qualité vectorielle.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Redimensionnement vectoriel Java : modifier les dimensions d''un EPS avec
  Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Comment redimensionner des fichiers EPS vectoriels en Java avec Aspose.Page
url: /fr/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner des fichiers EPS vectoriels en Java avec Aspose.Page

## Introduction
Si vous devez **redimensionner des EPS vectoriels en Java** de manière programmatique, vous êtes au bon endroit. Ce tutoriel vous guide à travers le redimensionnement des images EPS en Java à l'aide de la bibliothèque Aspose.Page. Que vous souhaitiez doubler la taille, la réduire à une mesure spécifique ou travailler avec des pourcentages, les étapes ci‑dessous vous donnent un contrôle complet sur les dimensions de sortie. Maîtriser le redimensionnement des EPS est essentiel lors de l'adaptation des graphiques à différents agencements d'impression, résolutions d'écran ou directives de marque.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Puis‑je redimensionner en points, pouces ou millimètres ?** Oui – l’API prend en charge les trois unités ainsi que les pourcentages.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure.  
- **Le code est‑il thread‑safe ?** Chaque instance `PsDocument` est isolée, vous pouvez donc traiter les fichiers en parallèle.  

## Qu'est-ce que l'EPS et pourquoi le redimensionner ?
Encapsulated PostScript (EPS) est un format de graphiques vectoriels largement utilisé pour l'impression et l'édition. Parfois, le fichier EPS original est créé à une taille qui ne correspond pas à votre sortie cible – par exemple, un logo conçu à 72 pts peut devoir être à 144 pts pour une brochure plus grande. Savoir **comment redimensionner les eps** vous permet de conserver la qualité vectorielle tout en adaptant les dimensions à n'importe quel flux de travail.

## Pourquoi utiliser Aspose.Page pour redimensionner les EPS ?
Aspose.Page fournit une API simple qui vous permet de spécifier la taille cible dans l'une des unités prises en charge tout en préservant automatiquement la structure vectorielle. La bibliothèque gère la conversion d'unités en interne, vous permettant ainsi de vous concentrer sur les dimensions souhaitées sans calculs manuels.

- **Prend en charge quatre unités de mesure** – Points, Pouces, Millimètres et Pourcentage.  
- **Aucune dépendance externe** – API Java pure, aucune bibliothèque native requise.  
- **Traitement haute performance** – peut gérer jusqu'à 500 fichiers EPS par minute sur un serveur standard à 8 cœurs.  
- **Préserve la fidélité vectorielle** – la sortie reste entièrement évolutive sans rasterisation.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Kit de développement Java (JDK) installé sur votre machine.  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger sur **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Une compréhension de base de la programmation Java.  

## Importer les packages
Dans votre projet Java, incluez les imports requis afin de pouvoir travailler avec les objets Aspose.Page et les flux d'E/S standard.

`PsDocument` représente un document EPS chargé en mémoire.  
`Units` est une énumération qui définit les unités de mesure acceptées par l'API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Comment modifier les dimensions EPS avec différentes unités
Vous pouvez modifier les dimensions EPS en appelant la méthode `resizeEps` avec la largeur, la hauteur souhaitées et une valeur d'énumération `Units` ; cela fonctionne pour les points, pouces, millimètres ou pourcentages. Le même schéma en cinq étapes s'applique à chaque unité, rendant l'API prévisible et facile à intégrer.

`resizeEps` redimensionne le canevas EPS aux dimensions spécifiées tout en conservant les données vectorielles internes.

## Comment redimensionner les EPS en points
Chargez votre EPS, spécifiez la nouvelle taille en points et enregistrez le résultat. Cette approche double les dimensions originales tout en préservant le ratio d'aspect. Utiliser les points vous donne un contrôle précis sur les tailles prêtes à imprimer, ce qui est particulièrement utile pour les mises en page typographiques et les sorties haute résolution.

### Étape 1 : configurer le flux d'entrée
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Étape 2 : initialiser l'objet `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Étape 3 : extraire la taille actuelle de l'image EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Étape 4 : créer un flux de sortie pour le fichier redimensionné
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Étape 5 : redimensionner et enregistrer l'EPS en points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Comment redimensionner les EPS en pouces
Redimensionner en pouces vous permet de correspondre aux spécifications définies en unités impériales, comme les mises en page de brochures ou les normes d'impression américaines. Fournissez la largeur et la hauteur cibles en pouces, et l'API les convertira en unités internes appropriées avant d'appliquer la transformation.

## Comment redimensionner les EPS en millimètres
Lorsque vous travaillez avec des flux de travail basés sur le système métrique, spécifier les dimensions en millimètres assure la cohérence avec les formats de papier et les équipements d'impression utilisés hors des États‑Unis. La bibliothèque gère automatiquement la conversion des millimètres vers le système de coordonnées interne.

## Comment redimensionner les EPS en pourcentages
Redimensionner en pourcentage met à l'échelle les dimensions originales proportionnellement, ce qui est pratique pour des ajustements rapides sans calculer de valeurs absolues. Par exemple, un facteur de `0.5` réduit la largeur et la hauteur de 50 %.

## Pièges courants et conseils
- **Fermez toujours les flux** – Dans le code de production, encapsulez les flux dans un try‑with‑resources pour éviter les verrous de fichiers.  
- **Préservez le ratio d'aspect** – Multipliez la largeur et la hauteur par le même facteur sauf si vous souhaitez intentionnellement une distorsion.  
- **Vérifiez le DPI** – Le redimensionnement ne change pas le DPI ; si vous avez besoin d'un DPI différent, ajustez‑le séparément après le redimensionnement.  
- **Sécurité des threads** – Créez un nouveau `PsDocument` par thread ; partager la même instance peut entraîner des résultats inattendus.  

## Questions fréquemment posées

**Q : Puis‑je utiliser cette bibliothèque pour d’autres formats d’image ?**  
R : Non, Aspose.Page est spécialisé uniquement pour les fichiers PostScript et EPS.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez explorer l’essai gratuit **[Aspose free trial page](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver de l’aide supplémentaire et des discussions ?**  
R : Consultez le **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** pour le support communautaire.

**Q : Comment puis‑je obtenir une licence temporaire ?**  
R : Vous pouvez obtenir une licence temporaire via la **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q : Existe‑t‑il des projets d’exemple disponibles ?**  
R : Oui, consultez la documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.

---

**Dernière mise à jour :** 2026-08-29  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [Redimensionner EPS avec Aspose.Page – Manipulation EPS Java](/page/java/manipulation-eps/)
- [Comment recadrer les fichiers EPS en Java – Guide Aspose.Page](/page/java/manipulation-eps/crop/)
- [Comment mettre à l'échelle un rectangle avec Aspose.Page pour Java](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}