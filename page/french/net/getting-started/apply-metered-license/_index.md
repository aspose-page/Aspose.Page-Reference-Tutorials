---
title: Appliquer une licence limitée avec Aspose.Page pour .NET
linktitle: Appliquer une licence limitée
second_title: API Aspose.Page .NET
description: Découvrez l'intégration transparente d'Aspose.Page pour .NET avec ce guide étape par étape sur l'application d'une licence limitée. Optimisez le traitement des documents sans effort.
weight: 10
url: /fr/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Appliquer une licence limitée avec Aspose.Page pour .NET

## Introduction

Libérez tout le potentiel d’Aspose.Page pour .NET en appliquant une licence limitée. Ce didacticiel vous guidera tout au long du processus de configuration et d'application de la licence limitée, garantissant une utilisation fluide et optimisée de cette puissante bibliothèque .NET.

## Conditions préalables

Avant de plonger dans les étapes, assurez-vous d’avoir les conditions préalables suivantes en place :

-  Une licence Aspose.Page pour .NET valide : vous pouvez l'obtenir auprès de[achat.aspose.com](https://purchase.aspose.com/buy).
-  Bibliothèque Aspose.Page installée : reportez-vous au[Documentation](https://reference.aspose.com/page/net/) pour les instructions d’installation.
- Environnement de développement .NET : assurez-vous qu'un environnement .NET fonctionnel est configuré sur votre ordinateur.

## Importer des espaces de noms

Dans votre projet .NET, importez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Page :

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Étape 1 : Définir les clés publiques et privées mesurées

 Initialisez le`Aspose.Page.Metered` classe et définissez les clés publiques et privées mesurées. Remplacer`<type public key here>` et`<type private key here>` avec vos vraies clés.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Étape 2 : Charger le fichier EPS et créer un document

 Spécifiez le chemin d'accès à votre fichier EPS et créez un flux pour lire son contenu. Ensuite, créez une instance de`PsDocument` classe du flux.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Étape 3 : Convertir une image EPS en PNG

 Créé un`ImageDevice` pour convertir le fichier EPS en image PNG. Enregistrez le fichier EPS en tant qu'image à l'aide du`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Étape 4 : Récupérer les octets de l'image

Obtenez les octets de l'image, où chaque tableau d'octets représente une page. Dans ce cas, nous avons une page.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Étape 5 : Enregistrer les octets d'image dans un fichier

Enregistrez les octets de l'image dans un fichier, garantissant ainsi une conversion réussie d'EPS en PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Étape 6 : Vérifier la licence limitée

Vérifiez visuellement si la licence limitée est appliquée avec succès. Si l'image résultante ne contient pas le message d'évaluation rouge, cela indique que la licence limitée est appliquée sans aucun problème.

Vous êtes maintenant prêt à exploiter toutes les capacités d'Aspose.Page pour .NET avec une licence limitée !

## Conclusion

Ce guide étape par étape vous a doté des connaissances nécessaires pour appliquer de manière transparente une licence limitée à l'aide d'Aspose.Page pour .NET. Améliorez vos capacités de traitement de documents et explorez les vastes fonctionnalités offertes par cette puissante bibliothèque.

## FAQ

### Q1 : Comment puis-je obtenir une licence limitée pour Aspose.Page pour .NET ?

 A1 : Visite[achat.aspose.com](https://purchase.aspose.com/buy) pour acquérir une licence valide.

### Q2 : Où puis-je trouver la documentation d’Aspose.Page pour .NET ?

 A2 : Référez-vous à[Aspose.Page .NET](https://reference.aspose.com/page/net/) pour une documentation complète.

### Q3 : Existe-t-il un forum pour les discussions et l'assistance sur Aspose.Page ?

 A3 : Oui, visitez[forum](https://forum.aspose.com/c/page/39) interagir avec la communauté et demander de l’aide.

### Q4 : Puis-je essayer Aspose.Page pour .NET avant d'acheter ?

 A4 : Absolument ! Accédez à l'essai gratuit sur[ici](https://releases.aspose.com/).

### Q5 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A5 : Visite[permis temporaire/](https://purchase.aspose.com/temporary-license/) pour obtenir un permis temporaire.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
