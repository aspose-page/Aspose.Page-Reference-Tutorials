---
date: 2026-02-18
description: Apprenez à définir la couleur de peinture et à créer une ellipse PostScript
  en Java avec Aspose.Page. Ce guide montre comment remplir une ellipse en Java, dessiner
  le contour de l'ellipse et définir l'épaisseur du trait.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Définir la couleur du paint pour dessiner une ellipse PostScript en Java
url: /fr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la couleur de peinture pour dessiner une ellipse PostScript en Java

## Introduction
Si vous devez **définir la couleur de peinture** lors du dessin de graphiques vectoriels, la bibliothèque Aspose.Page for Java vous offre un contrôle complet sur chaque trait et remplissage. Dans ce tutoriel, vous découvrirez comment **définir la couleur de peinture**, **remplir une ellipse Java**, et **dessiner le contour d’une ellipse** en suivant une approche simple, étape par étape. À la fin, vous serez capable d’ajouter des ellipses PostScript de haute qualité à des factures, rapports ou tout document imprimable.

## Quick Answers
- **Quelle bibliothèque est la meilleure pour dessiner des graphiques PostScript en Java ?** Aspose.Page for Java.  
- **Puis‑je remplir une ellipse avec une couleur unie ?** Oui – utilisez `document.setPaint(Color.YOUR_COLOR)` avant le `fill`.  
- **Comment dessiner uniquement le contour d’une ellipse ?** Définissez la peinture et le trait, puis appelez `document.draw(...)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise ; une licence temporaire est disponible pour les tests.  
- **Quelle version de Java est prise en charge ?** Tout environnement d’exécution Java 8+ fonctionne avec la version actuelle d’Aspose.Page.

## Qu’est‑ce qu’une ellipse PostScript ?
Une ellipse PostScript est une forme vectorielle définie par un rectangle englobant. Contrairement aux images raster, elle s’échelle sans perte de qualité, ce qui la rend idéale pour l’impression haute résolution et la conversion en PDF.

## Pourquoi utiliser Aspose.Page pour créer une ellipse PostScript ?
- **Contrôle total** sur les primitives de dessin (lignes, courbes, ellipses).  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS.  
- **Aucune dépendance externe** – API Java pure, sans code natif.  
- **Intégration facile** avec les applications Java existantes et les outils de construction.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. Un environnement de développement Java fonctionnel (JDK 8 ou ultérieur).  
2. La bibliothèque Aspose.Page for Java ajoutée à votre projet. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  

## Import Packages
Dans votre fichier source Java, importez les classes requises pour le dessin et l’enregistrement du contenu PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to set paint color for an ellipse
Définir la couleur de peinture est la première étape avant toute opération de remplissage ou de tracé. La méthode `setPaint` détermine la couleur qui sera utilisée pour la prochaine commande de dessin.

### Étape 1 : Configurer le document PostScript
Créez un flux de sortie, configurez la taille de la page et instanciez un `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 2 : Comment remplir une ellipse – utiliser set paint color
Pour **remplir une ellipse**, vous devez d’abord appeler `setPaint` avec la couleur de remplissage souhaitée, puis invoquer `fill` avec une instance `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Étape 3 : Dessiner le contour de l’ellipse et définir l’épaisseur du trait
Après le remplissage, vous pouvez changer la peinture pour une couleur différente, définir un `BasicStroke` pour contrôler la largeur du trait, et dessiner le contour de l’ellipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Étape 4 : Fermer et enregistrer le document
Finalisez la page et écrivez le fichier PostScript sur le disque.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Vous avez maintenant un fichier PostScript contenant deux ellipses — une remplie d’orange et une autre contournée en rouge. N’hésitez pas à expérimenter avec d’autres coordonnées, tailles et couleurs pour répondre à vos besoins de conception.

## Pièges courants et dépannage
- **Chemin de fichier incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur (`/` ou `\\`) approprié à votre OS.  
- **Licence manquante** – Sans licence valide, la bibliothèque fonctionne en mode d’évaluation et peut ajouter des filigranes.  
- **Couleur non appliquée** – N’oubliez pas d’appeler `document.setPaint(...)` *avant* chaque appel `fill` ou `draw` ; le paramètre de peinture ne persiste pas automatiquement entre les opérations séparées.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçu pour s’intégrer de façon transparente avec d’autres bibliothèques Java.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)** à des fins de test.

**Q : Aspose.Page convient‑il aux projets commerciaux ?**  
R : Absolument ! Consultez **[ici](https://purchase.aspose.com/buy)** pour explorer les options de licence commerciale.

**Q : Où puis‑je demander de l’aide ou discuter des questions liées à Aspose.Page ?**  
R : Rejoignez la communauté sur le **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour des discussions et de l’assistance.

**Q : Existe‑t‑il des ressources gratuites pour en savoir plus sur Aspose.Page for Java ?**  
R : Utilisez l’**[essai gratuit](https://releases.aspose.com/)** et explorez les exemples dans la documentation.

## Conclusion
Aspose.Page for Java rend simple le **définir la couleur de peinture**, le **remplir une ellipse**, et le **dessiner le contour d’une ellipse** — que vous ayez besoin d’une forme remplie simple ou d’un graphique tracé complexe. Avec les étapes ci‑dessus, vous pouvez rapidement ajouter des graphiques vectoriels de qualité professionnelle à tout document imprimable. Pour aller plus loin — comme combiner plusieurs formes, appliquer des dégradés ou convertir en PDF — référez‑vous à la **[documentation officielle](https://reference.aspose.com/page/java/)**.

---

**Dernière mise à jour :** 2026-02-18  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}