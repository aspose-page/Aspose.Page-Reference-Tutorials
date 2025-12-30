---
date: 2025-12-30
description: Apprenez à créer un document XPS en Java en ajoutant des rectangles avec
  Aspose.Page. Suivez ce guide étape par étape pour une manipulation fluide des documents
  XPS.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Créer un document XPS Java – Ajouter un rectangle avec Aspose.Page
url: /fr/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS Java – Ajouter un rectangle

## Introduction
Dans ce tutoriel complet, vous **créerez des fichiers XPS document Java** et apprendrez comment ajouter des rectangles à l'aide de la bibliothèque Aspose.Page. Que vous construisiez des rapports, des factures ou des graphiques personnalisés, maîtriser la création de rectangles vous donne un contrôle précis sur la mise en page XPS. Nous parcourrons chaque étape, expliquerons le pourquoi de chaque ligne de code et vous montrerons comment personnaliser les couleurs et les traits pour des résultats professionnels.

## Réponses rapides
- **Quelle bibliothèque est recommandée ?** Aspose.Page for Java  
- **Combien de temps prend l'implémentation ?** Environ 10 minutes pour un rectangle de base  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production  
- **Quelle version de Java est prise en charge ?** Java 8 et ultérieure  
- **Puis‑je ajouter plusieurs formes ?** Oui – répétez les étapes pour chaque forme

## Pré‑requis
Avant de commencer, assurez‑vous d'avoir :

- Des connaissances de base du langage de programmation Java.  
- La bibliothèque Aspose.Page installée. Sinon, vous pouvez la télécharger depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Un environnement de développement Java fonctionnel (IDE, JDK et Maven/Gradle si vous le préférez).

## Importer les packages
Pour démarrer, importez les packages nécessaires dans votre projet Java. Assurez‑vous que la bibliothèque Aspose.Page est correctement ajoutée à votre classpath. Voici un exemple de base :

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes pour ajouter un rectangle dans un XPS Java.

## Étape 1 : Définir le répertoire du document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin du dossier où vous souhaitez stocker les fichiers XPS.

## Étape 2 : Créer un nouveau document XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Cette ligne **crée** un nouveau document XPS que vous pourrez ensuite remplir avec des formes, du texte ou des images.

## Étape 3 : Ajouter un rectangle à contour couleur solide CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Cette étape ajoute un rectangle à contour avec une couleur solide CMYK. Vous pouvez modifier la chaîne de géométrie (`"M 20,10 L 220,10 220,100 20,100 Z"`) pour changer la taille ou la position, et ajuster les valeurs de couleur dans `createColor` selon votre conception.

## Étape 4 : Enregistrer le document XPS résultant
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Enfin, enregistrez le document XPS modifié avec le rectangle ajouté dans le répertoire que vous avez spécifié précédemment.

## Cas d'utilisation courants
- **En‑têtes de rapport** – Utilisez des rectangles comme blocs d'arrière‑plan pour les titres.  
- **Tableaux de facturation** – Mettez en évidence des cellules ou des sections avec des bordures colorées.  
- **Graphiques personnalisés** – Combinez plusieurs rectangles pour créer des formes complexes.

## Conseils de dépannage
- **Erreur fichier non trouvé :** Vérifiez que `dataDir` pointe vers un dossier existant et que le profil ICC (`uswebuncoated.icc`) est présent.  
- **Couleurs incorrectes :** Assurez‑vous que le profil ICC correspond à l'espace colorimétrique que vous souhaitez utiliser (CMYK vs. RGB).  
- **Dimensions inattendues :** Ajustez la chaîne de géométrie pour refléter les coordonnées correctes.

## Conclusion
Félicitations ! Vous avez appris avec succès comment **créer des fichiers XPS document Java** et ajouter des rectangles à l'aide d'Aspose.Page. Cette base vous permet de créer des documents XPS plus riches, de personnaliser les graphiques et d'intégrer des formes dans des flux de travail plus larges.

## FAQ
### Puis‑je ajouter plusieurs rectangles dans un même document XPS ?
Oui, vous pouvez ajouter autant de rectangles que nécessaire en répétant les étapes décrites dans le tutoriel.

### Comment puis‑je changer la couleur du rectangle ?
Modifiez les valeurs de couleur dans la méthode `createColor` pour obtenir la couleur souhaitée.

### Aspose.Page est‑il adapté à la manipulation de documents XPS complexes ?
Absolument ! Aspose.Page offre un ensemble complet de fonctionnalités pour gérer diverses tâches liées aux documents XPS.

### Où puis‑je trouver des exemples supplémentaires et du support ?
Explorez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour plus d'exemples et demandez de l'aide à la communauté.

### Puis‑je essayer Aspose.Page avant d'acheter ?
Oui, vous pouvez explorer un [essai gratuit](https://releases.aspose.com/) pour découvrir les capacités d'Aspose.Page.

## Questions fréquentes

**Q : Cette approche fonctionne‑t‑elle avec Java 11 ou une version plus récente ?**  
R : Oui, la bibliothèque Aspose.Page est compatible avec Java 8 et ultérieure, y compris Java 11, 17 et au‑delà.

**Q : Puis‑je intégrer des images à l'intérieur de la zone du rectangle ?**  
R : Vous pouvez ajouter un élément `XpsImage` et le positionner au‑dessus ou à l'intérieur du rectangle en utilisant les mêmes coordonnées de géométrie.

**Q : Comment définir une couleur de remplissage au lieu d'un simple contour ?**  
R : Appelez `path.setFill(...)` avec un pinceau couleur solide créé via `doc.createSolidColorBrush(...)`.

**Q : Est‑il possible de faire pivoter le rectangle ?**  
R : Appliquez une matrice de transformation au chemin avec `path.setTransform(...)` pour obtenir une rotation ou un redimensionnement.

**Q : Quelle licence est requise pour une utilisation en production ?**  
R : Une licence commerciale Aspose.Page est nécessaire pour le déploiement ; l'essai gratuit est limité à l'évaluation et au développement.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-30  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version)  
**Auteur :** Aspose  

---