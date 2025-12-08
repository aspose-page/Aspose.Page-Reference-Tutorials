---
date: 2025-12-08
description: Apprenez à créer un exemple de dégradé radial en Java PostScript avec
  Aspose.Page. Guide étape par étape avec le code complet et le dépannage.
language: fr
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Exemple de dégradé radial : Java PostScript avec Aspose.Page'
url: /java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple de dégradé radial : Java PostScript avec Aspose.Page

## Introduction
Dans ce tutoriel, vous allez créer un **exemple de dégradé radial** pour un document PostScript en utilisant Aspose.Page pour Java. Nous parcourrons chaque étape — de la configuration du projet au rendu d'un cercle rempli d'un dégradé radial lisse — afin que vous puissiez ajouter instantanément des graphiques accrocheurs à vos applications Java.

## Réponses rapides
- **Que crée ce tutoriel ?** Un fichier PostScript (`.ps`) contenant un cercle rempli d'un dégradé radial.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour Java (dernière version).  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple fonctionnel.  
- **Ai‑je besoin d'une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production ; un essai gratuit suffit pour le développement.  
- **Puis‑je réutiliser le code pour PDF ou SVG ?** Oui — Aspose.Page prend en charge plusieurs formats de sortie avec peu de modifications.

## Qu'est‑ce qu'un dégradé radial ?
Un dégradé radial fait passer les couleurs du centre vers l'extérieur, créant un mélange circulaire et fluide. Il est idéal pour les reflets, les arrière‑plans de boutons ou tout élément visuel nécessitant un effet de « lueur » naturel.

## Pourquoi utiliser Aspose.Page pour les dégradés radiaux ?
- **Rendu indépendant du dispositif** – fonctionne de la même manière sur PostScript, PDF, SVG, et plus encore.  
- **Intégration Java complète** – aucun code natif, uniquement des API Java simples.  
- **Sortie de haute qualité** – prend en charge l'anti‑aliasing et le contrôle de l'espace couleur.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

- Familiarité de base avec la programmation Java.  
- JDK 8 ou version supérieure installé sur votre machine.  
- Bibliothèque Aspose.Page pour Java (téléchargement depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importer les packages
Tout d'abord, importez les classes dont nous aurons besoin. Elles comprennent les types graphiques AWT standard et l'API Aspose.Page.

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

## Étape 1 : Configurer le répertoire du document
Définissez le dossier où le fichier PostScript généré sera enregistré. Remplacez le texte de substitution par un chemin réel sur votre système.

```java
String dataDir = "Your Document Directory";
```

## Étape 2 : Créer le flux de sortie
Ouvrez un `FileOutputStream` qui pointe vers le fichier `.ps` cible. Ce flux alimente les données binaires générées par Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Étape 3 : Créer les options d'enregistrement
Instanciez `PsSaveOptions`. Vous pouvez personnaliser la taille de la page, la compression, etc., mais les valeurs par défaut conviennent pour cet exemple.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Étape 4 : Créer le document PS
Créez l'objet `PsDocument`, en passant le flux de sortie et les options d'enregistrement. Le drapeau `false` indique à Aspose.Page de ne pas ouvrir automatiquement une page (nous le ferons manuellement).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 5 : Créer un cercle
Nous dessinerons un cercle à l'aide de `Ellipse2D.Float`. Les paramètres sont `(x, y, width, height)`. Fixer `width` = `height` crée un cercle parfait.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Étape 6 : Définir les couleurs du dégradé
Préparez deux tableaux : l'un pour les couleurs qui apparaîtront dans le dégradé et l'autre pour les positions fractionnelles correspondantes (0 = centre, 1 = bord).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Étape 7 : Créer l'AffineTransform
`AffineTransform` met à l'échelle et translate le dégradé pour l'adapter à notre cercle. La matrice `(scaleX, 0, 0, scaleY, translateX, translateY)` réalise cela.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Étape 8 : Créer le RadialGradientPaint
Nous construisons maintenant l'objet `RadialGradientPaint`. Il prend le point central, le rayon, le point de focalisation, les fractions de couleur, le tableau de couleurs, la méthode de cycle, l'espace couleur, et la transformation que nous venons de définir.

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

## Étape 9 : Appliquer la peinture et remplir le cercle
Appliquez la peinture de dégradé au document et remplissez le cercle précédemment défini. C’est le cœur de notre **exemple de dégradé radial**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Étape 10 : Fermer la page et enregistrer le document
Finalisez la page, écrivez le contenu sur le disque et fermez le flux. Votre fichier PostScript est maintenant prêt à être visualisé avec n'importe quel visualiseur PS.

```java
document.closePage();
document.save();
```

Félicitations ! Vous avez créé avec succès un exemple de dégradé radial en Java PostScript à l'aide d'Aspose.Page.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **FileNotFoundException** lors de l'ouverture du flux de sortie | Vérifiez que `dataDir` pointe vers un dossier existant et que vous avez les permissions d'écriture. |
| Le dégradé apparaît plat ou manquant | Assurez‑vous que le tableau `fractions` correspond à la longueur du tableau `colors` et que l'`AffineTransform` met correctement à l'échelle. |
| Les couleurs apparaissent inversées | Inversez l'ordre des couleurs dans le tableau `colors` ou ajustez les coordonnées du point `focus`. |

## Questions fréquentes

**Q : Où puis‑je trouver la documentation d'Aspose.Page pour Java ?**  
R : La référence complète de l'API est disponible [ici](https://reference.aspose.com/page/java/).

**Q : Comment télécharger Aspose.Page pour Java ?**  
R : Téléchargez le dernier JAR depuis la [page des releases](https://releases.aspose.com/page/java/).

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Oui — téléchargez une version d'essai [ici](https://releases.aspose.com/).

**Q : Puis‑je obtenir une licence temporaire pour les tests ?**  
R : Bien sûr, demandez‑en une sur la [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support communautaire ?**  
R : Rejoignez la discussion sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusion
Dans ce guide, nous avons construit un **exemple complet de dégradé radial** pour un document PostScript en utilisant Aspose.Page pour Java. En suivant les étapes, vous disposez désormais d'un modèle réutilisable pour créer des dégradés sophistiqués, que vous pouvez adapter à PDF, SVG ou d'autres formats pris en charge. Expérimentez avec différentes couleurs, rayons et formes pour enrichir vos projets graphiques Java.

---

**Dernière mise à jour :** 2025-12-08  
**Testé avec :** Aspose.Page for Java 24.11 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}