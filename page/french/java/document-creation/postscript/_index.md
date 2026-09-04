---
date: 2026-06-20
description: Apprenez à définir la taille de page A4, créer des fichiers PostScript
  en Java et ajouter des polices personnalisées avec Aspose.Page. Essayez la version
  d'essai gratuite dès aujourd'hui !
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Créer un document en Java avec PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Comment définir la taille de page A4 et créer du PostScript en Java avec Aspose.Page
url: /fr/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la taille de page A4 et créer du PostScript en Java avec Aspose.Page

## Introduction
Si vous devez **définir la taille de page a4** lors de la génération de fichiers PostScript à partir de Java, Aspose.Page fournit une API rapide et fiable qui masque les détails de bas niveau. Dans ce tutoriel, nous parcourrons l’ensemble du flux de travail — création d’un document PostScript, configuration des dimensions de page A4, et **ajout de polices personnalisées** si nécessaire. À la fin, vous disposerez d’un extrait de code prêt à l’emploi que vous pourrez intégrer à n’importe quel projet Java.

## Réponses rapides
- **Quelle bibliothèque crée du PostScript en Java ?** Aspose.Page for Java.  
- **Quelle taille de page ce guide cible-t-il ?** A4 (210 mm × 297 mm).  
- **Puis-je intégrer mes propres polices ?** Oui – définissez le dossier des polices supplémentaires dans les options d’enregistrement.  
- **Ai-je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible.  
- **Quelles versions de Java sont prises en charge ?** Java 8 et ultérieures.

## Comment définir la taille de page a4 et créer du postscript en Java
Chargez la bibliothèque Aspose.Page, configurez `PsSaveOptions` avec les constantes A4, et écrivez le document dans un fichier — le tout en moins de dix lignes de code. Cette approche directe garantit les dimensions de page correctes et vous permet d’ajouter des polices personnalisées sans configuration supplémentaire.

## Quelle est la taille A4 en PostScript ?
La taille A4 en PostScript correspond à la norme ISO 216 (210 mm × 297 mm) exprimée dans le langage de description de page PostScript. Elle définit la zone imprimable que les imprimantes et les visionneuses interprètent, assurant une mise en page cohérente sur toutes les plateformes. Comme le PostScript décrit le contenu de la page de manière indépendante du dispositif, l’utilisation de la taille A4 garantit que le document apparaîtra de la même façon sur n’importe quelle imprimante ou visionneuse compatible A4 dans le monde.

## Pourquoi utiliser Aspose.Page pour définir la taille de page PostScript ?
Aspose.Page prend en charge **plus de 30 opérateurs PostScript** et peut générer des fichiers jusqu’à **500 Mo** sans charger l’ensemble du document en mémoire. Cela vous offre un contrôle précis des dimensions de page tout en gérant efficacement de lourdes charges de travail. La bibliothèque abstrait également la syntaxe complexe du PostScript, gère automatiquement les ressources et fournit un streaming haute performance, ce qui la rend idéale tant pour de simples flyers d’une page que pour des rapports multi‑pages complexes.

## Comment ajouter des polices personnalisées en Java
Intégrer vos propres polices garantit que le document généré apparaît exactement comme conçu sur n’importe quelle imprimante ou visionneuse, et Aspose.Page découvre automatiquement les polices placées dans le dossier spécifié. En enregistrant un dossier de polices supplémentaire, vous pouvez utiliser n’importe quelle police TrueType ou OpenType, éviter les substitutions de secours et maintenir la cohérence de la marque sur tous les appareils de sortie.

## Prérequis
- Une connaissance pratique de la programmation Java.  
- Aspose.Page pour Java installé. Vous pouvez le télécharger [ici](https://releases.aspose.com/page/java/).  
- Un dossier nommé `necessary_fonts` (ou tout autre nom de votre choix) contenant les polices personnalisées que vous souhaitez intégrer.

## Importer les packages
Dans votre projet Java, importez les classes Aspose.Page requises :

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Maintenant, décomposons l’exemple en étapes numérotées claires.

### Étape 1 : Définir le répertoire du document
La constante `OUTPUT_DIR` indique à la bibliothèque où écrire le fichier généré.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Étape 2 : Définir le dossier des polices
`FONTS_FOLDER` pointe vers le répertoire contenant vos polices TrueType ou OpenType personnalisées.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Étape 3 : Créer le flux de sortie pour le document PostScript
`FileOutputStream` ouvre un flux qui recevra la sortie finale du PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Étape 4 : Créer les options d’enregistrement avec la taille A4
`PsSaveOptions` vous permet de spécifier la taille de page cible.  
**Définition :** `PsPageSize` est une énumération qui contient les constantes de tailles de page standard telles que A4, Letter et Legal.  
Définir `options.setPageSize(PsPageSize.A4)` configure le document avec les dimensions standard A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Étape 5 : Définir les marges de page et ajouter le dossier des polices personnalisées
`options.setMargins(0, 0, 0, 0)` supprime toutes les marges pour une page pleine bordure, et `options.setAdditionalFontsFolder(FONTS_FOLDER)` enregistre vos polices personnalisées.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Étape 6 : Créer un document PS multipage ou monopage
`PsDocument document = new PsDocument(outputStream, options)` crée le document. `PsDocument` représente un document PostScript pouvant contenir une ou plusieurs pages. Définissez `multiPaged` sur `true` pour une sortie multipage.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Étape 7 : Fermer la page actuelle et enregistrer le document
Appeler `document.close()` finalise le fichier et écrit la sortie **PostScript A4 size** sur le disque.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problèmes courants et astuces
- **Police non affichée ?** Vérifiez que le fichier de police est au format TrueType ou OpenType pris en charge et que `FONTS_FOLDER` se termine par une barre oblique (`/`).  
- **Les marges apparaissent toujours ?** Appelez `options.setMargins(...)` **avant** de construire le `PsDocument`.  
- **La sortie multipage apparaît vide ?** N’oubliez pas d’appeler `document.newPage()` pour chaque page supplémentaire dont vous avez besoin.

## Questions fréquemment posées

**Q : Puis-je utiliser des polices personnalisées dans mon document PostScript ?**  
R : Oui, définissez le dossier des polices supplémentaires dans les options d’enregistrement (voir Étape 5) et Aspose.Page intégrera les polices automatiquement.

**Q : Existe-t-il une version d’essai disponible pour Aspose.Page pour Java ?**  
R : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment accéder à la référence complète de l’API ?**  
R : Consultez la documentation [ici](https://reference.aspose.com/page/java/).

**Q : Où puis‑je acheter une licence pour Aspose.Page pour Java ?**  
R : Vous pouvez acheter une licence [ici](https://purchase.aspose.com/buy).

**Q : Où puis‑je demander de l’aide à la communauté ?**  
R : Visitez le forum Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**Q : Puis‑je générer des fichiers PostScript multipages ?**  
R : Absolument — définissez `multiPaged` sur `true` à l’Étape 6 et appelez `document.newPage()` pour chaque page supplémentaire.

## Conclusion
En suivant ces étapes, vous savez maintenant **comment définir la taille de page a4** et créer des fichiers **PostScript** en Java avec Aspose.Page, tout en pouvant **ajouter des polices personnalisées en Java** et contrôler les options de taille de page. Aspose.Page se charge du travail lourd, vous permettant de vous concentrer sur le contenu de vos documents.

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Tutoriel Aspose.Page Java – définir une taille de page personnalisée lors de l’ajout de pages en PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Comment ajouter du texte en PostScript avec Aspose.Page pour Java](/page/java/postscript-text-manipulation/)
- [Tutoriel Aspose Page Java – convertir le PostScript en PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```