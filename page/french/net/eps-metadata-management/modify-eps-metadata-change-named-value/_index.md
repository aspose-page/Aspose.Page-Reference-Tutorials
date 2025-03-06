---
title: Modifier la valeur nommée avec Aspose.Page pour .NET
linktitle: Modifier la valeur nommée
second_title: API Aspose.Page .NET
description: Découvrez comment modifier les valeurs nommées dans les fichiers EPS à l'aide d'Aspose.Page pour .NET. Personnalisez facilement les métadonnées XMP pour un traitement de documents sur mesure.
weight: 16
url: /fr/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifier la valeur nommée avec Aspose.Page pour .NET

## Introduction

Dans le monde du traitement de documents, Aspose.Page for .NET s'impose comme un outil puissant de manipulation de fichiers EPS. L'une des fonctionnalités clés qu'il offre est la possibilité de modifier les valeurs nommées dans les métadonnées XMP. Ce didacticiel vous guidera tout au long du processus de modification d'une valeur nommée à l'aide d'Aspose.Page pour .NET, vous permettant de personnaliser vos fichiers EPS en fonction de vos besoins spécifiques.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

- Répertoire de documents : disposez d'un répertoire désigné pour vos fichiers EPS dans lequel vous pouvez effectuer les modifications de valeurs nommées.

## Importer des espaces de noms

Dans votre projet .NET, vous devez importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par Aspose.Page. Ajoutez les espaces de noms suivants à votre code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant, décomposons le code en plusieurs étapes pour une compréhension globale :

## Étape 1 : initialiser le flux d'entrée du fichier EPS

```csharp
// ExDébut : 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExFin : 1
```

Dans cette étape, nous configurons le flux d'entrée pour le fichier EPS que vous souhaitez modifier. Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel d'accès à votre répertoire de documents.

## Étape 2 : Obtenez les métadonnées XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Récupérez les métadonnées XMP existantes du fichier EPS. Si le fichier EPS ne contient pas de métadonnées XMP, une nouvelle sera générée avec les valeurs des commentaires de métadonnées PS.

## Étape 3 : modifier les valeurs des métadonnées XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Ici, nous démontrons la modification de deux valeurs nommées dans la structure « xmpTPg:MaxPageSize ». Vous pouvez le personnaliser en fonction de vos besoins spécifiques.

## Étape 4 : Enregistrez le fichier EPS avec les métadonnées XMP modifiées

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Enregistrez le fichier EPS modifié dans le flux de sortie. Le fichier reflétera désormais les modifications apportées aux métadonnées XMP.

## Conclusion

Avec ce didacticiel, vous avez appris à exploiter Aspose.Page pour .NET pour modifier les valeurs nommées dans les métadonnées XMP des fichiers EPS. Cette fonctionnalité ouvre un monde de possibilités pour personnaliser et adapter vos documents afin de répondre à des exigences spécifiques.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats de document ?

A1 : Oui, Aspose.Page prend en charge divers formats de documents, notamment EPS, XPS et PDF.

### Q2 : Existe-t-il une version d’essai disponible pour Aspose.Page pour .NET ?

 A2 : Oui, vous pouvez accéder à un essai gratuit[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver plus de documentation sur Aspose.Page pour .NET ?

 A3 : Se référer à la documentation[ici](https://reference.aspose.com/page/net/).

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A4 : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Quelles options de support sont disponibles pour les utilisateurs d'Aspose.Page pour .NET ?

 A5 : Visitez le forum de la communauté[ici](https://forum.aspose.com/c/page/39) pour du soutien et des discussions.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
