---
date: 2026-03-21
description: Apprenez à créer un document PostScript en C# avec du texte Unicode en
  utilisant Aspose.Page pour .NET – une méthode rapide pour améliorer la manipulation
  de documents.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Créer un document PostScript en C# avec du texte Unicode – Aspose.Page
url: /fr/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter du texte avec une chaîne Unicode à PostScript (PS) avec Aspose.Page

## Introduction

Si vous devez **créer un document PostScript C#** et intégrer des caractères Unicode, Aspose.Page pour .NET rend le processus simple. Dans ce tutoriel, nous parcourrons un exemple complet et pratique qui montre comment ajouter du texte japonais (ou toute chaîne Unicode) à un fichier PS, choisir une police personnalisée et enregistrer le résultat. À la fin, vous disposerez d’un extrait réutilisable que vous pourrez insérer dans n’importe quel projet C#.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Ajout de texte Unicode à un fichier PostScript à l'aide d'Aspose.Page en C#.
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET (dernière version).
- **Ai-je besoin d’une police spéciale ?** Toute police TrueType/OpenType qui prend en charge la plage Unicode souhaitée, par ex., *Arial Unicode MS*.
- **Combien de lignes de code ?** Environ 30 lignes, réparties en étapes claires.
- **Une licence est‑elle nécessaire ?** Une licence temporaire suffit pour l'évaluation ; une licence complète est requise pour la production.

## Qu’est‑ce que “create postscript document c#” ?
Créer un document PostScript en C# signifie générer de façon programmatique un fichier .ps qui respecte les spécifications du langage PostScript. Aspose.Page abstrait les détails de bas niveau, vous permettant de vous concentrer sur le contenu tel que le texte, les graphiques et les polices.

## Pourquoi utiliser Aspose.Page pour le texte Unicode ?
- **Full Unicode support** – rendre les caractères de n’importe quelle langue sans encodage manuel.
- **Device‑independent** – le même code fonctionne pour les sorties PS, EPS et PDF.
- **No external dependencies** – la bibliothèque gère le chargement des polices et le mappage des glyphes en interne.

## Prérequis

- Familiarité de base avec C# et le développement .NET.
- Bibliothèque Aspose.Page pour .NET installée. Vous pouvez la télécharger depuis la [documentation Aspose.Page pour .NET](https://reference.aspose.com/page/net/).
- Un dossier contenant les polices que vous prévoyez d’utiliser (par ex., *Arial Unicode MS*).

## Importer les espaces de noms

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Configurer le répertoire du document et le dossier des polices

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Étape 2 : Créer le flux de sortie pour le document PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Étape 3 : Ajouter du texte Unicode avec une police personnalisée

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Étape 4 : Fermer la page actuelle

```csharp
document.ClosePage();
```

## Étape 5 : Finaliser et enregistrer le document

```csharp
document.Save();
```

## Problèmes courants et solutions

- **Font not found** – Assurez‑vous que le chemin `AdditionalFontsFolders` pointe vers le dossier contenant les fichiers .ttf/.otf et que le nom de la police correspond exactement.
- **Garbage characters** – Vérifiez que la chaîne source est encodée en UTF‑8 dans votre fichier source C# (utilisez `#pragma warning disable 1591` si nécessaire).
- **File not created** – Vérifiez les permissions d’écriture sur `dataDir` et que le flux est correctement libéré (le bloc `using` s’en charge).

## Questions fréquentes

**Q: Puis‑je utiliser Aspose.Page pour .NET avec d’autres langages de programmation ?**  
A: Aspose.Page est principalement conçu pour .NET, mais des équivalents Java sont disponibles.

**Q: Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?**  
A: Visitez [Temporary License](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire.

**Q: Existe‑t‑il un forum communautaire pour les discussions sur Aspose.Page ?**  
A: Oui, visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

**Q: Quels formats Aspose.Page pour .NET peut‑il gérer ?**  
A: Aspose.Page prend en charge divers formats, dont XPS, PS, EPS, PDF, et plus encore.

**Q: Puis‑je personnaliser l’apparence du texte ajouté ?**  
A: Oui, vous pouvez personnaliser la police, la taille, la couleur et d’autres propriétés du texte dans Aspose.Page.

## Conclusion

Dans ce tutoriel, nous avons démontré comment **créer un document PostScript C#** et intégrer du texte Unicode à l’aide d’Aspose.Page. En suivant les étapes ci‑dessus, vous pouvez rapidement intégrer le rendu de texte multilingue dans n’importe quelle application .NET, vous offrant un contrôle total sur la génération et la mise en page du document.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}