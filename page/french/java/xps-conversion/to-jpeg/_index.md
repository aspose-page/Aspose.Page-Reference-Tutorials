---
date: 2025-12-23
description: Apprenez à convertir XPS en JPEG en Java et découvrez comment convertir
  les fichiers XPS efficacement à l’aide d’Aspose.Page. Un guide complet avec des
  instructions étape par étape pour une intégration fluide.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Comment convertir XPS en JPEG en Java
url: /fr/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir XPS en JPEG avec Java

## Introduction
Dans ce tutoriel, **vous apprendrez comment convertir XPS en JPEG** en utilisant la puissante bibliothèque Aspose.Page pour Java. La conversion de fichiers XPS en formats d’image est une exigence courante lorsque vous devez afficher, prévisualiser ou traiter davantage les pages de documents dans des applications web ou de bureau. Nous parcourrons chaque étape, expliquerons pourquoi chaque ligne est importante et vous donnerons des conseils pratiques afin que vous puissiez intégrer la logique de conversion dans vos propres projets en toute confiance.

## Réponses rapides
- **Quelle bibliothèque gère la conversion ?** Aspose.Page for Java  
- **Puis‑je sélectionner des pages spécifiques ?** Oui – utilisez `setPageNumbers` dans `JpegSaveOptions`  
- **Quelle qualité d’image puis‑je contrôler ?** Mode de lissage, résolution et paramètres de qualité JPEG  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise (un essai gratuit est disponible)  
- **Le code est‑il compatible Java 8 ?** Absolument – l’API fonctionne avec Java 8 et versions ultérieures  

## Qu’est‑ce que le XPS et pourquoi le convertir en JPEG ?
XPS (XML Paper Specification) est un format de document à mise en page fixe similaire au PDF. Convertir XPS en JPEG est utile lorsque vous avez besoin d’images raster pour des miniatures, des pièces jointes d’e‑mail ou lors de l’intégration avec des systèmes qui n’acceptent que des fichiers image. JPEG offre un bon équilibre entre qualité visuelle et taille de fichier, ce qui le rend idéal pour les aperçus web.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de :

- **Environnement de développement Java** – JDK 8 ou version ultérieure installé et configuré.  
- **Aspose.Page for Java** – Téléchargez la dernière bibliothèque depuis le site officiel **[ici](https://releases.aspose.com/page/java/)**.  
- **Document XPS d’exemple** – Un fichier XPS que vous souhaitez transformer en images JPEG.  

## Importer les packages
Commencez par importer les classes nécessaires dans votre fichier source Java :

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Étape 1 : Initialiser chemins et charger le document XPS
Définissez le répertoire contenant votre fichier XPS source et créez une instance `XpsDocument` :

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Astuce :** Utilisez `Paths.get()` de `java.nio.file` pour une gestion des chemins indépendante de la plateforme.

## Étape 2 : Configurer les options d’enregistrement JPEG
Définissez comment les images JPEG doivent être rendues — résolution, lissage et pages à exporter :

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` produit une sortie haute résolution adaptée à l’impression.  
- `setPageNumbers` vous permet de ne choisir que les pages dont vous avez besoin, économisant ainsi du temps et de la mémoire.

## Étape 3 : Créer le dispositif de rendu
Le `ImageDevice` capture les pages rendues sous forme de tableaux d’octets :

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Étape 4 : Rendre le document XPS en JPEG
Appelez la méthode `save`, en passant le dispositif et les options que vous avez configurées :

```java
document.save(device, options);
```

À ce stade, le `device` contient un tableau à deux dimensions où chaque élément représente une page encodée en JPEG.

## Étape 5 : Parcourir le résultat et écrire les fichiers
Bouclez sur les pages rendues et écrivez chaque tableau d’octets dans un fichier JPEG distinct :

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Chaque fichier sera nommé `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, ce qui facilite l’identification du document source et du numéro de page.

## Problèmes courants & Dépannage
| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| **Fichiers JPEG vides** | Le flux de sortie n'est pas correctement vidé ou fermé | Assurez‑vous que `imageStream.close()` est appelé à l'intérieur de la boucle interne (comme indiqué). |
| **Erreurs de mémoire insuffisante sur de gros fichiers XPS** | Le rendu de toutes les pages en même temps consomme trop de RAM | Traitez les pages par lots plus petits ou augmentez le tas JVM (`-Xmx`). |
| **Pages manquantes** | `setPageNumbers` n'inclut pas la page souhaitée | Vérifiez que le tableau des numéros de page correspond aux indices réels des pages XPS (basé sur 1). |

## Foire aux questions

### Q : Aspose.Page convient‑il aux projets commerciaux ?
R : Oui, Aspose.Page est un produit commercial avec des options de licence disponibles. Consultez **[ici](https://purchase.aspose.com/buy)** pour plus de détails.

### Q : Puis‑je essayer Aspose.Page avant d'acheter ?
R : Oui, vous pouvez obtenir un essai gratuit **[ici](https://releases.aspose.com/)**.

### Q : Où puis‑je trouver la documentation d'Aspose.Page ?
R : La documentation est disponible **[ici](https://reference.aspose.com/page/java/)**.

### Q : Comment obtenir du support pour Aspose.Page ?
R : Visitez le **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** pour un support communautaire.

### Q : Ai‑je besoin d'une licence temporaire pour les tests ?
R : Oui, vous pouvez obtenir une licence temporaire **[ici](https://purchase.aspose.com/temporary-license/)**.

## Conclusion
Vous avez maintenant maîtrisé **comment convertir XPS en JPEG** en utilisant Aspose.Page pour Java. En suivant ce guide pas à pas, vous pouvez intégrer ce pipeline de conversion dans n’importe quelle application Java — qu’il s’agisse d’un outil de bureau, d’un service web ou d’une utilité de traitement par lots. N’hésitez pas à expérimenter avec différentes résolutions, sélections de pages et formats d’image pour répondre aux besoins de votre projet.

---

**Dernière mise à jour :** 2025-12-23  
**Testé avec :** Aspose.Page 24.11 for Java (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}