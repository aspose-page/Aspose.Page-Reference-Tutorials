---
date: 2026-02-05
description: Apprenez à enregistrer un EPS au format PNG avec Aspose.Page pour Java
  tout en configurant une licence à consommation. Guide étape par étape avec un exemple
  complet de code.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Enregistrer EPS au format PNG avec Aspose.Page Java (licence à la consommation)
url: /fr/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer EPS en PNG avec Aspose.Page Java (Licence à compteurs)

## Introduction
Si vous devez **enregistrer EPS en PNG** dans une application Java et que vous recherchez une solution simple pour gérer la licence, vous êtes au bon endroit. Ce tutoriel vous guide à travers la configuration d’une licence à compteurs pour Aspose.Page, le chargement d’un fichier PostScript (EPS) et sa conversion en image PNG — le tout avec des étapes claires et concises que vous pouvez suivre immédiatement. À la fin, vous comprendrez également comment **rendre EPS en PNG** efficacement et comment écrire du code **write PNG file Java** qui fonctionne en production.

## Quick Answers
- **Que signifie « save EPS as PNG » ?** Cela convertit un fichier EPS vectoriel en une image PNG raster.  
- **Pourquoi utiliser une licence à compteurs ?** Elle vous permet de ne payer que pour les pages que vous traitez, idéal pour des charges de travail variables.  
- **Ai‑je besoin d’une connexion Internet ?** Non, les clés à compteurs sont validées localement.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.  
- **Combien de temps prend la mise en place ?** Environ 10 minutes pour une implémentation de base.  

## What is “save EPS as PNG”?
Enregistrer EPS en PNG transforme un document Encapsulated PostScript évolutif en un format bitmap largement supporté. PNG conserve la transparence et offre une compression sans perte, ce qui le rend idéal pour les graphiques web, les vignettes et les aperçus d’impression.

## Why render EPS to PNG with Aspose.Page?
- **Pure Java API** – aucune dépendance native, vous pouvez l’exécuter partout où la JVM est prise en charge.  
- **Rendu haute fidélité** – les graphiques vectoriels sont rasterisés avec précision, préservant la qualité des lignes.  
- **Licence à compteurs** – vous ne payez que pour ce que vous convertissez, ce qui rend les coûts prévisibles.  
- **Multiples options de sortie** – en plus de PNG, vous pouvez également générer JPEG, TIFF, et plus encore, offrant ainsi une flexibilité pour différents projets.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en programmation Java.  
- La bibliothèque Aspose.Page installée – téléchargez‑la depuis [here](https://releases.aspose.com/page/java/).  
- Les clés publiques et privées à compteurs, que vous pouvez obtenir via votre compte Aspose.

## Import Packages
Tout d’abord, importez les classes dont nous aurons besoin. Conservez le bloc d’importation exactement tel qu’il est affiché afin que le code compile sans modifications.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## How to save EPS as PNG using Aspose.Page Java
Voici le guide étape par étape qui combine la licence, le chargement, le rendu et l’écriture du fichier PNG final.

### Step 1: Initialize Document and Image Format
Ici, nous définissons les clés à compteurs et spécifions le format de sortie (PNG). C’est la base de l’opération **save EPS as PNG**.

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

### Step 2: Initialize PostScript Input Stream
Ouvrez le fichier EPS que vous souhaitez convertir. Le flux alimente le document dans Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Step 3: Check Document License
Vérifiez toujours que la licence à compteurs a été appliquée correctement avant le traitement.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Step 4: Initialize Options and Image Device
Créez l’objet d’options qui contrôle les paramètres de conversion ainsi que le dispositif qui recevra l’image rendue.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Step 5: Save EPS File as Image
C’est l’appel principal **save EPS as PNG**. Le document est rendu dans le dispositif d’image en utilisant les options que nous avons configurées.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Step 6: Get and Save Image Bytes
Extrayez les octets PNG du dispositif et écrivez‑les dans un fichier sur le disque. Cette étape montre comment **write PNG file Java** en toute sécurité.

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

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | Les clés sont incorrectes ou placées dans le mauvais ordre. | Vérifiez à nouveau les chaînes de clés publiques/privées et assurez‑vous que `setMeteredKey` est appelé avant tout traitement du document. |
| **Output file is empty** | `device.getImagesBytes()` a renvoyé `null`. | Vérifiez que le fichier EPS est valide et que les `ImageSaveOptions` ne sont pas définies sur un canevas de taille zéro. |
| **OutOfMemoryError on large EPS** | Le rendu de gros fichiers vectoriels consomme beaucoup de mémoire. | Traitez les pages une à une ou augmentez le tas JVM (`-Xmx2g`). |

## Frequently Asked Questions

**Q : How do I obtain metered public and private keys?**  
R : Vous pouvez obtenir ces clés via votre compte Aspose.

**Q : Is the Aspose.Page library free?**  
R : Aspose.Page propose à la fois une version d’essai gratuite et des versions payantes. Visitez [here](https://releases.aspose.com/) pour un essai gratuit.

**Q : Can I use Aspose.Page for commercial projects?**  
R : Oui, Aspose.Page propose des licences commerciales. Vous pouvez les acheter [here](https://purchase.aspose.com/buy).

**Q : Where can I find additional documentation?**  
R : Consultez la documentation [here](https://reference.aspose.com/page/java/).

**Q : How can I get temporary licenses?**  
R : Les licences temporaires peuvent être obtenues [here](https://purchase.aspose.com/temporary-license/).

**Q : What if I need to convert multi‑page EPS files?**  
R : Parcourez chaque page avec `device.getImagesBytes()` et écrivez chaque tableau d’octets dans un fichier PNG séparé.

**Q : Can I change the PNG quality or color depth?**  
R : Oui, configurez `ImageSaveOptions` (par ex., `options.setCompressionLevel(...)`) avant d’appeler `document.save(...)`.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}