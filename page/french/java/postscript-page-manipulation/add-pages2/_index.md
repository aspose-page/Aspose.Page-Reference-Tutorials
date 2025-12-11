---
date: 2025-12-11
description: Apprenez à définir une taille de page personnalisée et à ajouter des
  pages aux documents PostScript Java en utilisant Aspose.Page. Suivez notre guide
  étape par étape pour une manipulation fluide des documents.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Tutoriel Aspose.Page Java – définir une taille de page personnalisée lors de
  l'ajout de pages en PostScript
url: /fr/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutoriel Aspose.Page Java – définir une taille de page personnalisée lors de l’ajout de pages en PostScript

## Introduction
Dans les applications Java modernes, **définir une taille de page personnalisée** pour la sortie PostScript est souvent nécessaire—que vous génériez des factures, des tickets ou des graphiques personnalisés. Aspose.Page pour Java rend cette tâche simple. Dans ce tutoriel, vous apprendrez comment ajouter des pages et définir des tailles de page personnalisées dans un document PostScript, étape par étape, afin de produire à chaque fois la mise en page exactement souhaitée.

## Quick Answers
- **Puis‑je définir des tailles de page différentes pour chaque page ?** Oui, vous pouvez ouvrir des pages avec des dimensions personnalisées en utilisant `document.openPage(width, height)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence Aspose.Page valide est requise pour les déploiements non‑évaluatifs.  
- **Quelles versions de Java sont prises en charge ?** La bibliothèque fonctionne avec Java 8 et les versions ultérieures.  
- **L’API est‑elle thread‑safe ?** Les instances de document ne sont pas thread‑safe ; créez un `PsDocument` distinct par thread.  
- **Quelle taille maximale peut atteindre un fichier PostScript ?** Aspose.Page gère efficacement les fichiers de plusieurs mégaoctets ; l’utilisation de la mémoire dépend du contenu, pas du nombre de pages.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Une compréhension de base de la programmation Java.  
- Aspose.Page pour Java ajouté à votre projet (Maven/Gradle ou JAR manuel).  
- Un environnement de développement Java (IDE, JDK 8+).  

## Import Packages
Pour commencer, importez les classes nécessaires de la bibliothèque Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
Tout d’abord, créez un nouveau `PsDocument` configuré pour plusieurs pages. Cela initialise le flux de sortie et indique à la bibliothèque que nous travaillerons avec un fichier multipage.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Step 2: Add Content to the First Page
Une fois le document prêt, vous pouvez ajouter tout le contenu souhaité à la première page. Lorsque vous avez terminé, fermez la page pour verrouiller son contenu.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
Si la taille de page par défaut ne correspond pas à vos besoins, vous pouvez **définir une taille de page personnalisée** lors de l’ouverture d’une nouvelle page. Cela est utile pour les reçus, les étiquettes ou toute mise en page non standard.

## Step 3: Add a Second Page with Different Size
Ci‑dessous, nous ouvrons une seconde page en fournissant explicitement une largeur et une hauteur personnalisées (en points). Cela montre comment définir une taille de page personnalisée pour des pages individuelles.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
Enfin, persistez les modifications en enregistrant le document. Toutes les pages—y compris celles avec des tailles personnalisées—sont écrites dans le fichier de sortie.

```java
// Save the document
document.save();
```

En suivant ces étapes, vous pouvez ajouter des pages de façon transparente et **définir des tailles de page personnalisées** dans un document PostScript Java en utilisant Aspose.Page, vous offrant un contrôle complet sur la mise en page de chaque page.

## Conclusion
Aspose.Page pour Java fournit une API robuste et conviviale pour la gestion des documents PostScript. Vous savez maintenant comment ajouter plusieurs pages, appliquer des dimensions personnalisées et enregistrer le résultat—vous permettant de générer une sortie parfaitement formatée pour toute solution basée sur Java.

## Frequently Asked Questions
### Puis‑je ajouter des pages de tailles différentes dans un même document PostScript ?
Oui, comme démontré dans ce tutoriel, vous pouvez ajouter des pages de tailles variées dans un document PostScript multipage.  
### Existe‑t‑il des limitations quant au nombre de pages que je peux ajouter ?
Aspose.Page prend en charge l’ajout d’un nombre pratiquement illimité de pages à un document.  
### Puis‑je ajouter du contenu personnalisé, tel que des images ou des graphiques, aux pages ?
Absolument ! Aspose.Page vous permet d’ajouter une large gamme de contenus, y compris du texte, des images et d’autres éléments graphiques.  
### Aspose.Page est‑il adapté à la gestion de documents volumineux ?
Oui, Aspose.Page est conçu pour gérer efficacement aussi bien les petits que les grands documents.  
### Où puis‑je trouver des ressources supplémentaires et de l’assistance pour Aspose.Page ?
Consultez la [documentation Aspose.Page](https://reference.aspose.com/page/java/), ou visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.  

**Additional Q&A**

**Q:** *Quels formats d’image sont pris en charge lors du dessin sur une page PostScript ?*  
**R:** Vous pouvez intégrer directement des images PNG, JPEG, BMP et GIF en utilisant l’API de dessin.  

**Q:** *Comment modifier le DPI par défaut du document ?*  
**R:** Définissez `PsSaveOptions.setResolution(int dpi)` avant de créer le `PsDocument`.  

**Q:** *Puis‑je chiffrer un fichier PostScript avec un mot de passe ?*  
**R:** Le format PostScript ne supporte pas le chiffrement, mais vous pouvez encapsuler la sortie dans un PDF et appliquer des paramètres de sécurité si nécessaire.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
