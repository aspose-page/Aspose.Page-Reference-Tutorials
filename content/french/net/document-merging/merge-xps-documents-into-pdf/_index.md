---
title: Fusionner des documents XPS en PDF avec Aspose.Page pour .NET
linktitle: Fusionner des documents XPS en PDF
second_title: API Aspose.Page .NET
description: Fusionnez sans effort des documents XPS dans des PDF de haute qualité à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour une expérience de conversion de documents fluide.
type: docs
weight: 11
url: /fr/net/document-merging/merge-xps-documents-into-pdf/
---
## Introduction

Dans le paysage en constante évolution du traitement des documents, Aspose.Page pour .NET apparaît comme un outil puissant pour fusionner de manière transparente des documents XPS au format PDF. Ce didacticiel vous guidera tout au long du processus, en décomposant chaque étape pour garantir une exécution fluide et efficace.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).

- Fichiers de documents : ayez le document XPS (`input.xps`) prêt dans votre répertoire spécifié.

## Importer des espaces de noms

Dans votre projet .NET, incluez les espaces de noms nécessaires pour travailler avec Aspose.Page :

```csharp
using Aspose.Page.XPS;
```

Cette étape garantit que vous avez accès aux classes et méthodes requises pour la conversion du document.

## Étape 1 : initialiser les flux

```csharp
// ExDébut : 3
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Initialiser le flux de sortie PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialiser le flux d'entrée XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExFin : 3
```

Cette étape implique la configuration des flux d'entrée et de sortie pour les fichiers XPS et PDF. Assurez-vous que les chemins et noms de fichiers corrects sont utilisés.

## Étape 2 : Charger le document XPS

```csharp
// ExDébut : 4
// Charger le document XPS à partir du flux
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// ou chargez le document XPS directement à partir du fichier. Aucun xpsStream n’est alors nécessaire.
//Document XpsDocument = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExFin : 4
```

 Ici, nous chargeons le document XPS dans le`XpsDocument` objet, le préparant pour un traitement ultérieur.

## Étape 3 : initialiser les options de sauvegarde

```csharp
// ExDébut : 5
// Initialisez l'objet d'options avec les paramètres nécessaires.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExFin : 5
```

 Personnalisez le`PdfSaveOptions` objet en fonction de vos préférences, en spécifiant des paramètres tels que la compression d’image, la compression de texte et les numéros de page.

## Étape 4 : Créer un périphérique de rendu

```csharp
// ExDébut : 6
// Créer un périphérique de rendu pour le format PDF
PdfDevice device = new PdfDevice(pdfStream);
// ExFin : 6
```

 Le`PdfDevice` est l'outil responsable du rendu du document XPS au format PDF.

## Étape 5 : Enregistrez le document

```csharp
// ExDébut : 7
document.Save(device, options);
// ExFin : 7
```

Enfin, enregistrez le document à l'aide du périphérique de rendu et des options spécifiées.

## Conclusion

Toutes nos félicitations! Vous avez réussi à fusionner des documents XPS en PDF à l'aide d'Aspose.Page pour .NET. Ce processus transparent garantit la préservation de la qualité et du formatage des documents.

## FAQ

### Q1 : Puis-je fusionner plusieurs fichiers XPS en un seul PDF ?

 A1 : Oui, vous pouvez. Ajustez simplement le`PageNumbers` paramètre dans le`PdfSaveOptions` pour inclure les pages souhaitées à partir de différents fichiers XPS.

### Q2 : Une licence temporaire est-elle disponible pour Aspose.Page pour .NET ?

 A2 : Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) à des fins de tests.

### Q3 : Existe-t-il des limitations sur la taille du fichier lors de l'utilisation d'Aspose.Page pour la conversion de documents ?

A3 : Aspose.Page pour .NET n'impose pas de limitations strictes sur la taille des fichiers, mais des performances optimales sont obtenues avec des tailles de fichiers raisonnables.

### Q4 : Puis-je personnaliser davantage le PDF de sortie, par exemple en ajoutant des filigranes ou des annotations ?

A4 : Oui, Aspose.Page pour .NET fournit des fonctionnalités étendues pour la manipulation de PDF. Consultez la documentation pour connaître les options de personnalisation avancées.

### Q5 : Aspose.Page pour .NET prend-il en charge le développement multiplateforme ?

A5 : Oui, Aspose.Page pour .NET est conçu pour fonctionner de manière transparente sur diverses plates-formes.