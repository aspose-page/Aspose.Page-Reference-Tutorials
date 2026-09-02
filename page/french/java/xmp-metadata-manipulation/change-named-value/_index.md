---
date: 2026-05-15
description: Apprenez à modifier les métadonnées XMP et à changer les valeurs XMP
  dans les fichiers EPS avec Aspose.Page for Java – un guide clair étape par étape.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Modifier la valeur nommée dans XMP avec Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: comment modifier xmp – Modifier la valeur nommée dans XMP avec Java
url: /fr/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# comment modifier xmp – Modifier une valeur nommée dans XMP avec Java

Dans les flux de travail modernes de documents, **Aspose.Page for Java** facilite la lecture, la modification et l'écriture des métadonnées XMP à l'intérieur des fichiers EPS. **Ce tutoriel montre comment modifier les métadonnées xmp** dans les documents EPS en utilisant l'API Aspose.Page, afin que vous puissiez garder les informations de vos documents précises, recherchables et conformes aux normes de l'industrie. Que vous mettiez à jour les dimensions de la page, les informations de l'auteur ou des balises personnalisées, les étapes ci‑dessous vous guident à travers le processus en Java.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Modification d'une valeur XMP nommée dans un fichier EPS avec Aspose.Page for Java.  
- **Quelle version de la bibliothèque est requise ?** Toute version récente d'Aspose.Page for Java (l'API est stable depuis plusieurs années).  
- **Ai-je besoin d'une licence ?** Une licence temporaire ou complète est requise pour la production ; un essai gratuit fonctionne pour les tests.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un développeur familier avec Java I/O.  
- **Puis-je l'utiliser avec d'autres formats de fichiers ?** L'API XMP est également disponible pour PDF, SVG et d'autres formats pris en charge par Aspose.Page.

## Qu'est-ce que les métadonnées XMP ?
XMP (Extensible Metadata Platform) est un format standardisé basé sur XML pour intégrer des métadonnées riches — telles que le créateur, le titre et des propriétés personnalisées — directement dans les fichiers. Dans les documents EPS, le XMP coexiste avec les commentaires PostScript traditionnels, permettant aux applications de lire et de modifier les métadonnées sans altérer le contenu visuel.

## Pourquoi utiliser Aspose.Page for Java pour modifier le XMP ?
Aspose.Page vous offre **un contrôle complet sur plus de 150 propriétés de schéma XMP** et fonctionne de manière cohérente sur les formats EPS, PDF et SVG. Il traite des fichiers jusqu'à **500 Mo** sans charger le document entier en mémoire, et il inclut une validation intégrée qui garantit que l'EPS résultant reste conforme aux normes. Aucun analyseur XML externe ni bibliothèque native n'est requis.

## Introduction
Aspose.Page for Java est une bibliothèque robuste qui facilite la manipulation et le traitement des fichiers EPS. En ce qui concerne la gestion des métadonnées XMP au sein de ces fichiers, Aspose.Page donne aux développeurs un ensemble complet de fonctionnalités. Dans ce tutoriel, nous nous concentrerons sur la modification d'une valeur nommée dans le XMP, offrant un guide clair et concis aux développeurs souhaitant améliorer leurs capacités de traitement de documents.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d'avoir les prérequis suivants en place :
1. **Environnement de développement Java** – Un JDK (8 ou supérieur) et un IDE ou un outil de construction (Maven/Gradle).  
2. **Bibliothèque Aspose.Page for Java** – Téléchargez et intégrez la bibliothèque Aspose.Page for Java dans votre projet. Vous pouvez trouver la bibliothèque et la documentation détaillée [ici](https://reference.aspose.com/page/java/).  
3. **Fichier EPS d'exemple** – Disposez d'un fichier EPS d'exemple prêt pour l'expérimentation. Si vous n'en avez pas, utilisez le fichier d'exemple fourni nommé **"xmp4.eps."**

## Importer les packages
Les instructions `import` importent les classes essentielles d'Aspose.Page dans le scope.

La classe `PsDocument` est l'objet principal d'Aspose.Page qui représente un document EPS en mémoire.  
La classe `XmpMetadata` fournit l'accès au paquet XMP intégré dans le fichier EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Comment modifier les métadonnées XMP ?
Chargez le fichier EPS, récupérez son paquet XMP, modifiez la propriété souhaitée et enregistrez le document — le tout en quelques lignes simples. Cette approche fonctionne pour toute valeur XMP nommée, qu'il s'agisse d'un champ Dublin Core standard ou d'un espace de noms personnalisé que vous avez défini.

## Étape 1 : Initialiser le flux du fichier EPS d'entrée
`FileInputStream` ouvre un flux en lecture seule vers le fichier EPS source, permettant à Aspose.Page d'ingérer le document sans verrouiller le système de fichiers.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Étape 2 : Initialiser PsDocument
`PsDocument` est l'objet principal qui encapsule le contenu EPS et fournit l'accès à ses métadonnées, pages et ressources.

```java
PsDocument document = new PsDocument(psStream);
```

## Étape 3 : Obtenir les métadonnées XMP
`XmpMetadata` représente le paquet XMP à l'intérieur du fichier EPS et offre des méthodes pour lire, modifier ou supprimer des propriétés individuelles.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 4 : Définir une nouvelle valeur dans le XMP
`setProperty` définit la valeur d'une propriété XMP spécifiée dans le paquet de métadonnées.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Étape 5 : Initialiser le flux du fichier EPS de sortie
`FileOutputStream` crée un flux en écriture pour enregistrer le fichier EPS modifié.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Étape 6 : Enregistrer le document avec les métadonnées XMP modifiées
`save` écrit le PsDocument en mémoire, incluant le XMP mis à jour, vers le flux de sortie.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Étape 7 : Fermer le flux du fichier EPS d'entrée
`close` libère le handle du fichier et libère les ressources associées au flux d'entrée.

```java
// Close input EPS stream
psStream.close();
```

## Problèmes courants et solutions
- **FileNotFoundException** – Vérifiez que `dataDir` pointe vers le bon dossier et que `xmp4.eps` existe.  
- **LicenseException** – Si vous rencontrez des erreurs de licence, assurez‑vous qu'un fichier de licence Aspose.Page valide est chargé avant de créer `PsDocument`.  
- **Metadata Not Updated** – Après l'enregistrement, ouvrez l'EPS résultant dans un visualiseur de métadonnées (par ex., Adobe Bridge) pour confirmer que la nouvelle valeur apparaît.

## Questions fréquemment posées
**Q : Puis‑je utiliser Aspose.Page for Java avec d'autres langages de programmation ?**  
R : Aspose.Page prend principalement en charge Java, mais Aspose propose des bibliothèques équivalentes pour .NET, C++ et Python qui offrent des capacités similaires de manipulation du XMP.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez explorer un essai gratuit d'Aspose.Page for Java [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver un support supplémentaire et des discussions sur Aspose.Page for Java ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.Page for Java ?**  
R : Pour acheter Aspose.Page for Java, visitez la [page d'achat](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-05-15  
**Testé avec :** Aspose.Page for Java (latest release)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment lire les métadonnées XMP avec Java – Guide Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutoriel Aspose Page Java – Ajouter des métadonnées XMP aux fichiers EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modifier xmp – Modifier les valeurs du XMP avec Java](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}