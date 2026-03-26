---
date: 2026-03-26
description: Apprenez à créer un document PostScript .NET et à ajouter une image transparente
  en utilisant Aspose.Page. Ce guide étape par étape couvre les prérequis, le code
  et les astuces.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: Créer un document PostScript .NET avec une image transparente (Aspose.Page)
url: /fr/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document PostScript .NET avec image transparente (Aspose.Page)

## Introduction

Dans ce tutoriel, vous apprendrez **comment créer un document PostScript .NET** et intégrer un PNG transparent à l'aide d'Aspose.Page pour .NET. Ajouter des images transparentes vous permet de créer des graphiques plus riches et superposés — parfaits pour les filigranes, les superpositions ou les maquettes d'interface utilisateur dans un fichier PS. Nous parcourrons chaque étape, de la configuration de l'environnement au rendu des images opaques et transparentes.

## Réponses rapides
- **Que fait Aspose.Page ?** Il fournit une API complète pour générer, modifier et rendre des documents PostScript (PS) et XPS en .NET.  
- **Puis‑je ajouter des PNG transparents ?** Oui — utilisez `DrawTransparentImage` pour contrôler l'opacité.  
- **Quelles versions de .NET sont prises en charge ?** Toutes les versions récentes de .NET Framework, .NET Core et .NET 5/6.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour l'évaluation ; une licence est requise pour la production.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple de base.

## Prérequis

Avant de plonger, assurez‑vous d'avoir :

- **Aspose.Page pour .NET** – téléchargez-le depuis le [lien de téléchargement](https://releases.aspose.com/page/net/).  
- Un dossier où vous conserverez le document PS et l'image à intégrer.  
- Un PNG translucide (par ex., `mask1.png`) qui sera utilisé pour la couche transparente.

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms contenant les classes dont nous aurons besoin. Cela nous donne accès au modèle de document PS, aux utilitaires graphiques et aux types de dessin .NET de base.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Configurer le répertoire de votre document

Définissez le chemin où se trouvent l'image source et le fichier PS de sortie. Remplacez le texte de substitution par le chemin réel sur votre machine.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer le flux de sortie pour le document PostScript

Nous écrirons le contenu PS généré dans un flux de fichier. Ce flux est ensuite passé au constructeur `PsDocument`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Étape 3 : Définir les options d’enregistrement et la couleur d’arrière‑plan

Configurez `PsSaveOptions` pour définir la façon dont le fichier est enregistré. Définir une couleur d’arrière‑plan est utile lorsque vous souhaitez un canevas solide derrière les éléments transparents.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Étape 4 : Créer un nouveau document PS d’une page

Créez le document en utilisant le flux et les options définies ci‑dessus. Le drapeau `false` indique à Aspose.Page de ne pas fermer automatiquement le flux.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 5 : Enregistrer l’état graphique et traduire

Avant de dessiner, nous enregistrons l’état graphique actuel et déplaçons l’origine afin que nos images apparaissent à l’emplacement souhaité sur la page.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## Comment ajouter une image transparente à un document PostScript

### Étape 6 : Ajouter une image RGB opaque

Tout d'abord, nous ajoutons le même PNG comme image opaque normale. Cela montre la différence visuelle lorsque nous appliquerons plus tard la transparence.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Étape 7 : Ajouter une image transparente

Maintenant, nous utilisons `DrawTransparentImage` pour rendre le PNG avec une valeur d’opacité. Le troisième paramètre (`255`) représente une opacité totale ; des valeurs plus faibles augmentent la transparence. C’est ici que nous **définissons la transparence de l’image .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Astuce :** Pour rendre l’image à 50 % transparente, passez `128` au lieu de `255`.

## Étape 8 : Restaurer l’état graphique et fermer la page

Après le dessin, restaurez l’état graphique précédent et fermez la page pour finaliser le contenu.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Étape 9 : Enregistrer le document

Enfin, enregistrez le fichier PS sur le disque.

```csharp
document.Save();
```

En suivant ces étapes, vous avez **créé un document PostScript .NET** contenant à la fois une image opaque et une image transparente, démontrant comment **dessiner une image transparente en C#** avec Aspose.Page.

## Pourquoi utiliser Aspose.Page pour les effets de transparence ?

- **Contrôle total** de l’état graphique, des matrices et des niveaux d’opacité.  
- **Aucune dépendance externe** — tout fonctionne dans du code .NET pur.  
- **Prise en charge multiplateforme** vous permet de générer des fichiers PS sous Windows, Linux ou macOS.

## Problèmes courants & dépannage

| Problème | Solution |
|----------|----------|
| L'image apparaît complètement opaque même après `DrawTransparentImage` | Assurez‑vous que la valeur alpha (troisième argument) est inférieure à `255`. |
| Le fichier PS affiche une page blanche | Vérifiez que la couleur d’arrière‑plan est définie et que le chemin du flux est correct. |
| Exception « File not found » | Vérifiez à nouveau `dataDir` et que `mask1.png` existe dans ce dossier. |

## Questions fréquentes

**Q : Puis‑je utiliser d’autres formats d’image que le PNG pour la transparence ?**  
R : Oui — Aspose.Page prend en charge PNG, GIF et TIFF pour le rendu transparent.

**Q : Aspose.Page est‑il compatible avec le dernier framework .NET ?**  
R : Absolument. La bibliothèque est régulièrement mise à jour pour .NET 6, .NET 7 et les versions ultérieures.

**Q : Puis‑je appliquer la transparence à un document PS existant ?**  
R : Oui. Ouvrez le document avec `PsDocument`, ajoutez une nouvelle page ou modifiez une page existante, puis utilisez la même approche `DrawTransparentImage`.

**Q : Quels avantages Aspose.Page offre‑t‑il par rapport aux bibliothèques graphiques génériques ?**  
R : Il est spécialement conçu pour PS/XPS, offrant un contrôle précis sur les graphiques vectoriels, les polices et la gestion des images sans nécessiter un moteur de rendu complet.

**Q : Existe‑t‑il des limites au niveau de transparence que je peux définir ?**  
R : Non. Vous pouvez spécifier n’importe quelle valeur alpha de `0` (complètement transparent) à `255` (totalement opaque).

## Conclusion

Nous avons démontré comment **créer un document PostScript .NET** et intégrer à la fois des images opaques et transparentes à l’aide d’Aspose.Page. Cette technique ouvre la voie à des mises en page de documents sophistiquées, au filigrane et aux graphiques superposés — le tout généré de manière programmatique depuis C#.

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.Page 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}