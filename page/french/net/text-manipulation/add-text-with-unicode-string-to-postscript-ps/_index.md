---
title: Ajouter du texte avec une chaîne Unicode à PostScript (PS) avec Aspose.Page
linktitle: Ajouter du texte avec une chaîne Unicode à PostScript (PS)
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter du texte Unicode aux fichiers PostScript à l'aide d'Aspose.Page pour .NET. Améliorez facilement la manipulation des documents.
weight: 11
url: /fr/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter du texte avec une chaîne Unicode à PostScript (PS) avec Aspose.Page

## Introduction

Dans le domaine de la manipulation de documents, Aspose.Page pour .NET se distingue comme une bibliothèque robuste qui permet aux développeurs de créer, modifier et convertir divers formats de documents. L'une de ses fonctionnalités puissantes est la possibilité d'ajouter du texte à l'aide de chaînes Unicode aux fichiers PostScript (PS). Dans ce didacticiel, nous explorerons un guide étape par étape pour accomplir cette tâche, offrant une expérience transparente aux développeurs travaillant avec Aspose.Page.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

- Une connaissance pratique du langage de programmation C#.
-  Aspose.Page pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis le[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).
- Un environnement de développement mis en place avec les configurations nécessaires.

## Importer des espaces de noms

Dans votre code C#, importez les espaces de noms requis pour utiliser les fonctionnalités Aspose.Page pour .NET :

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : configurer le répertoire de documents et le dossier de polices

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Étape 2 : Créer un flux de sortie pour un document PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Créez des options de sauvegarde au format A4
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Des options supplémentaires peuvent être définies ici)
    
    // Créer un nouveau document PS d'une page
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (D'autres étapes seront expliquées ci-dessous)
    
    // Enregistrez le document
    document.Save();
}
```

## Étape 3 : ajouter du texte Unicode avec une police personnalisée

```csharp
string str = "試してみます.";  // Texte Unicode
int fontSize = 48;

// Utiliser une police personnalisée pour remplir le texte
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Étape 4 : Fermez la page actuelle

```csharp
document.ClosePage();
```

## Étape 5 : finaliser et enregistrer le document

```csharp
document.Save();
```

## Conclusion

Dans ce didacticiel, nous avons parcouru le processus d'ajout de texte Unicode à un document PostScript à l'aide d'Aspose.Page pour .NET. En tirant parti de ses puissantes capacités, les développeurs peuvent améliorer leurs flux de travail de manipulation de documents, garantissant flexibilité et précision.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres langages de programmation ?

A1 : Aspose.Page est principalement conçu pour .NET, mais il existe d'autres versions pour Java disponibles.

### Q2 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A2 : Visite[Permis temporaire](https://purchase.aspose.com/temporary-license/) pour l'obtention d'un permis temporaire.

### Q3 : Existe-t-il un forum communautaire pour les discussions sur Aspose.Page ?

 A3 : Oui, visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien de la communauté.

### Q4 : Avec quels formats Aspose.Page pour .NET peut-il fonctionner ?

A4 : Aspose.Page prend en charge divers formats, notamment XPS, PS, EPS, PDF, etc.

### Q5 : Puis-je personnaliser l’apparence du texte ajouté ?

A5 : Oui, vous pouvez personnaliser la police, la taille, la couleur et d'autres propriétés du texte dans Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
