---
date: 2025-12-03
description: Apprenez à enregistrer un EPS au format PNG avec Aspose.Page pour Java
  tout en configurant une licence à compte. Guide étape par étape avec un exemple
  complet de code.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Enregistrer EPS en PNG avec Aspose.Page Java (Licence à la consommation)
url: /fr/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer EPS en PNG avec Aspose.Page Java (Licence à la consommation)

## Introduction
Si vous devez **enregistrer EPS en PNG** dans une application Java et que vous recherchez une méthode simple pour gérer la licence, vous êtes au bon endroit. Ce tutoriel vous guide à travers la configuration d’une licence à la consommation pour Aspose.Page, le chargement d’un fichier PostScript (EPS) et sa conversion en image PNG — le tout avec des étapes claires et concises que vous pouvez suivre immédiatement.

## Réponses rapides
- **Que signifie « enregistrer EPS en PNG » ?** Cela convertit un fichier EPS vectoriel en une image PNG raster.  
- **Pourquoi utiliser une licence à la consommation ?** Elle vous permet de ne payer que pour les pages que vous traitez, idéal pour des charges de travail variables.  
- **Ai‑je besoin d’une connexion Internet ?** Non, les clés à la consommation sont validées localement.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.  
- **Combien de temps prend la mise en place ?** Environ 10 minutes pour une implémentation de base.

## Qu’est‑ce que « enregistrer EPS en PNG » ?
Enregistrer EPS en PNG transforme un document Encapsulated PostScript évolutif en un format bitmap largement supporté. PNG conserve la transparence et offre une compression sans perte, ce qui le rend idéal pour les graphiques web, les vignettes et les aperçus d’impression.

## Pourquoi utiliser Aspose.Page pour cette tâche ?
- **Pure Java API** – aucune dépendance native.  
- **Haute fidélité** – les graphiques vectoriels sont rendus avec précision.  
- **Licence à la consommation** – vous ne payez que pour ce que vous convertissez.  
- **Prise en charge de plusieurs formats de sortie** – PNG, JPEG, TIFF, etc.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page installée – téléchargez‑la depuis [ici](https://releases.aspose.com/page/java/).  
- Clés publiques et privées à la consommation, que vous pouvez obtenir via votre compte Aspose.

## Importer les packages
Tout d’abord, importez les classes dont nous aurons besoin. Conservez le bloc d’import exactement tel qu’il est affiché afin que le code compile sans modification.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Étape 1 : Initialiser le document et le format d’image
Ici, nous définissons les clés à la consommation et spécifions le format de sortie (PNG). C’est la base de l’opération **enregistrer EPS en PNG**.

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

## Étape 2 : Initialiser le flux d’entrée PostScript
Ouvrez le fichier EPS que vous souhaitez convertir. Le flux alimente le document dans Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Étape 3 : Vérifier la licence du document
Vérifiez toujours que la licence à la consommation a été appliquée correctement avant tout traitement.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Étape 4 : Initialiser les options et le dispositif d’image
Créez l’objet d’options qui contrôle les paramètres de conversion ainsi que le dispositif qui recevra l’image rendue.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Étape 5 : Enregistrer le fichier EPS en image
C’est l’appel principal **enregistrer EPS en PNG**. Le document est rendu dans le dispositif d’image à l’aide des options configurées.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Étape 6 : Obtenir et enregistrer les octets de l’image
Extrayez les octets PNG du dispositif et écrivez‑les dans un fichier sur le disque.

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
| **Licence non reconnue** | Les clés sont incorrectes ou placées dans le mauvais ordre. | Revérifiez les chaînes de clé publique/privée et assurez‑vous que `setMeteredKey` est appelé avant tout traitement de document. |
| **Fichier de sortie vide** | `device.getImagesBytes()` a renvoyé `null`. | Vérifiez que le fichier EPS est valide et que les `ImageSaveOptions` ne définissent pas une toile de taille zéro. |
| **OutOfMemoryError sur EPS volumineux** | Le rendu de gros fichiers vectoriels consomme beaucoup de mémoire. | Traitez les pages une à une ou augmentez le tas JVM (`-Xmx2g`). |

## Questions fréquentes

**Q : Comment obtenir les clés publiques et privées à la consommation ?**  
R : Vous pouvez obtenir ces clés via votre compte Aspose.

**Q : La bibliothèque Aspose.Page est‑elle gratuite ?**  
R : Aspose.Page propose à la fois une version d’essai gratuite et des versions payantes. Visitez [ici](https://releases.aspose.com/) pour une version d’essai gratuite.

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Oui, Aspose.Page propose des licences commerciales. Vous pouvez les acheter [ici](https://purchase.aspose.com/buy).

**Q : Où trouver une documentation supplémentaire ?**  
R : Consultez la documentation [ici](https://reference.aspose.com/page/java/).

**Q : Comment obtenir des licences temporaires ?**  
R : Les licences temporaires sont disponibles [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2025-12-03  
**Testé avec :** Aspose.Page 24.12 for Java  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}