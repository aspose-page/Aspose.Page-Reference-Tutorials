---
title: Ajoutez des propriétés simples avec Aspose.Page pour .NET
linktitle: Ajouter des propriétés simples
second_title: API Aspose.Page .NET
description: Améliorez les fichiers EPS avec Aspose.Page pour .NET. Ajoutez facilement des propriétés simples pour des métadonnées de document personnalisées.
type: docs
weight: 14
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Introduction

Dans le domaine de la manipulation et de l'amélioration de documents, Aspose.Page pour .NET apparaît comme un outil puissant, offrant aux développeurs la possibilité d'ajouter et de modifier de manière transparente des métadonnées XMP dans des fichiers EPS. Ce didacticiel vous guidera tout au long du processus d'ajout de propriétés simples à un fichier EPS à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Aspose.Page pour .NET : assurez-vous qu'Aspose.Page pour .NET est installé dans votre environnement de développement. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

2.  Répertoire de documents : configurez un répertoire pour stocker vos fichiers EPS. Mettre à jour le`dataDir` variable dans l'extrait de code fourni avec le chemin d'accès à votre répertoire de documents.

## Importer des espaces de noms

Pour commencer, importez les espaces de noms nécessaires pour activer la communication avec Aspose.Page for .NET. Ajoutez les lignes suivantes au début de votre fichier de code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Étape 1 : initialiser le flux d'entrée du fichier EPS

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Initialiser le flux d'entrée du fichier EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Créer une instance PsDocument à partir du flux
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : Obtenez les métadonnées XMP

```csharp
// Obtenez les métadonnées XMP. Si le fichier EPS ne contient pas de métadonnées XMP, nous en obtenons une nouvelle remplie de valeurs provenant des commentaires de métadonnées PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Étape 3 : modifier les valeurs des métadonnées XMP

```csharp
// Modifier les valeurs des métadonnées XMP
DateTime now = DateTime.UtcNow;

// Ajouter une propriété Integer
xmp.Add("xmp:Intg1", new XmpValue(111));

// Ajouter une propriété DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Ajouter une propriété Double
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Ajouter une propriété String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Étape 4 : Enregistrez le fichier EPS avec les métadonnées XMP modifiées

```csharp
// Enregistrer le fichier EPS avec les métadonnées XMP modifiées

// Créer un flux de sortie
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Enregistrer le fichier EPS
    document.Save(outPsStream);
}
```

## Étape 5 : Fermez FileStream

```csharp
finally
{
    psStream.Close();
}
```

En suivant ces étapes, vous pouvez facilement incorporer des propriétés simples dans vos fichiers EPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

En conclusion, Aspose.Page pour .NET s'avère être un atout inestimable pour les développeurs cherchant à améliorer les fichiers EPS avec des métadonnées XMP personnalisées. En ajoutant des propriétés simples, vous pouvez personnaliser et enrichir vos documents pour répondre à des exigences spécifiques, ouvrant ainsi un monde de possibilités de manipulation de documents.

## FAQ

### Q1 : Aspose.Page pour .NET est-il compatible avec tous les fichiers EPS ?

A1 : Aspose.Page pour .NET prend en charge une large gamme de fichiers EPS. Cependant, la compatibilité peut varier en fonction de la complexité et de la structure des fichiers individuels.

### Q2 : Puis-je modifier les métadonnées XMP existantes avec Aspose.Page pour .NET ?

A2 : Absolument ! Comme démontré dans ce didacticiel, vous pouvez facilement modifier les valeurs de métadonnées XMP existantes ou en ajouter de nouvelles en fonction de vos besoins.

### Q3 : Y a-t-il des limites aux types de propriétés que je peux ajouter ?

A3 : Aspose.Page pour .NET prend en charge différents types de données pour les propriétés, notamment les entiers, les dates, les doubles et les chaînes. Vous avez la flexibilité de choisir le type approprié pour vos métadonnées.

### Q4 : Comment puis-je obtenir une assistance technique pour Aspose.Page pour .NET ?

 A4 : Pour une assistance technique, visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) ou explorez le[Documentation](https://reference.aspose.com/page/net/) pour des conseils complets.

### Q5 : Existe-t-il un essai gratuit disponible pour Aspose.Page pour .NET ?

 A5 : Oui, vous pouvez accéder à un essai gratuit[ici](https://releases.aspose.com/).