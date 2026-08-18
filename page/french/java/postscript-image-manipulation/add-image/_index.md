---
date: 2026-02-15
description: Apprenez à créer des documents PostScript Java et à générer des fichiers
  de documents PostScript avec la translation et la rotation d'images en utilisant
  Aspose.Page pour Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Créer du PostScript Java – Ajouter une image dans le PostScript Java
url: /fr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer PostScript Java – Ajouter une image dans PostScript Java

## Introduction
Dans ce tutoriel, vous apprendrez comment créer des documents **create postscript java** et intégrer des images à l'aide de la bibliothèque Aspose.Page for Java. Nous parcourrons chaque étape, depuis l'initialisation d'un nouveau fichier PostScript jusqu'à l'application des transformations **translate and rotate image**. À la fin, vous serez capable de générer des fichiers PostScript de manière programmatique et de contrôler le placement des images avec une précision pixel‑par‑pixel — idéal pour les rapports automatisés, les flux d'impression, ou tout scénario où vous devez produire une sortie **generate postscript document** depuis Java.

## Quick Answers
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis-je ajouter plusieurs images ?** Oui – répétez les étapes de transformation et de dessin  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production  
- **Quelle version de Java est prise en charge ?** Java 8 et ultérieure  
- **La rotation d’image est‑elle prise en charge ?** Absolument – utilisez `AffineTransform.rotate()`

## What is create postscript java?
Une opération **create postscript java** produit un fichier de description de page PostScript qui encode du texte, des graphiques vectoriels et des images raster. Avec Aspose.Page, vous pouvez créer ces fichiers directement depuis du code Java, vous offrant un contrôle programmatique complet sur la mise en page, le redimensionnement et la rotation sans avoir besoin d'un interprète PostScript séparé.

## Why use Aspose.Page for image manipulation?
- **API de haut niveau :** Abstrait les commandes PostScript de bas niveau en méthodes Java simples.  
- **Multi‑plateforme :** Fonctionne sur tout système d'exploitation supportant Java.  
- **Contrôle complet de l’état graphique :** Enregistrez, restaurez, translatez, redimensionnez et faites pivoter les graphiques à volonté.  
- **Aucune dépendance externe :** Gère le chargement d'images, la conversion de formats et l'intégration en interne.

## Prerequisites
Avant de plonger dans le code, assurez‑vous d'avoir :

- Java Development Kit (JDK) installé sur votre système.  
- La bibliothèque Aspose.Page for Java. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).  
- Une compréhension de base de la programmation Java.

## Import Packages
Pour commencer, importez les packages nécessaires dans votre projet Java. Utilisez l'extrait de code suivant comme référence :

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Write Graphics Save
La première étape consiste à écrire la sauvegarde graphique dans le document. Cela garantit que toutes les transformations ou modifications effectuées ensuite peuvent être annulées si nécessaire.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Step 2: Translate and Transform (translate and rotate image)
Ensuite, translatez le document et créez un objet `BufferedImage` à partir du fichier image. Appliquez une série de transformations telles que le redimensionnement et la rotation à l'aide de `AffineTransform`. C’est à cet endroit que l’opération **translate and rotate image** se produit.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Step 3: Add Image to Document
Maintenant, ajoutez l'image transformée au document.

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
Après avoir ajouté l'image, écrivez la restauration graphique pour finaliser les modifications apportées.

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
Fermez la page actuelle et enregistrez le document.

```java
document.closePage();
document.save();
```

Vous pouvez répéter ces étapes pour ajouter plusieurs images ou personnaliser les transformations selon vos besoins.

## Common Issues and Solutions
- **FileNotFoundException :** Assurez‑vous que le chemin `dataDir` se termine par un séparateur de fichier (`/` ou `\\`) et que le nom du fichier image correspond exactement.  
- **ImageIO.read renvoie null :** Vérifiez que le format de l'image est pris en charge (par ex., JPEG, PNG).  
- **Angle de rotation incorrect :** `AffineTransform.rotate` attend des radians. Convertissez les degrés en radians (`Math.toRadians(degrees)`) si nécessaire.

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?**  
R : Aspose.Page prend principalement en charge Java, mais des versions sont également disponibles pour d’autres langages de programmation.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où trouver le support communautaire et les discussions liées à Aspose.Page for Java ?**  
R : Visitez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

**Q : Y a‑t‑il des ressources supplémentaires pour acheter Aspose.Page for Java ?**  
R : Vous pouvez acheter la bibliothèque [ici](https://purchase.aspose.com/buy).

## Conclusion
Félicitations ! Vous avez appris avec succès comment **create postscript java** des documents et intégrer des images à l'aide d'Aspose.Page for Java. Explorez la [documentation](https://reference.aspose.com/page/java/) pour découvrir des fonctionnalités avancées, telles que les graphiques vectoriels, le rendu de texte et les tailles de page personnalisées.

---

**Dernière mise à jour :** 2026-02-15  
**Testé avec :** Aspose.Page for Java 23.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}