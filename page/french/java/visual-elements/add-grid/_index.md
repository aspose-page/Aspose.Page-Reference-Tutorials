---
date: 2026-03-05
description: Apprenez à ajouter une grille avec Visual Brush en Java et Aspose.Page.
  Suivez le guide pas à pas pour améliorer les visuels du document sans effort.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Comment ajouter une grille à l'aide de Visual Brush en Java
url: /fr/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une grille avec Visual Brush en Java

## Introduction
Si vous cherchez à **ajouter une grille** à vos documents générés en Java, la fonctionnalité Visual Brush d’Aspose.Page la rend étonnamment simple. Dans ce tutoriel, nous parcourrons chaque étape, expliquerons pourquoi un Visual Brush est idéal pour les motifs de grille, et vous montrerons un exemple complet et exécutable.

## Réponses rapides
- **Qu’est‑ce qu’un Visual Brush ?** Un élément visuel réutilisable qui peut être répété ou étiré pour remplir une zone.  
- **Pourquoi utiliser une grille ?** Les grilles aident à structurer les mises en page, créer des motifs d’arrière‑plan ou mettre en évidence des sections dans les documents XPS.  
- **Pré‑requis ?** Java JDK, Aspose.Page for Java, et une compréhension de base du graphisme Java.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes une fois la bibliothèque installée.  
- **Puis‑je personnaliser les couleurs ?** Oui – vous contrôlez les couleurs de remplissage, l’opacité et la taille des tuiles directement dans le code.

## Pourquoi utiliser Visual Brush pour ajouter une grille ?
Visual Brush vous permet de définir un petit visuel (la « tuile ») une fois, puis de le répéter sur n’importe quelle forme. Cette approche est efficace en mémoire et garde votre code propre, surtout lorsque vous devez appliquer le même motif à plusieurs canevas.

## Pré‑requis
Avant de plonger dans le code, assurez‑vous de disposer des éléments suivants :
- Compréhension de base de la programmation Java.  
- Bibliothèque Aspose.Page installée. Vous pouvez la télécharger depuis la [documentation Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Java Development Kit (JDK) installé sur votre machine.

## Importer les packages
Assurez‑vous d’avoir les packages nécessaires importés dans votre projet Java :
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

### Étape 1 : Configurer votre projet
Tout d’abord, créez une instance `XpsDocument` et indiquez le dossier où le résultat sera enregistré.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Étape 2 : Créer un Visual Brush de grille magenta
Nous construisons une petite tuile magenta qui sera répétée. La géométrie de chemin définit la forme de la tuile.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Étape 3 : Définir la géométrie du Visual Brush de grille magenta
Ici nous décrivons la zone qui recevra le pinceau en mosaïque.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Étape 4 : Créer un nouveau canvas
Un nouveau canvas est ajouté au document, et nous appliquons une transformation de translation afin que la grille apparaisse à l’endroit souhaité.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Étape 5 : Ajouter la grille au canvas
Nous associons maintenant le visual brush à la géométrie et définissons le mode de mosaïque.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Étape 6 : Ajouter un rectangle rouge transparent
Pour démontrer la superposition, nous superposons un rectangle rouge semi‑transparent au-dessus de la grille.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Étape 7 : Enregistrer le document XPS résultant
Enfin, écrivez le fichier XPS sur le disque.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Suivez ces étapes, et vous ajouterez avec succès une grille visuellement attrayante à l’aide de Visual Brush dans votre application Java avec Aspose.Page.

## Cas d'utilisation courants
- **Arrière‑plans de rapports** : Ajoutez des motifs de grille subtils aux rapports financiers ou techniques pour une meilleure lisibilité.  
- **Modèles de conception** : Créez des modèles de page réutilisables où la même grille se répète sur plusieurs pages.  
- **Mettre en évidence des sections** : Superposez des grilles colorées pour attirer l’attention sur des zones spécifiques du document.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La grille apparaît étirée** | Vérifiez que `TileMode` est défini sur `XpsTileMode.Tile` et que les rectangles source et destination ont la même taille. |
| **Les couleurs semblent incorrectes** | Assurez‑vous d’utiliser les bonnes valeurs RGBA lors de la création du pinceau couleur unie (`createColor(alpha, red, green, blue)`). |
| **Le document n’est pas enregistré** | Vérifiez que `dataDir` pointe vers un dossier existant et accessible en écriture et que vous disposez des permissions nécessaires. |

## Conclusion
Félicitations ! Vous avez appris **à ajouter une grille** à l’aide du Visual Brush d’Aspose.Page en Java. Cette technique vous offre un contrôle fin du rendu des motifs tout en maintenant votre code propre et maintenable.

## Questions fréquentes
### Aspose.Page convient‑il à la génération de documents professionnels ?
Oui, Aspose.Page est une bibliothèque robuste conçue pour la génération professionnelle de documents en Java.

### Puis‑je personnaliser les couleurs de la grille avec Visual Brush ?
Absolument ! Visual Brush vous permet de peindre avec diverses couleurs, offrant une grande flexibilité de personnalisation.

### Où puis‑je trouver un support supplémentaire pour Aspose.Page ?
Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

### Existe‑t‑il un essai gratuit pour Aspose.Page ?
Oui, vous pouvez accéder à l’[essai gratuit](https://releases.aspose.com/) pour explorer les fonctionnalités d’Aspose.Page.

### Comment obtenir une licence temporaire pour Aspose.Page ?
Obtenez une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour vos besoins de test.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour** : 2026-03-05  
**Testé avec** : Aspose.Page for Java (latest release)  
**Auteur** : Aspose  

---