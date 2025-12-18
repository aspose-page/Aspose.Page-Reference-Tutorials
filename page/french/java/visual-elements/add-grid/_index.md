---
date: 2025-12-18
description: Apprenez comment ajouter une grille et un rectangle transparent dans
  les documents XPS Java avec Aspose.Page. Guide étape par étape pour enregistrer
  efficacement un document XPS.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Comment ajouter une grille avec un pinceau visuel en Java
url: /fr/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une grille avec Visual Brush en Java

## Introduction
Si vous cherchez **comment ajouter une grille** à vos documents XPS générés en Java, vous êtes au bon endroit. Dans ce tutoriel, nous vous guiderons pas à pas pour ajouter une grille avec un Visual Brush, superposer un rectangle transparent, puis **enregistrer le document XPS** à l’aide de l’API Aspose.Page Java. À la fin, vous disposerez d’un rendu soigné réutilisable dans des rapports, factures ou toute application lourde en documents.

## Réponses rapides
- **Que fait un Visual Brush ?** Il peint une zone définie avec du contenu visuel réutilisable, idéal pour les motifs répétés comme les grilles.  
- **Puis‑je changer la couleur de la grille ?** Oui – modifiez les paramètres du pinceau à couleur unie.  
- **Comment ajouter un rectangle transparent au‑dessus de la grille ?** Utilisez `setOpacity` sur un chemin rempli d’une couleur unie.  
- **Quelle méthode enregistre le fichier ?** `doc.save(...)` écrit le fichier XPS sur le disque.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production.

## Qu’est‑ce qu’une grille Visual Brush ?
Un Visual Brush vous permet de définir un petit visuel (le motif de la grille) puis de le dupliquer sur une zone plus grande. Cette approche est plus efficace en mémoire que de dessiner chaque ligne individuellement et offre une répétition pixel‑parfait.

## Pourquoi utiliser Aspose.Page pour cette tâche ?
- **Cross‑platform** – Fonctionne sur tout OS supportant Java.  
- **Rendu haute fidélité** – Contrôle précis des couleurs, de l’opacité et du carrelage.  
- **Aucune dépendance externe** – Tout est géré via la bibliothèque Aspose.Page.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en programmation Java.  
- La bibliothèque Aspose.Page installée – vous pouvez la télécharger depuis la [documentation Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- JDK 8 ou supérieur installé sur votre machine de développement.

## Importer les packages
Tout d’abord, importez les classes requises afin que le compilateur sache où trouver les types que nous allons utiliser :

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Guide étape par étape

### Étape 1 : Configurer votre projet
Créez une nouvelle instance `XpsDocument` et indiquez le dossier où vous souhaitez enregistrer le fichier de sortie.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Étape 2 : Créer un Visual Brush de grille magenta
Nous définissons une petite forme magenta qui sera dupliquée sur la zone de la grille.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Étape 3 : Définir la géométrie pour le Visual Brush
Configurez la zone rectangulaire qui recevra le visuel dupliqué.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Étape 4 : Créer un nouveau Canvas pour le document
Ajoutez un canvas au document et positionnez‑le à l’endroit où la grille doit apparaître.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Étape 5 : Ajouter la grille au Canvas
Appliquez le visual brush à la géométrie, en activant le carrelage.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Étape 6 : Ajouter un rectangle rouge transparent (fonction secondaire)
Ici nous montrons **comment ajouter un rectangle transparent** au‑dessus de la grille pour mettre en évidence.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Étape 7 : Enregistrer le document XPS résultant
Enfin, écrivez le document sur le disque — c’est l’étape **enregistrer le document XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Suivez ces étapes et vous obtiendrez une grille professionnelle avec une superposition transparente, le tout généré de façon programmatique.

## Problèmes courants & astuces

- **Taille de tuile incorrecte :** Assurez‑vous que le `Rectangle2D` utilisé pour le brush correspond à la taille de répétition souhaitée ; sinon le motif risque de s’étirer.  
- **Opacité non appliquée :** N’oubliez pas d’appeler `setOpacity` sur le chemin que vous voulez rendre transparent ; cela n’affecte pas le brush lui‑même.  
- **Fichier non enregistré :** Vérifiez que `dataDir` pointe vers un dossier existant et que votre application possède les droits d’écriture.

## Foire aux questions

**Q : Aspose.Page convient‑il à la génération professionnelle de documents ?**  
R : Oui, Aspose.Page est une bibliothèque robuste conçue pour la génération de haute qualité de XPS et PDF en Java.

**Q : Puis‑je personnaliser les couleurs de la grille avec Visual Brush ?**  
R : Absolument ! Modifiez les paramètres de `createColor` dans l’appel `setFill` du brush avec les valeurs RGBA de votre choix.

**Q : Où puis‑je trouver un support supplémentaire pour Aspose.Page ?**  
R : Consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide communautaire et des réponses officielles.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Page ?**  
R : Oui, vous pouvez accéder à l’[essai gratuit](https://releases.aspose.com/) pour explorer toutes les fonctionnalités avant d’acheter.

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Procurez‑vous une [licence temporaire](https://purchase.aspose.com/temporary-license/) valable pour le développement et l’évaluation.

---

**Dernière mise à jour :** 2025-12-18  
**Testé avec :** Aspose.Page for Java 23.12 (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}