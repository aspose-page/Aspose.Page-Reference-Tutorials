---
title: Ajouter du texte avec une chaîne Unicode au document XPS avec Aspose.Page
linktitle: Ajouter du texte avec une chaîne Unicode au document XPS
second_title: API Aspose.Page .NET
description: Découvrez la puissance d'Aspose.Page pour .NET avec notre guide étape par étape sur l'ajout de texte Unicode aux documents XPS.
type: docs
weight: 12
url: /fr/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Introduction

Dans le paysage en constante évolution du développement .NET, Aspose.Page se distingue comme un outil puissant pour gérer les documents XPS. Parmi ses nombreuses fonctionnalités, la possibilité d'ajouter du texte avec des chaînes Unicode à un document XPS est une fonctionnalité précieuse. Ce guide étape par étape vous guidera tout au long du processus, garantissant que vous exploitez efficacement cette fonctionnalité.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Une compréhension de base du développement .NET.
- Visual Studio installé sur votre ordinateur.
-  Aspose.Page pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).

## Importer des espaces de noms

Pour commencer, assurez-vous d'importer les espaces de noms nécessaires dans votre projet. Cela fournira les classes et fonctionnalités requises pour travailler avec Aspose.Page. Voici les espaces de noms essentiels :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Configurer le document

Tout d'abord, créez un nouveau document XPS dans lequel vous ajouterez le texte Unicode. Suivez l'extrait de code ci-dessous :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```

## Étape 2 : Ajouter du texte Unicode

Maintenant, ajoutons du texte Unicode au document XPS. Cet exemple utilise la police Arial, définit la taille de la police sur 20 et positionne le texte aux coordonnées (400f, 200f). La chaîne Unicode dans ce cas est "TEN. rof SPX.esopsA". Consultez l'extrait de code ci-dessous :

```csharp
// Ajouter du texte
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Étape 3 : Enregistrez le document

Une fois le texte Unicode ajouté, enregistrez le document XPS résultant. Voici la dernière étape :

```csharp
// Enregistrer le document XPS résultant
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Toutes nos félicitations! Vous avez ajouté avec succès du texte Unicode à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré le processus d'ajout de texte Unicode aux documents XPS à l'aide d'Aspose.Page pour .NET. Cette fonctionnalité ouvre les portes à la création de documents diversifiés et dynamiques dans l'environnement .NET.

## FAQ

### Q1 : Aspose.Page est-il compatible avec les derniers frameworks .NET ?

A1 : Oui, Aspose.Page est régulièrement mis à jour pour garantir la compatibilité avec les derniers frameworks .NET.

### Q2 : Puis-je personnaliser le style et la taille de la police lors de l’ajout de texte ?

A2 : Absolument ! L'exemple de code fourni vous permet de personnaliser facilement le style de police, la taille et d'autres attributs.

### Q3 : Où puis-je trouver de la documentation supplémentaire pour Aspose.Page ?

 A3 : Vous pouvez vous référer à la documentation[ici](https://reference.aspose.com/page/net/) pour des informations complètes et des exemples.

### Q4 : Existe-t-il des ressources gratuites pour démarrer avec Aspose.Page ?

 A4 : Oui, vous pouvez explorer le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien et les discussions de la communauté.

### Q5 : Existe-t-il une version d'essai disponible avant d'effectuer un achat ?

 A5 : Certainement ! Vous pouvez accéder à la version d'essai gratuite[ici](https://releases.aspose.com/) avant de faire un achat.