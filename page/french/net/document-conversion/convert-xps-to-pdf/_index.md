---
title: Convertir XPS en PDF avec Aspose.Page pour .NET
linktitle: Convertir XPS en PDF
second_title: API Aspose.Page .NET
description: Convertissez sans effort XPS en PDF dans .NET avec Aspose.Page. Téléchargez la bibliothèque, explorez la documentation et bénéficiez d'un essai gratuit.
weight: 11
url: /fr/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS en PDF avec Aspose.Page pour .NET

## Introduction

Dans ce didacticiel, nous approfondirons le processus de conversion de documents XPS (XML Paper Spécification) en PDF (Portable Document Format) à l'aide de la puissante bibliothèque Aspose.Page pour .NET. Aspose.Page pour .NET fournit un ensemble robuste de fonctionnalités pour travailler avec des fichiers XPS, permettant aux développeurs de les convertir de manière transparente au format PDF avec diverses options de personnalisation.

## Conditions préalables

Avant de nous lancer dans ce voyage de conversion, assurez-vous d'avoir les conditions préalables suivantes en place :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez le télécharger depuis le[Documentation Aspose.Page](https://reference.aspose.com/page/net/).

- Environnement de développement : configurez un environnement de développement .NET avec Visual Studio ou tout autre IDE compatible.

- Document XPS : préparez le document XPS que vous souhaitez convertir en PDF. Il peut s'agir de votre exemple de fichier XPS stocké dans un répertoire désigné.

## Importer des espaces de noms

Avant de plonger dans le code, importons les espaces de noms nécessaires pour rendre les fonctionnalités Aspose.Page for .NET accessibles dans notre code :

```csharp
using Aspose.Page.XPS;
```

## Étape 1 : initialiser le répertoire de documents

```csharp
string dataDir = "Your Document Directory";
```

Remplacez « Votre répertoire de documents » par le chemin d'accès au répertoire contenant votre document XPS.

## Étape 2 : initialiser les flux PDF et XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Ouvrez les flux pour le fichier PDF de sortie et le fichier XPS d'entrée. Assurez-vous que les chemins de fichiers appropriés sont définis.

## Étape 3 : Charger le document XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Chargez le document XPS à l'aide de la bibliothèque Aspose.Page for .NET.

## Étape 4 : initialiser les options d'enregistrement PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Configurez les options d'enregistrement PDF, y compris les paramètres tels que le niveau de qualité JPEG, la compression d'image, la compression de texte et les numéros de page spécifiques à inclure.

## Étape 5 : Créer un périphérique de rendu PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Créez un périphérique de rendu pour le format PDF à l'aide de la bibliothèque Aspose.Page for .NET.

## Étape 6 : Enregistrer le document au format PDF

```csharp
document.Save(device, options);
```

Enregistrez le document XPS au format PDF à l'aide du périphérique de rendu et des options spécifiés.

## Conclusion

Toutes nos félicitations! Vous avez converti avec succès un document XPS en PDF à l'aide d'Aspose.Page pour .NET. Cette bibliothèque polyvalente offre aux développeurs un ensemble d'outils puissants pour gérer sans effort différents formats de documents.

## FAQ

### Q1 : Puis-je convertir plusieurs fichiers XPS en un seul PDF à l'aide d'Aspose.Page pour .NET ?

A1 : Oui, vous pouvez parcourir plusieurs fichiers XPS et suivre les mêmes étapes pour les fusionner en un seul PDF.

### Q2 : Existe-t-il d'autres formats de sortie pris en charge par Aspose.Page pour .NET ?

R2 : Oui, Aspose.Page pour .NET prend en charge divers formats de sortie, notamment TIFF, JPEG, PNG, etc.

### Q3 : Comment puis-je personnaliser l'apparence du document PDF converti ?

A3 : Vous pouvez modifier les paramètres de l'objet d'options, tels que la compression d'image et la compression de texte, pour obtenir l'apparence souhaitée.

### Q4 : Existe-t-il une version d’essai disponible pour Aspose.Page pour .NET ?

 A4 : Oui, vous pouvez explorer les capacités d'Aspose.Page pour .NET en obtenant un essai gratuit auprès de[ici](https://releases.aspose.com/).

### Q5 : Où puis-je obtenir une assistance communautaire pour Aspose.Page pour .NET ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour les discussions et le soutien de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
