---
date: 2026-03-21
description: Apprenez à remplir du texte et à ajouter du texte aux documents PS à
  l'aide d'Aspose.Page pour .NET. Guide étape par étape avec des exemples de code.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Comment remplir du texte dans les documents PostScript (PS) avec Aspose.Page
url: /fr/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment remplir du texte dans des documents PostScript (PS) avec Aspose.Page

## Introduction

Si vous devez **remplir du texte** à l’intérieur d’un fichier PostScript (PS), Aspose.Page pour .NET rend cela simple. Que vous génériez des rapports, des factures ou des graphiques personnalisés, ajouter et styliser du texte est une exigence fondamentale. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration de l’environnement à l’enregistrement du document PS final — afin que vous puissiez ajouter du texte aux fichiers PS dans vos applications .NET en toute confiance.

## Réponses rapides
- **Que signifie « remplir du texte » ?** Il rend les caractères à l’aide d’un pinceau plein, peignant les glyphes directement sur la page.  
- **Puis‑je utiliser des polices personnalisées ?** Oui — Aspose.Page prend en charge les polices personnalisées via la fonctionnalité `add custom font ps`.  
- **Comment enregistrer le document PS ?** Appelez `document.Save()` après avoir fermé la page ; cela écrit le fichier sur le disque (`save ps document`).  
- **Le « fill and stroke text » est‑il supporté ?** Absolument ; utilisez `FillAndStrokeText` pour appliquer à la fois le remplissage et le contour.  
- **Quelles versions de .NET sont requises ?** Toute version .NET Framework 4.5+ ou .NET Core/5/6+.

## Qu’est‑ce que « how to fill text » dans un document PS ?

Remplir du texte signifie peindre les caractères avec une couleur unie (ou un pinceau) sans contour. En PostScript, cela correspond à l’opérateur `fill`. Aspose.Page abstrait cela en méthodes faciles à utiliser comme `FillText` et `FillAndStrokeText`.

## Pourquoi utiliser Aspose.Page pour ajouter une police personnalisée ps ?

- **Prise en charge complète des polices** – les polices système et les polices TrueType/OpenType externes fonctionnent immédiatement.  
- **Positionnement précis** – vous contrôlez les coordonnées X/Y, la taille et le style.  
- **Stylisation riche** – combinez remplissages, contours et stylos pour des effets tels que « fill and stroke text ».  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS avec la même API.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Aspose.Page pour .NET** – téléchargez la bibliothèque depuis la [documentation Aspose.Page .NET](https://reference.aspose.com/page/net/).  
- **Répertoire de documents** – un dossier sur votre machine où les fichiers PS source et de sortie seront stockés (désigné comme *Your Document Directory* dans le code).  
- **Dossier de polices** – un sous‑dossier contenant toutes les polices personnalisées que vous prévoyez d’utiliser.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin que le compilateur sache où trouver les classes que nous allons utiliser :

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Guide étape par étape

### Étape 1 : Créer le flux de sortie pour le document PS  

Nous ouvrons un `FileStream` qui contiendra le fichier PS généré, configurons `PsSaveOptions` pour pointer vers notre dossier de polices personnalisées, et instancions un `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Astuce :** Conservez le bloc `using` pour garantir que le flux est fermé automatiquement, ce qui finalise également le fichier PS (`save ps document`).

### Étape 2 : Remplir du texte avec une police système  

Ici nous démontrons l’opération de base **how to fill text** en utilisant la police intégrée *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Étape 3 : Remplir du texte avec une police personnalisée  

Si vous avez besoin d’un rendu spécifique, chargez une police personnalisée depuis le dossier de polices avec `ExternalFontCache.FetchDrFont`. Cela satisfait l’exigence **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Étape 4 : Contour (stroke) du texte avec une police système  

Le contour trace le périmètre du glyphe. Combinez‑le avec un remplissage pour obtenir un effet « fill and stroke ».

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Pourquoi c’est important :** L’appel `FillAndStrokeText` montre comment **fill and stroke text** en une seule étape, vous offrant un contrôle typographique plus riche.

### Étape 5 : Contour du texte avec une police personnalisée  

La même technique de contour fonctionne avec n’importe quelle police personnalisée que vous avez chargée.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Étape 6 : Fermer la page et enregistrer le document  

Terminer est simple : fermez la page courante et invoquez `Save()` pour écrire le fichier PS sur le disque.

```csharp
document.ClosePage();
document.Save();
}
```

> **Résultat :** Vous trouverez `AddText_outPS.ps` dans *Your Document Directory*, contenant à la fois du texte rempli et contourné rendu avec les polices système et personnalisées.

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Police personnalisée introuvable** | Vérifiez que le fichier de police (.ttf/.otf) existe dans le dossier référencé par `AdditionalFontsFolders`. |
| **Le texte apparaît à la mauvaise position** | Ajustez les coordonnées X/Y passées à `FillText`/`OutlineText`. N’oubliez pas que PostScript utilise des points (1/72 pouce). |
| **Les couleurs diffèrent** | Assurez‑vous d’utiliser `SolidBrush` ou `Pen` avec les valeurs `Color` correctes. |
| **Le document ne s’enregistre pas** | Confirmez que le bloc `using` se termine sans exception et que l’application possède les droits d’écriture sur le dossier cible. |

## Foire aux questions

**Q : Puis‑je utiliser Aspose.Page avec d’autres bibliothèques .NET ?**  
R : Oui, Aspose.Page s’intègre facilement avec d’autres composants .NET, vous permettant de combiner des bibliothèques PDF, image ou graphique dans la même solution.

**Q : Les polices personnalisées sont‑elles indispensables pour ce processus ?**  
R : Bien que les polices système fonctionnent correctement, les polices personnalisées vous offrent une liberté de conception totale et sont utiles lorsque la typographie propre à une marque est requise.

**Q : Aspose.Page convient‑il au traitement de documents à grande échelle ?**  
R : Absolument. La bibliothèque est optimisée pour les scénarios à haut débit et peut gérer des milliers de fichiers PS efficacement.

**Q : Puis‑je modifier la position du texte dans le document PS ?**  
R : Certainement — modifiez simplement les valeurs numériques X/Y dans les appels `FillText` ou `OutlineText`.

**Q : Où puis‑je obtenir de l’aide pour les questions liées à Aspose.Page ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour rejoindre la communauté et obtenir de l’assistance experte.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-21  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose