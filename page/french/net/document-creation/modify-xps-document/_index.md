---
date: 2026-01-12
description: Apprenez à modifier les documents XPS à l'aide d'Aspose.Page pour .NET
  et découvrez comment ajouter du texte aux fichiers XPS avec des exemples de code
  simples.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Modifier un document XPS avec Aspose.Page pour .NET
url: /fr/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifier un document XPS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans notre guide étape par étape sur **comment modifier un document xps** avec Aspose.Page pour .NET. Que vous ayez besoin d'insérer une signature, d'ajouter un filigrane, ou simplement de placer du texte personnalisé sur une page, ce tutoriel vous montre exactement **comment ajouter du texte** à un document XPS en quelques minutes. Nous passerons en revue chaque ligne de code, expliquerons pourquoi chaque étape est importante, et vous donnerons des conseils pour éviter les pièges courants.

### Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Ajout d'un texte de signature (« Confirmé ») aux pages sélectionnées d'un fichier XPS.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET (dernière version).  
- **Ai-je besoin d'une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Combien de temps prend l'implémentation ?** Environ 10 minutes pour une insertion de signature basique.

## Qu'est-ce que la modification d'un document XPS ?

XPS (XML Paper Specification) est le format de document à mise en page fixe de Microsoft, similaire au PDF. Modifier un document XPS signifie changer son contenu visuel de façon programmatique — ajouter du texte, des images ou des formes — sans convertir le fichier dans un autre format. Aspose.Page fournit un modèle d'objets riche qui vous permet d'éditer les fichiers XPS directement depuis votre code .NET.

## Pourquoi utiliser Aspose.Page pour modifier des documents XPS ?

* **Contrôle total** – travailler avec les pages, glyphes, pinceaux et transformations à bas niveau.  
* **Aucune dépendance externe** – bibliothèque pure .NET, pas besoin de composants Office ou Adobe.  
* **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS via .NET Core.  
* **Performance robuste** – gère efficacement les gros documents et prend en charge la typographie avancée.

## Prérequis

Avant de commencer, assurez‑vous d'avoir les éléments suivants :

- **Aspose.Page pour .NET** – Installez le package NuGet ou téléchargez la bibliothèque depuis la documentation officielle **[here](https://reference.aspose.com/page/net/)**.  
- **Fichier XPS d'entrée** – Obtenez un document XPS d'exemple (par ex., `input1.xps`) depuis la **[Aspose releases page](https://releases.aspose.com/page/net/)**.  
- **Répertoire de travail** – Créez un dossier sur votre machine pour stocker les fichiers d'entrée et de sortie et notez son chemin complet ; vous assignerez ce chemin à la variable `dir` dans le code.  
- **Environnement de développement** – Visual Studio 2019/2022, .NET Framework 4.7.2 ou ultérieur, ou tout projet .NET Core/5/6.

Maintenant que tout est prêt, plongeons dans le code.

## Import Namespaces

Dans votre projet .NET, commencez par importer les espaces de noms requis pour Aspose.Page :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Étape 1 : Ouvrir le flux du document XPS

Nous ouvrirons le fichier XPS source sous forme de flux et créerons un objet `XpsDocument` qui représente l'intégralité du document.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Astuce :* Enveloppez le flux dans un bloc `using` pour garantir que le handle du fichier est libéré automatiquement.

## Étape 2 : Créer le texte de signature

Ensuite, nous créons un pinceau de couleur unie qui sera utilisé pour peindre les glyphes de la signature.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Vous pouvez changer `Color.BlueViolet` en n'importe quel `System.Drawing.Color` qui correspond à votre charte graphique.

## Étape 3 : Définir les pages et ajouter la signature

Nous spécifierons quelles pages doivent recevoir la signature, puis ajouterons les glyphes à chaque page.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Pourquoi ces coordonnées ?* Les valeurs X et Y sont mesurées en points (1/72 pouce). Ajustez‑les pour positionner le texte exactement où vous le souhaitez dans la mise en page de votre page.

## Étape 4 : Enregistrer les modifications du document XPS

Enfin, écrivez le document modifié sur le disque.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Le nouveau fichier `input1_out.xps` contient désormais la signature « Confirmé » sur les pages 1‑3.

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Signature non visible** | Coordonnées incorrectes ou page non sélectionnée | Vérifiez que `SelectActivePage` est appelé pour chaque page et ajustez les valeurs X/Y. |
| **Exception sur `AddGlyphs`** | Police non installée sur le serveur | Assurez‑vous que la police spécifiée (par ex., Arial) est disponible, ou intégrez une police personnalisée avec `document.AddFont`. |
| **Fichier de sortie corrompu** | Flux non fermé correctement | Utilisez des instructions `using` pour tous les flux et appelez `document.Dispose()` si nécessaire. |
| **Ralentissement des performances sur les gros fichiers** | Chargement du document entier en mémoire | Traitez les pages par lots ou utilisez `XpsLoadOptions` avec des options de streaming (si disponible dans les versions récentes). |

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec les dernières versions de .NET ?**  
R : Oui, Aspose.Page est régulièrement mis à jour pour prendre en charge .NET Framework 4.5+, .NET Core 3.1+, .NET 5 et .NET 6.

**Q : Puis‑je personnaliser la police et le style du texte ajouté ?**  
R : Absolument. Modifiez les paramètres de `AddGlyphs` (nom de la police, taille, `FontStyle`) selon vos besoins.

**Q : Existe‑t‑il des limites de taille pour les fichiers XPS ?**  
R : Aspose.Page peut gérer de gros documents, mais la consommation de mémoire augmente avec la taille du fichier. Pour des fichiers très volumineux, envisagez de traiter les pages individuellement.

**Q : Comment obtenir une licence temporaire pour Aspose.Page ?**  
R : Vous pouvez acquérir une licence temporaire **[here](https://purchase.aspose.com/temporary-license/)**.

**Q : Où puis‑je obtenir de l'aide ou rejoindre la communauté Aspose ?**  
R : Visitez le **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** pour poser des questions et partager vos expériences.

## Conclusion

Dans ce tutoriel nous avons démontré comment **modifier un document xps** en ajoutant du texte de signature personnalisé à l'aide d'Aspose.Page pour .NET. Vous disposez maintenant d’une base solide pour insérer n’importe quel texte, filigrane ou annotation sur des pages spécifiques d’un fichier XPS. Expérimentez avec différentes polices, couleurs et positions pour répondre aux exigences de votre marque, et explorez l’API plus large d’Aspose.Page pour des capacités graphiques et de mise en page avancées.

---

**Dernière mise à jour :** 2026-01-12  
**Testé avec :** Aspose.Page 24.11 for .NET (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}