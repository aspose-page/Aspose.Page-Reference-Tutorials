---
date: 2025-12-09
description: Apprenez à créer un document PostScript en Java et à translater et faire
  pivoter une image en utilisant Aspose.Page pour une manipulation d'image fluide.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Créer un document PostScript en Java – Ajouter une image dans le PostScript
  Java
url: /fr/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document PostScript Java – Ajouter une image dans PostScript Java

## Introduction
Dans ce tutoriel, vous apprendrez comment **créer un document PostScript Java** et intégrer des images en utilisant la bibliothèque Aspose.Page for Java. Nous parcourrons chaque étape, de la configuration du document à l'application de transformations comme les opérations **translate and rotate image**. À la fin, vous serez capable de générer des fichiers PostScript riches de manière programmatique et de personnaliser le placement des images pour répondre exactement à vos besoins de mise en page.

## Quick Answers
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis-je ajouter plusieurs images ?** Oui – répétez les étapes de transformation et de dessin  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit fonctionne pour les tests ; une licence est requise pour la production  
- **Quelle version de Java est prise en charge ?** Java 8 et ultérieure  
- **La rotation d’image est‑elle prise en charge ?** Absolument – utilisez `AffineTransform.rotate()`

## Qu’est‑ce que la création d’un document PostScript en Java ?
Un document PostScript est un fichier de langage de description de page qui décrit le texte, les graphiques et les images. En utilisant Aspose.Page, vous pouvez générer ces fichiers de manière programmatique en Java, vous offrant un contrôle complet sur la mise en page, l’état graphique et la gestion des images sans avoir besoin d’un interpréteur PostScript.

## Pourquoi utiliser Aspose.Page pour la manipulation d’images ?
- **API de haut niveau :** simplifie les commandes PostScript complexes.  
- **Multiplateforme :** fonctionne sur tout OS supportant Java.  
- **Contrôle complet de l’état graphique :** sauvegarde, restauration, translation, mise à l’échelle et rotation des graphiques facilement.  
- **Aucune dépendance externe :** gère le chargement et la conversion d’images en interne.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir :

- Java Development Kit (JDK) installé sur votre système.  
- Aspose.Page for Java library. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).  
- Une compréhension de base de la programmation Java.  

## Import Packages
Pour commencer, importez les packages nécessaires dans votre projet Java. Utilisez le fragment de code suivant comme référence :

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Étape 1 : Écrire la sauvegarde graphique
La première étape consiste à écrire la sauvegarde graphique dans le document. Cela garantit que toutes les transformations ou modifications effectuées ultérieurement peuvent être annulées si nécessaire.

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

## Étape 2 : Translation et transformation (translate and rotate image)
Ensuite, translatez le document et créez un objet `BufferedImage` à partir du fichier image. Appliquez une série de transformations telles que le redimensionnement et la rotation à l’aide de `AffineTransform`. C’est à cet endroit que l’opération **translate and rotate image** se produit.

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

## Étape 3 : Ajouter l’image au document
Maintenant, ajoutez l’image transformée au document.

```java
document.drawImage(image, transform, null);
```

## Étape 4 : Écrire la restauration graphique
Après avoir ajouté l’image, écrivez la restauration graphique pour finaliser les modifications apportées.

```java
document.writeGraphicsRestore();
```

## Étape 5 : Fermer la page actuelle et enregistrer
Fermez la page actuelle et enregistrez le document.

```java
document.closePage();
document.save();
```

Vous pouvez répéter ces étapes pour ajouter plusieurs images ou personnaliser les transformations selon vos besoins.

## Problèmes courants et solutions
- **FileNotFoundException :** Assurez‑vous que le chemin `dataDir` se termine par un séparateur de fichiers (`/` ou `\\`) et que le nom du fichier image correspond exactement.  
- **ImageIO.read renvoie null :** Vérifiez que le format de l’image est pris en charge (par ex., JPEG, PNG).  
- **Angle de rotation incorrect :** `AffineTransform.rotate` attend des radians. Convertissez les degrés en radians (`Math.toRadians(degrees)`) si nécessaire.  

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?**  
R : Aspose.Page prend principalement en charge Java, mais des versions sont également disponibles pour d’autres langages de programmation.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver du support communautaire et des discussions liées à Aspose.Page for Java ?**  
R : Consultez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

**Q : Existe‑t‑il des ressources supplémentaires pour l’achat d’Aspose.Page for Java ?**  
R : Vous pouvez acheter la bibliothèque [ici](https://purchase.aspose.com/buy).

## Conclusion
Félicitations ! Vous avez appris avec succès comment **créer un document PostScript Java** et intégrer des images en utilisant Aspose.Page for Java. Explorez la [documentation](https://reference.aspose.com/page/java/) pour des fonctionnalités avancées, telles que les graphiques vectoriels, le rendu de texte et les tailles de page personnalisées.

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Page for Java 23.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}