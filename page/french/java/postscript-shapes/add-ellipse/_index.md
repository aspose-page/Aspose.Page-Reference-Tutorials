---
date: 2025-12-11
description: Apprenez à créer une ellipse PostScript en Java avec Aspose.Page. Ce
  guide étape par étape vous montre comment remplir une ellipse avec de la couleur
  et comment dessiner une ellipse en Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Comment créer une ellipse PostScript en Java avec Aspose.Page
url: /fr/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une ellipse PostScript en Java avec Aspose.Page

## Introduction
Créer une **ellipse PostScript** de façon programmatique vous donne un contrôle fin sur les graphiques vectoriels dans les rapports, factures ou tout document imprimable. Dans ce tutoriel, vous apprendrez à **créer des formes d’ellipse PostScript** à l’aide de la bibliothèque Aspose.Page for Java, à remplir une ellipse avec une couleur, et à tracer le contour d’une ellipse. À la fin, vous serez prêt à intégrer des graphiques personnalisés directement dans votre sortie PostScript.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour dessiner des graphiques PostScript en Java ?** Aspose.Page for Java.  
- **Puis‑je remplir une ellipse avec une couleur unie ?** Oui – utilisez `document.setPaint(Color.YOUR_COLOR)` avant `fill`.  
- **Comment tracer uniquement le contour d’une ellipse ?** Définissez la couleur de peinture et le trait, puis appelez `document.draw(...)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence commerciale est requise ; une licence temporaire est disponible pour les tests.  
- **Quelle version de Java est prise en charge ?** Toute version Java 8+ fonctionne avec la version actuelle d’Aspose.Page.

## Qu’est‑ce qu’une ellipse PostScript ?
Une ellipse PostScript est une forme vectorielle définie par un rectangle englobant. Contrairement aux images raster, elle s’échelle sans perte de qualité, ce qui la rend idéale pour l’impression haute résolution et la conversion PDF.

## Pourquoi utiliser Aspose.Page pour créer une ellipse PostScript ?
- **Contrôle total** sur les primitives de dessin (lignes, courbes, ellipses).  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS.  
- **Aucune dépendance externe** – API pure Java, pas de code natif.  
- **Intégration facile** avec les applications Java existantes et les outils de construction.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. Un environnement de développement Java fonctionnel (JDK 8 ou supérieur).  
2. La bibliothèque Aspose.Page for Java ajoutée à votre projet. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  

## Importer les packages
Dans votre fichier source Java, importez les classes nécessaires au dessin et à l’enregistrement du contenu PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guide étape par étape

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

### Étape 2 : Remplir l’ellipse avec une couleur
Définissez la peinture sur la couleur de remplissage souhaitée et appelez `fill` avec une instance `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Étape 3 : Tracer le contour de l’ellipse
Changez la peinture pour la couleur du trait, définissez un `BasicStroke` pour l’épaisseur de ligne, et dessinez le contour de l’ellipse.

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

Vous avez maintenant un fichier PostScript contenant deux ellipses — une remplie d’orange et une autre tracée en rouge. N’hésitez pas à expérimenter avec d’autres coordonnées, tailles et couleurs pour répondre à vos besoins de conception.

## Pièges courants et dépannage
- **Chemin de fichier incorrect** – Assurez‑vous que `dataDir` se termine par un séparateur (`/` ou `\\`) adapté à votre OS.  
- **Licence manquante** – Sans licence valide, la bibliothèque fonctionne en mode d’évaluation et peut ajouter des filigranes.  
- **Couleur non appliquée** – N’oubliez pas d’appeler `document.setPaint(...)` *avant* chaque appel `fill` ou `draw` ; le réglage de la peinture ne persiste pas automatiquement entre les opérations séparées.

## Foire aux questions

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçu pour s’intégrer de façon transparente avec d’autres bibliothèques Java.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Obtenez une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)** à des fins de test.

**Q : Aspose.Page convient‑il aux projets commerciaux ?**  
R : Absolument ! Visitez **[ici](https://purchase.aspose.com/buy)** pour explorer les options de licence commerciale.

**Q : Où puis‑je obtenir de l’aide ou discuter des questions liées à Aspose.Page ?**  
R : Rejoignez la communauté sur le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour des discussions et de l’assistance.

**Q : Existe‑t‑il des ressources gratuites pour en savoir plus sur Aspose.Page for Java ?**  
R : Utilisez l’**[essai gratuit](https://releases.aspose.com/)** et explorez les exemples dans la documentation.

## Conclusion
Aspose.Page for Java rend simple la **création d’ellipses PostScript**, que vous ayez besoin d’une forme remplie simple ou d’un contour complexe. Avec les étapes ci‑dessus, vous pouvez rapidement ajouter des graphiques vectoriels de qualité professionnelle à tout document imprimable. Pour aller plus loin — comme combiner plusieurs formes, appliquer des dégradés ou convertir en PDF—consultez la **[documentation officielle](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-11  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose