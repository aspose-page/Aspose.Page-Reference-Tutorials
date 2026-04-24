---
date: 2026-04-24
description: Apprenez à définir la couleur d’un rectangle et à ajouter un rectangle
  en Java XPS à l’aide d’Aspose.Page. Ce guide couvre l’ajout de rectangles en Java
  et la modification du trait du rectangle.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Ajouter un rectangle dans Java XPS
second_title: Aspose.Page Java API
title: Définir la couleur du rectangle et ajouter un rectangle en Java XPS
url: /fr/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la couleur du rectangle et ajouter un rectangle en Java XPS

## Introduction
Dans ce guide, vous apprendrez comment **définir la couleur du rectangle** et **ajouter un rectangle** en Java XPS à l'aide de la bibliothèque Aspose.Page. Que vous ayez besoin de dessiner des formes simples pour un rapport ou de créer des graphiques vectoriels complexes, maîtriser le style des rectangles vous donne un contrôle précis sur vos documents XPS.  

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis-je modifier le trait du rectangle ?** Oui, en utilisant `setStroke` et `setStrokeThickness`  
- **Un profil couleur CMYK est‑il pris en charge ?** Absolument – vous pouvez charger des profils ICC comme indiqué  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise pour une utilisation non‑évaluation  
- **Combien de temps prend l’implémentation ?** Typiquement moins de 10 minutes pour un rectangle de base

## Qu’est‑ce que **set rectangle color** ?
Définir la couleur d’un rectangle signifie spécifier la couleur de remplissage ou du trait que la forme utilisera dans le document XPS final. Avec Aspose.Page, vous pouvez utiliser les espaces colorimétriques RGB, CMYK, ou même des profils ICC personnalisés pour obtenir une correspondance de couleur exacte.

## Pourquoi utiliser Aspose.Page pour **add rectangle java** et **change rectangle stroke** ?
- **API complète** – prend en charge les couleurs unies et les dégradés.  
- **Multiplateforme** – fonctionne sur n’importe quel runtime Java sans dépendances natives.  
- **Support géométrique riche** – créez des chemins complexes, appliquez des transformations et gérez facilement l’épaisseur du trait.  

## Prérequis
- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page installée. Sinon, téléchargez‑la depuis la [documentation Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Environnement de développement Java fonctionnel (IDE, JDK, etc.).  

## Importer les packages
Pour commencer, importez les packages nécessaires dans votre projet Java. Assurez‑vous que la bibliothèque Aspose.Page est correctement ajoutée à votre classpath. Voici un exemple de base :
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Maintenant, décomposons l’exemple fourni en plusieurs étapes pour **ajouter un rectangle** et **définir sa couleur** en Java XPS.

## Étape 1 : définir le répertoire du document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Remplacez `"Your Document Directory"` par le chemin absolu où vous souhaitez lire/écrire les fichiers XPS.

## Étape 2 : créer un nouveau document XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Cette ligne initialise un nouveau document XPS qui contiendra nos formes.

## Étape 3 : ajouter un rectangle à contour solide CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Cette étape ajoute un **rectangle à contour** avec une couleur solide CMYK. La méthode `setStroke` définit la couleur du contour du rectangle, tandis que `setStrokeThickness` contrôle l’épaisseur de la ligne — idéal pour **modifier le trait du rectangle**.

### Astuce :
Si vous préférez une couleur RGB, remplacez l’appel `createColor` par `doc.createColor(0, 0, 255)` pour un remplissage bleu uni.

## Étape 4 : enregistrer le document XPS résultant
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Enfin, enregistrez le document XPS sur le disque. Le fichier `AddRectangle_out.xps` contient maintenant un rectangle dont vous avez défini la couleur et le contour.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Rectangle non visible** | Géométrie du chemin incorrecte ou épaisseur du trait réglée à 0 | Vérifiez la chaîne du chemin (`"M 20,10 L 220,10 220,100 20,100 Z"`) et assurez‑vous que `setStrokeThickness` est supérieur à 0. |
| **Couleur incorrecte** | Utilisation d’un profil ICC qui ne correspond pas à l’espace couleur prévu | Utilisez `doc.createColor(r, g, b)` pour le RGB ou revérifiez le chemin du fichier ICC. |
| **Fichier non enregistré** | `dataDir` pointe vers un dossier inexistant ou n’a pas les permissions d’écriture | Créez le dossier au préalable ou choisissez un emplacement avec droits d’écriture. |

## Questions fréquemment posées

**Q :** *Puis‑je ajouter plusieurs rectangles dans un même document XPS ?*  
**R :** Oui. Répétez simplement les étapes de création de géométrie et de style pour chaque rectangle nécessaire.

**Q :** *Comment changer la couleur de remplissage du rectangle au lieu du contour ?*  
**R :** Utilisez `path.setFill(...)` avec un pinceau de couleur unie, de façon similaire à `setStroke`.

**Q :** *Aspose.Page convient‑il aux manipulations complexes de documents XPS ?*  
**R :** Absolument. La bibliothèque prend en charge des fonctionnalités avancées comme les dégradés, les transformations et les polices intégrées.

**Q :** *Où puis‑je trouver des exemples supplémentaires et du support communautaire ?*  
**R :** Explorez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour plus d’exemples de code et d’aide entre pairs.

**Q :** *Puis‑je essayer Aspose.Page avant d’acheter ?*  
**R :** Oui, vous pouvez explorer un [essai gratuit](https://releases.aspose.com/) pour évaluer les capacités de l’API.

---

**Dernière mise à jour :** 2026-04-24  
**Testé avec :** Aspose.Page for Java 24.12  
**Auteur :** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}