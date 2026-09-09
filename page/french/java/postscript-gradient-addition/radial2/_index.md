---
date: 2026-09-09
description: Apprenez comment créer un gradient dans Java PostScript et ajouter un
  gradient à une forme en utilisant Aspose.Page. Suivez ce guide step‑by‑step avec
  code et tips.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Gradient radial Java PostScript avec Aspose.Page
og_description: Apprenez comment créer un gradient dans Java PostScript et ajouter
  un gradient à une forme en utilisant Aspose.Page. Suivez ce guide step‑by‑step avec
  code et tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Comment créer un gradient dans Java PostScript avec radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Comment créer un gradient dans Java PostScript avec radial fill
url: /fr/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un dégradé en Java PostScript avec remplissage radial

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer des dégradés** graphiques dans un document PostScript en utilisant Java et Aspose.Page. Nous parcourrons chaque étape — de la configuration du projet au rendu d’un cercle rempli d’un dégradé radial fluide — afin que vous puissiez **ajouter un dégradé à une forme** instantanément et améliorer la qualité visuelle de vos applications Java.

## Réponses rapides
- **Que crée ce tutoriel ?** Un fichier PostScript (`.ps`) contenant un cercle rempli d’un dégradé radial.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (dernière version).  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple fonctionnel.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour la production ; un essai gratuit suffit pour le développement.  
- **Puis‑je réutiliser le code pour PDF ou SVG ?** Oui — Aspose.Page prend en charge plusieurs formats de sortie avec peu de modifications.

## Comment remplir une forme avec un dégradé en PostScript
Vous pouvez remplir une forme avec un dégradé radial en PostScript en créant un `PsDocument`, en définissant un `RadialGradientPaint`, en l’appliquant à la forme cible, puis en enregistrant le document. Ce flux de travail concis vous permet de produire des graphiques vectoriels d’aspect professionnel sans images raster, et le même code peut être réutilisé pour les sorties PDF ou SVG. Le processus est simple et fonctionne de manière cohérente sur tous les formats pris en charge.

## Qu’est‑ce qu’un dégradé radial ?
Un dégradé radial fait passer les couleurs du centre vers l’extérieur, créant une transition circulaire douce. Il est idéal pour les reflets, les arrière‑plans de boutons ou tout visuel nécessitant un effet de « lueur » naturel. En variant les arrêts de couleur et le rayon, vous pouvez simuler l’éclairage, la profondeur et les propriétés matérielles en pur vecteur.

## Pourquoi utiliser Aspose.Page pour les dégradés radiaux ?
Aspose.Page vous permet de générer des graphiques vectoriels indépendants du dispositif avec une seule API Java. Il prend en charge plus de 50 formats d’entrée et de sortie — dont PostScript, PDF et SVG — tout en conservant la précision des couleurs et l’anti‑aliasing pour des rendus haute résolution. La bibliothèque fournit également des classes de dégradé faciles à utiliser, rendant les effets visuels complexes simples à implémenter.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Une connaissance de base de la programmation Java.  
- JDK 8 ou une version plus récente installée sur votre machine.  
- La bibliothèque Aspose.Page for Java (téléchargez‑la depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin. Elles comprennent les types graphiques AWT standard et l’API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Étape 1 : configurer le répertoire du document
Définissez le dossier où le fichier PostScript généré sera enregistré. Remplacez le texte de substitution par un chemin réel sur votre système.

```java
String dataDir = "Your Document Directory";
```

## Étape 2 : créer le flux de sortie
`FileOutputStream` écrit les octets bruts dans un fichier, permettant d’enregistrer des données binaires. En ouvrant un flux ciblant un fichier `.ps`, Aspose.Page transmet directement les données PostScript générées sur le disque.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Étape 3 : créer les options d’enregistrement
`PsSaveOptions` configure la façon dont un fichier PostScript est enregistré, incluant la taille de page et la compression. Vous pouvez personnaliser ces paramètres, mais les valeurs par défaut conviennent à cet exemple.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Étape 4 : créer le document ps
`PsDocument` représente un document PostScript en mémoire et fournit des méthodes pour ajouter des pages et des graphiques.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 5 : créer un cercle
`Ellipse2D.Float` décrit une forme d’ellipse ; lorsque la largeur = hauteur, elle devient un cercle parfait. Cet objet servira de canevas pour notre remplissage de dégradé.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Comment dessiner un cercle avec un dégradé
Pour dessiner un cercle avec un dégradé radial, vous chargez un `RadialGradientPaint` dans le contexte graphique puis remplissez l’ellipse précédemment définie. Cette opération unique peint la forme avec une transition de couleur douce du centre vers l’extérieur, créant un effet visuel attrayant.

## Étape 6 : définir les couleurs du dégradé
Préparez deux tableaux : l’un pour les couleurs qui apparaîtront dans le dégradé et l’autre pour les positions fractionnelles correspondantes (0 = centre, 1 = bord).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Étape 7 : créer l’AffineTransform
`AffineTransform` est une matrice qui peut translater, faire pivoter, mettre à l’échelle ou ciseler les objets graphiques. Ici, elle met à l’échelle et translate le dégradé afin qu’il s’ajuste précisément à l’intérieur du cercle.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Étape 8 : créer le RadialGradientPaint
`RadialGradientPaint` crée un dégradé de couleur radial basé sur un point central, un rayon et des arrêts de couleur.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Étape 9 : définir la peinture et remplir le cercle
Appliquez la peinture de dégradé au document et remplissez le cercle précédemment défini. C’est le cœur de notre **exemple de dégradé radial** et cela montre comment **remplir une forme avec un dégradé**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Étape 10 : fermer la page et enregistrer le document
Finalisez la page, écrivez le contenu sur le disque et fermez le flux. Votre fichier PostScript est maintenant prêt à être visualisé avec n’importe quel lecteur PS.

```java
document.closePage();
document.save();
```

Félicitations ! Vous avez créé avec succès un exemple de dégradé radial en Java PostScript grâce à Aspose.Page. Vous disposez désormais d’un modèle réutilisable pour **remplir une forme avec un dégradé** qui peut être adapté à d’autres formes et formats de sortie.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **FileNotFoundException** lors de l’ouverture du flux de sortie | Vérifiez que `dataDir` pointe vers un dossier existant et que vous avez les permissions d’écriture. |
| Le dégradé apparaît plat ou absent | Assurez‑vous que le tableau `fractions` correspond à la longueur du tableau `colors` et que l’`AffineTransform` met à l’échelle correctement. |
| Les couleurs semblent inversées | Inversez l’ordre des couleurs dans le tableau `colors` ou ajustez les coordonnées du point de focalisation. |

## Questions fréquentes

**Q : Où puis‑je trouver la documentation d’Aspose.Page for Java ?**  
R : La référence complète de l’API est disponible dans la [documentation Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q : Comment télécharger Aspose.Page for Java ?**  
R : Téléchargez le dernier JAR depuis la [page des releases](https://releases.aspose.com/page/java/).

**Q : Existe‑t‑il une version d’essai gratuite ?**  
R : Oui — téléchargez une version d’essai depuis la [page de téléchargement d’essai gratuit d’Aspose](https://releases.aspose.com/).

**Q : Puis‑je obtenir une licence temporaire pour les tests ?**  
R : Absolument, demandez‑en une sur la [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Rejoignez la discussion sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusion
Dans ce guide, nous avons construit un **exemple complet de dégradé radial** pour un document PostScript en utilisant Aspose.Page for Java. En suivant les étapes, vous disposez maintenant d’un modèle réutilisable pour **remplir une forme avec un dégradé**, que vous pouvez adapter à PDF, SVG ou tout autre format supporté par Aspose.Page. Expérimentez avec différentes couleurs, rayons et formes pour enrichir vos projets graphiques Java.

---

**Dernière mise à jour :** 2026-09-09  
**Testé avec :** Aspose.Page for Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un dégradé PostScript en Java – Ajouter un dégradé vertical](/page/java/postscript-gradient-addition/vertical/)
- [Créer un motif de texture en PostScript avec Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Tutoriel Aspose.Page Transparency – Ajouter de la transparence en Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}