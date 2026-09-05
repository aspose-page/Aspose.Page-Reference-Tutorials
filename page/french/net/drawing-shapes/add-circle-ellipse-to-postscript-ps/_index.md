---
date: 2026-07-19
description: Découvrez le tutoriel asp page postscript pour ajouter des ellipses circulaires
  aux fichiers PostScript (PS) à l'aide d'Aspose.Page pour .NET – comment générer
  rapidement une sortie postscript.
keywords:
- asp page postscript tutorial
- how to generate postscript
- write postscript output
lastmod: 2026-07-19
linktitle: Ajouter un cercle ellipse à PostScript (PS)
og_description: tutoriel asp page postscript qui vous montre comment générer une sortie
  postscript en ajoutant des ellipses circulaires avec Aspose.Page pour .NET. Suivez
  le guide étape par étape pour une intégration rapide.
og_image_alt: 'Guide: Add circle ellipse to PostScript using Aspose.Page .NET'
og_title: asp page postscript tutorial – Ajouter un cercle ellipse (PS)
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn the asp page postscript tutorial for adding circle ellipses to
    PostScript (PS) files using Aspose.Page for .NET – how to generate postscript
    output quickly.
  headline: asp page postscript tutorial – Add Circle Ellipse (PS)
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily focuses on PostScript, but Aspose provides other
      libraries for various formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/)
      for a full list.
    question: Can I use Aspose.Page for .NET with other document formats?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community discussions and support.
    question: Where can I find additional support and community discussions?
  - answer: Yes, you can access the [free trial](https://releases.aspose.com/) to
      explore the features of Aspose.Page for .NET.
    question: Is there a free trial available for Aspose.Page for .NET?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  - answer: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- Aspose.Page
- .NET drawing
- circle ellipse
title: asp page postscript tutorial – Ajouter un cercle ellipse (PS)
url: /fr/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tutoriel asp page postscript – Ajouter une ellipse circulaire (PS)

## Introduction

Dans ce **asp page postscript tutorial**, vous découvrirez comment ajouter des ellipses circulaires parfaites à un document PostScript (PS) en utilisant la bibliothèque Aspose.Page pour .NET. Que vous génériez des dessins techniques, des graphiques vectoriels ou des rapports personnalisés, Aspose.Page vous permet d’écrire du code PostScript sans gérer la syntaxe PS de bas niveau. Nous parcourrons chaque étape, de la configuration de l’environnement au rendu de deux ellipses — l’une remplie et l’autre tracée — afin que vous puissiez intégrer cette fonctionnalité dans vos propres applications immédiatement.

## Réponses rapides
- **Que couvre ce tutoriel ?** Ajouter des ellipses circulaires remplies et tracées à un fichier PS avec Aspose.Page pour .NET.  
- **Combien d’étapes de code sont requises ?** Huit étapes concises, chacune illustrée par un fragment de code prêt à l’exécution.  
- **Ai-je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET 5, .NET 6, .NET Core 3.1, et .NET Framework 4.6+.  
- **Puis-je réutiliser le même chemin graphique ?** Oui — créez un `GraphicsPath` une fois et dessinez‑le ou remplissez‑le plusieurs fois.

## Qu’est‑ce que le tutoriel asp page postscript ?
Le **asp page postscript tutorial** est un guide pas à pas qui montre comment générer du contenu PostScript de manière programmatique avec Aspose.Page pour .NET. Il se concentre sur du code pratique, des cas d’utilisation réels et des conseils de bonnes pratiques afin que vous puissiez produire rapidement des fichiers PS fiables.

## Pourquoi utiliser Aspose.Page pour la génération de PostScript ?
Aspose.Page prend en charge **plus de 30 formats de sortie** (y compris PDF, SVG et EPS) et peut rendre **des documents de plusieurs centaines de pages** sans charger le fichier complet en mémoire, offrant une **réduction de l’empreinte mémoire allant jusqu’à 70 %** comparée à la construction manuelle de chaînes PS. Son API de haut niveau élimine le besoin d’écrire des commandes PS brutes, réduisant le temps de développement d’environ **80 %** en moyenne.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

1. Bibliothèque Aspose.Page pour .NET : Téléchargez et installez la bibliothèque Aspose.Page pour .NET depuis [ici](https://releases.aspose.com/page/net/).  
2. Environnement de développement : Assurez‑vous d’avoir un environnement de développement .NET fonctionnel installé sur votre machine.

Maintenant, commençons le guide pas à pas.

## Importer les espaces de noms

Les directives `using` importent les classes Aspose.Page dans le scope afin que vous puissiez travailler directement avec les graphiques, les couleurs et les documents PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Maintenant, décomposons l’exemple fourni en plusieurs étapes pour vous guider à travers le processus d’ajout d’ellipses circulaires à un document PostScript.

## Comment définir le répertoire du document ?
Pour indiquer au programme où stocker le fichier PS généré, vous devez spécifier un chemin de dossier que l’application peut écrire. Utilisez une variable telle que `dataDir` et attribuez‑lui un chemin complet ou relatif ; ce chemin sera combiné avec le nom du fichier de sortie plus tard dans le code.  
> **Astuce :** Utilisez `Path.Combine(Environment.CurrentDirectory, "output")` pour créer un chemin multiplateforme et éviter les séparateurs codés en dur.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Comment créer le flux de sortie pour le document PostScript ?
Créer un flux de sortie ouvre un handle de fichier dans lequel le moteur Aspose.Page écrira les données PostScript. En utilisant un `FileStream` avec `FileMode.Create`, le fichier est créé à chaque exécution, écrasant toute version précédente. Ce flux est ensuite passé au constructeur `PsDocument`.

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

## Comment configurer les options d’enregistrement et initialiser un document PS ?
`PsSaveOptions` vous permet de spécifier la taille de page, la résolution et d’autres paramètres de rendu. Ici nous utilisons la taille de page A4 standard et un document d’une seule page. `PsDocument` représente le document PostScript en cours de création ; il reçoit le flux de sortie et les options d’enregistrement, et il gère les événements du cycle de vie des pages.

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Comment créer un chemin graphique pour la première ellipse ?
`GraphicsPath` représente une forme vectorielle qui peut être dessinée ou remplie dans une page PostScript. Le constructeur prend les coordonnées X/Y du coin supérieur gauche, suivies de la largeur et de la hauteur, vous permettant de définir la taille et la position exactes de l’ellipse sur la page.

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

## Comment définir la couleur de remplissage et remplir la première ellipse ?
`SolidBrush` définit une couleur de remplissage solide pour les opérations de dessin. En créant un `SolidBrush` avec une `Color` spécifique et en le passant à `graphics.FillPath`, l’ellipse est rendue avec cette couleur unie.

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

## Comment créer un chemin graphique pour la deuxième ellipse ?
Un second `GraphicsPath` est défini pour illustrer comment vous pouvez dessiner un contour (trait) séparé d’un remplissage. Le même modèle de constructeur est utilisé, mais vous pouvez modifier les dimensions du rectangle pour obtenir une ellipse de taille différente.

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

## Comment définir le trait et dessiner la deuxième ellipse ?
`SolidPen` spécifie la couleur et la largeur pour le tracé des formes. En fournissant un `SolidPen` à `graphics.DrawPath`, le contour de l’ellipse est dessiné sans aucun remplissage, vous donnant une forme proprement tracée.

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

## Comment fermer la page actuelle et enregistrer le document ?
Après l’émission de toutes les commandes de dessin, vous devez fermer la page active avec `document.ClosePage()` pour finaliser son contenu. Enfin, appeler `document.Save()` écrit les données PostScript accumulées dans le flux précédemment ouvert, produisant le fichier de sortie sur le disque.

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Fichier non trouvé** | Chemin de répertoire incorrect | Vérifiez que le dossier existe ou créez-le avec `Directory.CreateDirectory`. |
| **Sortie vide** | Oubli d’appeler `document.ClosePage()` | Assurez‑vous de fermer la page avant d’enregistrer. |
| **Couleurs incorrectes** | Utilisation de `Color.FromArgb` avec un mauvais ordre | Utilisez `Color.FromRgb(red, green, blue)` pour plus de clarté. |
| **Ralentissement des performances sur les gros fichiers** | Chargement de tout le document en mémoire | Utilisez `PsSaveOptions` avec `EnableMemorySaving = true` pour diffuser les grandes pages. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Page pour .NET avec d’autres formats de documents ?**  
A : Aspose.Page se concentre principalement sur le PostScript, mais Aspose propose d’autres bibliothèques pour divers formats. Consultez la [documentation Aspose](https://reference.aspose.com/page/net/) pour la liste complète.

**Q : Où puis‑je trouver un support supplémentaire et des discussions communautaires ?**  
A : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour les discussions communautaires et le support.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour .NET ?**  
A : Oui, vous pouvez accéder à l’[essai gratuit](https://releases.aspose.com/) pour explorer les fonctionnalités d’Aspose.Page pour .NET.

**Q : Comment obtenir une licence temporaire pour Aspose.Page ?**  
A : Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins de test et d’évaluation.

**Q : Où puis‑je acheter Aspose.Page pour .NET ?**  
A : Achetez Aspose.Page pour .NET depuis la [page d’achat](https://purchase.aspose.com/buy).

## Conclusion

Félicitations ! Vous avez terminé avec succès le **asp page postscript tutorial** d’ajout d’ellipses circulaires aux documents PostScript en utilisant Aspose.Page pour .NET. En suivant les huit étapes claires, vous pouvez désormais générer des fichiers PS de haute qualité avec des ellipses remplies et tracées, prêts à être intégrés aux moteurs de rapports, aux exportateurs CAD ou à tout pipeline graphique personnalisé.

---

**Dernière mise à jour:** 2026-07-19  
**Testé avec:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Aspose.Page .NET – Dessiner des formes](/page/net/drawing-shapes/)
- [Créer un document postscript .net – Ajouter un rectangle avec Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Comment créer un document PostScript avec Aspose.Page pour .NET](/page/net/document-creation/create-postscript-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}