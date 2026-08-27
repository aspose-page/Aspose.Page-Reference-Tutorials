---
date: 2026-03-29
description: Apprenez à ajouter des objets transparents aux documents XPS, puis à
  exporter XPS en PDF à l'aide d'Aspose.Page pour .NET. Guide étape par étape avec
  des conseils pratiques.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Exporter XPS en PDF – Ajouter un objet transparent avec Aspose.Page
url: /fr/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exporter XPS en PDF – Ajouter un objet transparent avec Aspose.Page

## Introduction

Dans ce tutoriel, vous apprendrez comment ajouter des objets transparents à un document XPS puis **exporter XPS en PDF** avec Aspose.Page pour .NET. La transparence peut rendre vos documents plus modernes et vous aider à mettre en évidence des informations importantes. Nous parcourrons chaque étape, expliquerons la logique du code et vous montrerons comment terminer le flux de travail en convertissant le fichier XPS en PDF pour un partage facile.

## Réponses rapides
- **Que signifie « exporter XPS en PDF » ?** Conversion d'un fichier XPS en fichier PDF tout en préservant la mise en page, les couleurs et la transparence.  
- **Pourquoi ajouter la transparence d'abord ?** Les objets transparents vous permettent de créer des graphiques en couches qui ont fière allure dans le PDF final.  
- **Ai-je besoin d'une licence ?** Oui, une licence valide d'Aspose.Page est requise pour une utilisation en production.  
- **Cette fonctionnalité fonctionne-t-elle sur .NET Core ?** Absolument – Aspose.Page prend en charge .NET Core, .NET 5/6 et le framework .NET complet.  
- **Où puis‑je trouver plus d'exemples ?** Consultez la documentation Aspose.Page et le forum communautaire ci‑dessous.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d'avoir les prérequis suivants en place :

- Aspose.Page for .NET : Assurez‑vous d'avoir la bibliothèque Aspose.Page pour .NET installée. Vous pouvez la télécharger depuis [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Importer les espaces de noms

Pour commencer, incluez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Maintenant, poursuivons avec le guide étape par étape.

## Étape 1 : Créer un nouveau document XPS

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Ce code initialise un nouveau document XPS en utilisant Aspose.Page pour .NET.

## Étape 2 : Démontrer la transparence

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Ces lignes créent deux chemins gris qui serviront de fond pour les formes transparentes que nous ajouterons plus tard.

## Étape 3 : Créer un chemin avec une géométrie de rectangle fermé

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Ici, nous créons un rectangle bleu. Comme nous modifierons plus tard son opacité, le rectangle apparaîtra semi‑transparent dans le PDF final.

## Étape 4 : Manipuler les chemins et les couleurs

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Nous clonons le premier rectangle, l'ajoutons à la page et changeons sa couleur de remplissage en vert. Cela montre à quel point il est facile de réutiliser une géométrie existante.

## Étape 5 : Cloner et transformer les chemins

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Le chemin cloné est déplacé de 300 unités vers le bas et peint en rouge, vous offrant un effet de superposition en couches.

## Étape 6 : Répéter et modifier les chemins

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Nous réutilisons les données de géométrie de `path2`, les déplaçons vers la droite et appliquons à nouveau un remplissage bleu.

## Étape 7 : Gérer l'opacité

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Définir la propriété `Opacity` à 0,8 rend ce rectangle opaque à 80 %, illustrant comment vous pouvez ajuster finement la transparence de chaque élément.

## Étape 8 : Enregistrer le document XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Le fichier XPS est maintenant enregistré avec tous les objets transparents appliqués.  

**Exportation en PDF :** Pour **exporter XPS en PDF**, appelez simplement `doc.Save` à nouveau avec une extension `.pdf`, par exemple `doc.Save(dataDir + "TransparentDocument.pdf");`. La même fidélité visuelle, y compris les réglages d'opacité, est conservée dans le PDF résultant.

## Pourquoi exporter XPS en PDF après avoir ajouté de la transparence ?

- **Compatibilité universelle :** Le PDF est largement supporté sur toutes les plateformes, tandis que le XPS est plus niche.  
- **Effets visuels préservés :** Aspose.Page conserve la transparence, les dégradés et les transformations matricielles intacts pendant la conversion.  
- **Partage facile :** Les PDF peuvent être ouverts dans les navigateurs, les appareils mobiles et de nombreux lecteurs tiers sans plugins supplémentaires.

## Cas d'utilisation courants

- **Brochures marketing** où les graphiques en couches offrent une impression premium.  
- **Diagrammes techniques** qui nécessitent des sections mises en évidence sans encombrer la mise en page.  
- **Génération de rapports** où vous souhaitez superposer des filigranes ou des logos avec une opacité partielle.

## Astuces et pièges

- **Conseil pro :** Toujours définir la valeur `Opacity` entre 0 et 1. Les valeurs en dehors de cet intervalle sont limitées et peuvent produire des résultats inattendus.  
- **Astuce de performance :** Réutiliser la géométrie (`path2.Data`) réduit l'utilisation de la mémoire lorsque vous avez besoin de nombreuses formes similaires.  
- **Écueil :** Enregistrer directement en PDF après avoir ajouté de la transparence fonctionne immédiatement, mais si vous modifiez plus tard le PDF avec d'autres outils, certains visionneurs plus anciens peuvent ne pas rendre correctement l'opacité.

## Conclusion

Ajouter des objets transparents aux documents XPS en utilisant Aspose.Page pour .NET offre une méthode polyvalente pour améliorer les présentations visuelles. Une fois que votre fichier XPS a l'apparence souhaitée, vous pouvez **exporter XPS en PDF** en une seule ligne de code, préservant tous les effets de transparence pour une large diffusion.

## FAQ

### Q1 : Puis‑je appliquer la transparence à n'importe quel objet dans un document XPS ?

R1 : Oui, la transparence peut être appliquée à divers objets tels que les chemins, les formes et les images dans un document XPS.

### Q2 : Comment puis‑je ajuster l'opacité d'un élément spécifique ?

R2 : Vous pouvez définir la propriété d'opacité du remplissage (Fill) ou du contour (Stroke) pour ajuster la transparence d'un élément spécifique.

### Q3 : Aspose.Page est‑il compatible avec .NET Core ?

R3 : Oui, Aspose.Page prend en charge .NET Core, permettant le développement multiplateforme.

### Q4 : Puis‑je exporter des documents XPS vers d'autres formats avec Aspose.Page ?

R4 : Aspose.Page offre la fonctionnalité d'exporter des documents XPS vers divers formats, y compris le PDF et les images.

### Q5 : Où puis‑je trouver un support supplémentaire et des discussions communautaires ?

R5 : Pour un support supplémentaire et des discussions communautaires, consultez le [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6 : La conversion PDF conserve‑t‑elle mes paramètres de transparence ?

R6 : Absolument. Lorsque vous exportez XPS en PDF avec Aspose.Page, tous les paramètres d'opacité et de fusion sont conservés.

### Q7 : Puis‑je traiter par lots plusieurs fichiers XPS en PDF ?

R7 : Oui, vous pouvez parcourir une collection de fichiers XPS et appeler `doc.Save(...".pdf")` pour chacun, automatisant les conversions en masse.

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** Aspose.Page 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}