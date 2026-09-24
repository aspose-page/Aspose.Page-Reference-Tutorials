---
date: 2026-09-24
description: Apprenez à utiliser Aspose.Page pour convertir EPS en PNG en Java, configurer
  une licence à compteurs et écrire du code Java pour créer un fichier PNG efficacement.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Configurer la licence à compteurs en Java
og_description: Aspose.Page convertit EPS en PNG en Java avec une licence à compteurs.
  Ce guide montre étape par étape comment configurer la licence, rendre EPS et écrire
  du code Java pour créer un fichier PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page convertit EPS en PNG en Java (licence à compteurs)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page convertit EPS en PNG en Java (licence à compteurs)
url: /fr/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page convertir EPS en PNG en Java (licence à compteurs)

## Introduction
Si vous devez **enregistrer EPS en PNG** dans une application Java tout en gardant la licence simple, vous êtes au bon endroit. Ce tutoriel vous guide à travers la configuration d’une **licence à compteurs** pour Aspose.Page, le chargement d’un fichier EPS (Encapsulated PostScript) et sa conversion en image PNG. À la fin, vous comprendrez comment **rendre EPS en PNG efficacement** et comment **écrire du code Java pour créer un fichier PNG** qui fonctionne de manière fiable en production.

## Réponses rapides
- **Que signifie « save EPS as PNG » ?** Il convertit un fichier EPS vectoriel en une image PNG raster, en préservant la transparence et la compression sans perte.  
- **Pourquoi utiliser une licence à compteurs ?** Vous ne payez que pour les pages que vous traitez, ce qui est idéal pour des charges de travail variables.  
- **Ai-je besoin d’une connexion Internet ?** Non, les clés à compteurs sont validées localement sur la JVM.  
- **Quelle version de Java est requise ?** Java 8 ou supérieur est entièrement pris en charge.  
- **Combien de temps prend la configuration ?** Environ 10 minutes pour une implémentation de base.

## Qu’est‑ce que « save EPS to PNG » ?
Enregistrer EPS en PNG convertit un document Encapsulated PostScript vectoriel en une image PNG raster, en préservant la transparence et offrant une compression sans perte. Cette transformation est utile lorsque vous avez besoin de graphiques prêts pour le web, de vignettes ou d’aperçus imprimables qui peuvent être affichés dans n’importe quel navigateur sans nécessiter d’interpréteur PostScript.

## Pourquoi rendre EPS en PNG avec Aspose.Page ?
Aspose.Page fournit une API pure‑Java qui rasterise les fichiers EPS avec une haute fidélité, prend en charge plus de 50 formats de sortie et propose une licence à compteurs afin que vous ne payiez que pour ce que vous convertissez. La bibliothèque peut traiter des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire, offrant un rendu rapide et précis sur toute plateforme supportant la JVM.

## Prérequis
- Expérience de base en développement Java.  
- La bibliothèque Aspose.Page téléchargée depuis la [page de téléchargement Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Une paire de clés publiques et privées à compteurs provenant de votre compte Aspose.  

## Importation des packages
Les instructions `import` importent les classes requises dans le scope. Conservez ce bloc exactement tel qu’il est affiché afin que le code compile sans modifications.

Les classes `java.io` gèrent les flux de fichiers, tandis que les classes Aspose.Page gèrent la licence, le chargement du document et le rendu d’image.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Comment enregistrer EPS en PNG avec Aspose.Page Java
Voici le guide étape par étape qui combine la licence, le chargement, le rendu et l’écriture du fichier PNG final.

### Réponse directe
Chargez votre fichier EPS, appliquez une licence à compteurs, configurez `ImageSaveOptions` pour PNG, rendez le document vers un `ImageDevice`, puis écrivez le tableau d’octets résultant sur le disque. Cette séquence complète le flux de travail **save EPS as PNG** en quelques lignes de code Java.

### Étape 1 : initialiser le document et le format d’image
Tout d’abord, définissez les clés à compteurs et spécifiez le format de sortie (PNG). Cela établit la base de la conversion.

La classe `MeteredLicense` stocke vos clés publiques et privées, tandis que `ImageSaveOptions` indique à Aspose.Page de produire une sortie PNG.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Étape 2 : initialiser le flux d’entrée PostScript
Ouvrez le fichier EPS que vous souhaitez convertir. Le flux alimente le document dans Aspose.Page.

Le `FileInputStream` lit le fichier EPS depuis le disque, permettant au constructeur `Document` d’analyser les données PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Étape 3 : vérifier la licence du document
Vérifiez toujours que la licence à compteurs a été appliquée correctement avant le traitement.

La méthode `isLicensed()` renvoie `true` uniquement lorsque les clés fournies sont valides, évitant ainsi l’utilisation accidentelle d’une bibliothèque non licenciée.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Étape 4 : initialiser les options et le dispositif d’image
Créez l’objet d’options qui contrôle les paramètres de conversion et le dispositif qui recevra l’image rendue.

`ImageDevice` capture la sortie rasterisée en mémoire, tandis que `ImageSaveOptions` vous permet d’ajuster le DPI, le niveau de compression et la profondeur de couleur.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Étape 5 : enregistrer le fichier EPS en image
Ceci est l’appel principal **save EPS as PNG**. Le document est rendu dans le dispositif d’image en utilisant les options que nous avons configurées.

La méthode `document.save(device, options)` effectue la rasterisation en une seule étape.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Étape 6 : obtenir et enregistrer les octets de l’image
Extrayez les octets PNG du dispositif et écrivez‑les dans un fichier sur le disque. Cette étape montre comment **write PNG file Java** en toute sécurité.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` persiste l’image sans bibliothèques supplémentaires.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Licence non reconnue** | Les clés sont incorrectes ou `setMeteredKey` est appelé après le traitement du document. | Vérifiez à nouveau les chaînes de clés publiques/privées et assurez‑vous que `setMeteredKey` s’exécute avant tout appel Aspose.Page. |
| **Le fichier de sortie est vide** | `device.getImagesBytes()` a renvoyé `null` parce que le fichier EPS n’a pas pu être analysé. | Vérifiez que le fichier EPS est valide et que `ImageSaveOptions` spécifie une taille de canevas non nulle. |
| **OutOfMemoryError sur un EPS volumineux** | Le rendu de gros fichiers vectoriels consomme beaucoup de mémoire du tas. | Traitez les pages une à une ou augmentez le tas JVM (`-Xmx2g`). |

## Questions fréquemment posées

**Q : Comment obtenir les clés publiques et privées à compteurs ?**  
R : Connectez‑vous à votre compte Aspose, accédez à la section **Metered License** et copiez les clés publiques et privées générées.

**Q : La bibliothèque Aspose.Page est‑elle gratuite ?**  
R : Aspose.Page propose un essai gratuit avec toutes les fonctionnalités ; l’utilisation en production nécessite une licence payante. Téléchargez l’essai depuis la [page de téléchargement d’essai Aspose](https://releases.aspose.com/).

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Oui, une licence commerciale autorise le déploiement en environnement de production. Achetez une licence sur la [page d’achat Aspose](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver une documentation supplémentaire ?**  
R : La référence complète de l’API est disponible sur la [référence API Java Aspose.Page](https://reference.aspose.com/page/java/).

**Q : Comment obtenir une licence temporaire pour l’évaluation ?**  
R : Les licences temporaires sont fournies via le portail Aspose [page de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/).

**Q : Que faire si je dois convertir des fichiers EPS multi‑pages ?**  
R : Parcourez chaque page avec `device.getImagesBytes()` et écrivez chaque tableau d’octets dans un fichier PNG séparé.

**Q : Puis‑je modifier la qualité ou la profondeur de couleur du PNG ?**  
R : Oui, configurez `ImageSaveOptions` (par ex., `options.setCompressionLevel(9)`) avant d’appeler `document.save(...)`.

---

**Dernière mise à jour :** 2026-09-24  
**Testé avec :** Aspose.Page 24.12 for Java (latest)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment définir la licence pour l’API Java Aspose.Page – Gestion des licences](/page/java/license-management/)
- [Convertir PS en PNG avec l’API Java Aspose.Page](/page/java/postscript-conversion/to-image/)
- [Redimensionner EPS avec Aspose.Page – Manipulation EPS Java](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}