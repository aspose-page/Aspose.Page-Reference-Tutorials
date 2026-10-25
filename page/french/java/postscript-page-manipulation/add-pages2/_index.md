---
date: 2026-10-25
description: Apprenez à définir une taille de page personnalisée et à ajouter des
  pages aux documents PostScript Java en utilisant Aspose.Page. Suivez notre guide
  étape par étape pour une manipulation fluide des documents.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Ajout de pages en PostScript
og_description: Apprenez à définir une taille de page personnalisée en PostScript
  avec Aspose.Page pour Java. Suivez les instructions étape par étape pour ajouter
  des pages, définir les dimensions et enregistrer le document efficacement.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Définir une taille de page personnalisée en PostScript avec Aspose.Page
  Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
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
Dans les applications Java modernes, **set custom page size** pour la sortie PostScript est souvent requis—que vous génériez des factures, des tickets ou des graphiques personnalisés. Ce tutoriel vous montre comment définir une taille de page personnalisée pour chaque page, ajouter plusieurs pages et générer un fichier PostScript qui correspond exactement à vos besoins de mise en page. Vous obtiendrez un exemple complet et exécutable que vous pouvez intégrer à n’importe quel projet Java 8+.

## Réponses rapides
- **Puis‑je définir des tailles de page différentes pour chaque page ?** Oui—vous pouvez ouvrir des pages avec des dimensions personnalisées en utilisant `document.openPage(width, height)`.  
- **Ai‑je besoin d’une licence pour une utilisation en production ?** Une licence valide Aspose.Page est requise pour les déploiements non‑évaluatifs.  
- **Quelles versions de Java sont prises en charge ?** La bibliothèque fonctionne avec Java 8 et les versions ultérieures.  
- **L’API est‑elle thread‑safe ?** Les instances de Document ne sont pas thread‑safe ; créez un `PsDocument` distinct par thread.  
- **Quelle taille maximale peut avoir un fichier PostScript ?** Aspose.Page gère efficacement les fichiers de plusieurs mégaoctets ; l’utilisation de la mémoire augmente avec le contenu, pas avec le nombre de pages.  
- **Puis‑je utiliser la surcharge open page width/height ?** Absolument—`openPage(double width, double height)` vous permet de spécifier n’importe quelles dimensions en points.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Une compréhension de base de la programmation Java.  
- Aspose.Page for Java ajouté à votre projet (Maven/Gradle ou JAR manuel).  
- Un environnement de développement Java (IDE, JDK 8+).  

## Importer les packages
Les classes suivantes sont requises : `FileOutputStream` pour écrire des fichiers, `PsDocument` pour créer des documents PostScript, et `PsSaveOptions` pour configurer les options de sortie.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Étape 1 : créer un document PostScript multipage
`PsDocument` est la classe principale représentant un document PostScript pouvant contenir plusieurs pages.

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

## Étape 2 : ajouter du contenu à la première page
Une fois le document prêt, vous pouvez ajouter tout le contenu nécessaire à la première page. Lorsque vous avez terminé, fermez la page pour verrouiller son contenu.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Comment définir une taille de page personnalisée
Vous définissez une taille de page personnalisée en appelant `document.openPage(width, height)` avec les dimensions souhaitées en points avant de dessiner tout contenu. `openPage(width, height)` ouvre une nouvelle page avec la largeur et la hauteur spécifiées, vous offrant un contrôle total sur le canevas de la page. Si la taille de page par défaut ne convient pas, vous pouvez **set custom page size** lors de l’ouverture d’une nouvelle page. Cela est utile pour les reçus, les étiquettes ou toute mise en page non standard.

## Étape 3 : ajouter une deuxième page avec une taille différente
Ci-dessous, nous ouvrons une deuxième page et fournissons explicitement une largeur et une hauteur personnalisées (en points). Cela montre comment définir une taille de page personnalisée pour chaque page, vous permettant de travailler avec **different page sizes** au sein du même document.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Étape 4 : enregistrer le document
Enfin, persistez les modifications en enregistrant le document. Toutes les pages—y compris celles avec des tailles personnalisées—sont écrites dans le fichier de sortie.

```java
// Save the document
document.save();
```

En suivant ces étapes, vous pouvez ajouter des pages de manière fluide et **set custom page size** dans un document PostScript Java avec Aspose.Page, vous offrant un contrôle complet sur la mise en page de chaque page.

## Pourquoi utiliser Aspose.Page pour définir une taille de page personnalisée ?
Aspose.Page offre un contrôle précis sur les dimensions des pages, vous permettant de définir n’importe quelle largeur et hauteur en points, de mélanger plusieurs tailles de page dans un même document, et de diffuser le contenu efficacement pour une génération PostScript haute performance. Cela le rend idéal pour les factures, les tickets et le traitement par lots à grande échelle où l’utilisation de la mémoire doit rester faible.

Aspose.Page vous permet de définir des dimensions de page exactes en points, de mélanger plusieurs tailles dans un même fichier, et de diffuser le contenu efficacement, ce qui vous donne un contrôle précis et de hautes performances pour la génération de PostScript.  
- **Précision :** Les dimensions sont définies en points, vous obtenez ainsi un contrôle exact sur la largeur et la hauteur de la page.  
- **Flexibilité :** Mélangez et associez **different page sizes** dans un seul fichier PostScript.  
- **Performance :** La bibliothèque diffuse le contenu directement vers le fichier de sortie, gérant des fichiers jusqu’à 500 Mo tout en maintenant l’utilisation du tas en dessous de 100 Mo, ce qui la rend adaptée aux scénarios de **generate PostScript file** à grande échelle.  
- **API riche :** Prend en charge plus de 30 primitives graphiques, 10 formats d’image et un nombre illimité d’objets texte par page—tout en respectant les dimensions personnalisées que vous avez définies.

## Problèmes courants et solutions
| Issue | Solution |
|-------|----------|
| **Les dimensions de la page semblent inversées** | Rappelez‑vous que `openPage(width, height)` attend la largeur en premier, puis la hauteur (toutes deux en points). |
| **Le contenu dépasse les limites de la page** | Utilisez le système de coordonnées `PsGraphics` pour positionner les éléments dans les limites personnalisées, ou redimensionnez votre dessin. |
| **Erreurs de mémoire insuffisante sur de très gros documents** | Activez le streaming en écrivant directement dans un `FileOutputStream` comme indiqué, et évitez de charger de grandes images en mémoire d’un seul coup. |

## Questions fréquemment posées
### Puis‑je ajouter des pages de tailles différentes dans un seul document PostScript ?
Oui, comme démontré dans ce tutoriel, vous pouvez ajouter des pages de tailles variables dans un document PostScript multipage.  

### Existe‑t‑il des limites au nombre de pages que je peux ajouter ?
Aspose.Page prend en charge l’ajout d’un nombre pratiquement illimité de pages à un document.  

### Puis‑je ajouter du contenu personnalisé, tel que des images ou des graphiques, aux pages ?
Absolument ! Aspose.Page vous permet d’ajouter une large gamme de contenus, y compris du texte, des images et d’autres éléments graphiques.  

### Aspose.Page est‑il adapté à la gestion de gros documents ?
Oui, Aspose.Page est conçu pour gérer efficacement tant les petits que les gros documents.  

### Où puis‑je trouver des ressources supplémentaires et du support pour Aspose.Page ?
Explorez la [documentation Aspose.Page](https://reference.aspose.com/page/java/), ou visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide de la communauté.  

**Questions supplémentaires**

**Q :** *Quels formats d’image sont pris en charge lors du dessin sur une page PostScript ?*  
**R :** Vous pouvez intégrer directement des images PNG, JPEG, BMP et GIF en utilisant l’API de dessin.  

**Q :** *Comment modifier le DPI par défaut du document ?*  
**R :** Définissez `PsSaveOptions.setResolution(int dpi)` avant de créer le `PsDocument`.  

**Q :** *Puis‑je chiffrer un fichier PostScript avec un mot de passe ?*  
**R :** Le PostScript lui‑même ne prend pas en charge le chiffrement, mais vous pouvez encapsuler la sortie dans un PDF et appliquer des paramètres de sécurité si nécessaire.

**Last updated:** 2026-10-25  
**Tested with:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

## Tutoriels associés

- [Comment définir la taille de page A4 et créer un PostScript en Java avec Aspose.Page](/page/java/document-creation/postscript/)
- [Comment convertir un PostScript en PDF en utilisant l’API Java Aspose.Page](/page/java/postscript-conversion/to-pdf/)
- [Comment dessiner un rectangle en PostScript Java avec Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}