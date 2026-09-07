---
date: 2026-09-04
description: Apprenez comment réduire la taille des fichiers EPS en recadrant des
  fichiers EPS en Java avec Aspose.Page – un guide étape par étape qui montre comment
  recadrer un EPS, recadrer une image EPS et couper un fichier EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Recadrer un fichier EPS en Java
og_description: Apprenez comment réduire la taille des fichiers EPS en recadrant des
  fichiers EPS en Java avec Aspose.Page – un guide rapide avec du code et des astuces.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Comment recadrer des fichiers EPS en Java pour réduire la taille des fichiers
  EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Comment recadrer des fichiers EPS en Java pour réduire la taille des fichiers
  EPS
url: /fr/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment recadrer les fichiers EPS en Java pour réduire la taille des fichiers EPS

## Introduction
Si vous devez **recadrer des fichiers EPS** de manière programmatique dans une application Java et souhaitez **réduire la taille des fichiers EPS**, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du processus de recadrage d’une image EPS à l’aide de la puissante bibliothèque Aspose.Page for Java. À la fin du guide, vous comprendrez pourquoi le recadrage d’EPS est important, verrez le code exact dont vous avez besoin et serez prêt à intégrer la solution dans vos propres projets.

## Réponses rapides
- **Quelle bibliothèque gère le recadrage EPS en Java ?** Aspose.Page for Java.  
- **Combien de temps faut‑il pour implémenter un recadrage de base ?** Environ 5‑10 minutes.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Quelles versions de Java sont prises en charge ?** Java 8 et supérieures.  
- **Puis‑je définir une boîte englobante personnalisée ?** Oui – vous fournissez les coordonnées dont vous avez besoin.

## Qu’est‑ce que le recadrage EPS et pourquoi l’utiliser ?
**Le recadrage EPS crée une nouvelle boîte englobante qui définit la région visible d’un fichier EPS.**  
Le recadrage d’un fichier EPS supprime les espaces blancs indésirables et ajuste le graphique à la zone réellement nécessaire, ce qui **réduit directement la taille du fichier EPS** et améliore la cohérence de la mise en page dans les documents en aval tels que les PDF ou les rapports.

## Pourquoi recadrer les fichiers EPS ?
Le recadrage des fichiers EPS vous permet de **réduire la taille du fichier jusqu’à 30 %**, d’éliminer les marges excessives et de standardiser les graphiques pour les pipelines de traitement par lots. C’est particulièrement utile lorsque vous devez intégrer de nombreux actifs EPS dans un seul PDF ou lorsque vous souhaitez accélérer le rendu sur des appareils à faible puissance.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir :

- La bibliothèque **Aspose.Page for Java** installée – téléchargez‑la depuis la page officielle [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- Le **Java Development Kit (JDK)** 8 ou supérieur installé sur votre machine.  
- **Un dossier** pour stocker votre EPS d’entrée (`input.eps`) et le fichier recadré résultant (`output_crop.eps`).

## Importer les packages
Tout d’abord, importez les classes Java nécessaires. Cet extrait reste exactement le même que dans le tutoriel original :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Comment recadrer une image EPS en Java
Chargez votre EPS source, définissez une nouvelle boîte englobante et appelez l’API de recadrage – l’opération complète se réalise en cinq étapes concises.

### Étape 1 : définir le répertoire du document et le flux d’entrée
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Ici nous indiquons au code le dossier contenant notre fichier EPS source et ouvrons un flux pour le lire.

### Étape 2 : initialiser l’objet PsDocument
La classe `PsDocument` représente un fichier EPS en mémoire, vous permettant de lire et de modifier ses propriétés.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
L’objet vous donne accès à la boîte englobante originale et à d’autres métadonnées.

### Étape 3 : extraire la boîte englobante initiale
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extraire la boîte englobante originale vous fournit les coordonnées de la zone visible actuelle – pratique pour décider de la quantité à découper.

### Étape 4 : créer le flux de sortie
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Nous ouvrons un flux où l’EPS recadré sera écrit.

### Étape 5 : définir la nouvelle boîte englobante et recadrer
La méthode `cropEps` découpe le document selon une nouvelle boîte englobante et écrit le résultat dans un flux de sortie.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Fournissez les quatre coordonnées (x inférieur‑gauche, y inférieur‑gauche, x supérieur‑droit, y supérieur‑droit) qui définissent la zone à conserver. La méthode effectue le recadrage et écrit le résultat dans `output_crop.eps`.

## Problèmes courants et solutions
- **Coordonnées incorrectes :** EPS utilise des points (1/72 pouce). Si le recadrage semble erroné, revérifiez la conversion d’unité.  
- **Erreurs de fichier introuvable :** Assurez‑vous que `dataDir` se termine par le séparateur de chemin approprié (`/` ou `\`).  
- **Exceptions de licence :** Exécuter le code sans licence valide peut ajouter un filigrane à la sortie. Appliquez votre licence temporaire ou permanente avant l’utilisation en production.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec Java 8 ?**  
R : Oui, Aspose.Page fonctionne avec Java 8 et toute version ultérieure.

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Absolument. Une licence commerciale est requise pour les déploiements en production. Vous pouvez en obtenir une sur la [page d’achat Aspose](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver des ressources supplémentaires et le support communautaire ?**  
R : Consultez le [forum officiel Aspose.Page](https://forum.aspose.com/c/page/39) pour les discussions, exemples de code et astuces de dépannage.

**Q : Existe‑t‑il un essai gratuit disponible pour les tests ?**  
R : Oui, vous pouvez télécharger un essai gratuit d’Aspose.Page depuis la page des versions [Aspose.Page releases page](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour une évaluation à court terme ?**  
R : Une licence temporaire peut être demandée via le portail de licences [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous savez maintenant **comment recadrer des fichiers EPS** en Java en utilisant Aspose.Page pour **réduire la taille des fichiers EPS**. En définissant une boîte englobante personnalisée et en invoquant `cropEps`, vous pouvez éliminer les marges indésirables ou isoler des parties spécifiques d’un graphique EPS avec seulement quelques lignes de code. Intégrez cet extrait dans vos pipelines de traitement de documents plus vastes pour automatiser la manipulation d’EPS, **recadrer les images EPS** et **rogner le contenu des fichiers EPS** efficacement.

---

**Dernière mise à jour :** 2026-09-04  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose

## Tutoriels associés

- [Comment redimensionner les fichiers EPS en Java avec Aspose.Page](/page/java/manipulation-eps/resize/)
- [Convertir EPS en PNG avec Aspose.Page Java (Licence à compteurs)](/page/java/license-management/set-metered-license/)
- [Tutoriel Aspose Page Java – Ajouter des métadonnées XMP aux fichiers EPS](/page/java/xmp-metadata-manipulation/add-metadata/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}