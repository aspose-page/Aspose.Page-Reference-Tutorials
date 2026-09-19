---
date: 2026-09-19
description: Apprenez comment ajouter des valeurs nommées XMP aux fichiers EPS en
  utilisant Aspose.Page for Java – un guide étape par étape avec des exemples de code.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Ajouter une valeur nommée dans XMP avec Java
og_description: Comment ajouter des valeurs nommées XMP aux fichiers EPS en utilisant
  Aspose.Page for Java. Suivez ce guide concis pour injecter des métadonnées personnalisées
  en quelques minutes.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Comment ajouter une valeur nommée XMP dans les fichiers EPS avec Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Comment ajouter une valeur nommée XMP dans les fichiers EPS avec Java
url: /fr/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une valeur nommée dans les métadonnées XMP avec Java

## Introduction
Dans le développement Java moderne, apprendre **comment ajouter des métadonnées XMP** à l'intérieur des fichiers EPS est essentiel pour préserver la provenance des documents et améliorer leur recherchabilité. Avec **Aspose.Page for Java**, vous pouvez injecter sans effort des valeurs nommées personnalisées dans le paquet XMP. Ce tutoriel vous guide à travers les étapes exactes — avec des extraits de code — afin que vous puissiez commencer à ajouter des métadonnées XMP à vos documents EPS dès aujourd'hui.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java (Aspose)  
- **Quel type de fichier est ciblé ?** Fichiers EPS contenant des métadonnées XMP  
- **Cas d'utilisation principal ?** Ajouter des valeurs nommées personnalisées (par ex., limites de taille de page) au XMP  
- **Prérequis ?** JDK 8+ et la bibliothèque Aspose.Page for Java  
- **Temps d'implémentation typique ?** 5–10 minutes une fois la bibliothèque configurée  

## Qu'est-ce que Aspose ?
Aspose est le diminutif d'Aspose, une suite d'API qui permet aux développeurs de créer, modifier, convertir et rendre une large gamme de formats de documents sans nécessiter de logiciel externe. Le composant Aspose.Page for Java se concentre spécifiquement sur le traitement PostScript et EPS, offrant un accès programmatique au contenu des pages, aux graphiques et aux métadonnées telles que XMP.

## Pourquoi ajouter des valeurs nommées aux métadonnées XMP ?
Les valeurs nommées vous permettent de stocker des paires clé‑valeur arbitraires directement dans le paquet XMP, les rendant instantanément lisibles par les outils en aval. Cela améliore la compatibilité avec les moteurs de recherche, permet l'automatisation des flux de travail et satisfait les exigences de conformité en intégrant des informations réglementaires sans altérer le contenu visuel.

## Pourquoi cela importe
L'ajout de valeurs nommées aux métadonnées XMP vous permet de stocker des paires clé‑valeur arbitraires qui peuvent être lues sans analyser l'intégralité du fichier EPS. Cette capacité est particulièrement précieuse dans les pipelines de publication automatisés, les systèmes de gestion d'actifs numériques et les flux de travail axés sur la conformité où les métadonnées pilotent les actions en aval.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- **Kit de développement Java (JDK) :** Un JDK récent (8 ou supérieur) installé sur votre machine.  
- **Bibliothèque Aspose.Page for Java :** Téléchargez‑la depuis le [téléchargement officiel d'Aspose.Page for Java](https://releases.aspose.com/page/java/). Ajoutez le JAR au classpath de votre projet.  
- **Un fichier EPS** qui contient déjà des métadonnées XMP ou qui les générera automatiquement.

## Importer les packages
Commencez par importer les packages Java nécessaires. Ces imports vous donnent accès aux flux de fichiers, au modèle de document EPS et aux classes de gestion XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Comment ajouter une valeur nommée XMP dans les fichiers EPS avec Java
Pour ajouter une valeur nommée, chargez le fichier EPS avec un `FileInputStream`, récupérez ou créez son objet `XmpMetadata`, insérez la `NamedValue` souhaitée dans l'espace de noms approprié, puis écrivez le document modifié à l'aide d'un `FileOutputStream`. Aspose.Page gère automatiquement la création du paquet XMP s'il est absent, garantissant que les nouvelles métadonnées sont correctement intégrées.

### Étape 1 : Initialiser le flux du fichier EPS d'entrée
**FileInputStream** est une classe I/O Java qui lit les octets bruts d'un fichier. Chargez le fichier EPS source dans un `FileInputStream`. Ce flux alimente le document dans l'API d'Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Conseil :** Gardez la variable `dataDir` configurable afin que le même code fonctionne dans différents environnements.

### Étape 2 : Obtenir les métadonnées XMP
**XmpMetadata** représente le paquet XMP associé à un document EPS. Récupérez le paquet XMP existant ; si le fichier EPS n'en possède pas, Aspose crée un nouvel objet XMP à partir des commentaires PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Étape 3 : Ajouter une valeur nommée
**NamedValue** est une paire clé‑valeur stockée dans l'espace de noms des métadonnées XMP. Insérez une valeur nommée personnalisée dans la structure XMP. Dans cet exemple, nous ajoutons une nouvelle clé sous l'espace de noms `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Pourquoi c'est important :** Les valeurs nommées vous permettent de stocker des paires clé‑valeur arbitraires que les applications en aval peuvent lire sans analyser le document complet.

### Étape 4 : Initialiser le flux du fichier EPS de sortie
**FileOutputStream** est une classe I/O Java qui écrit des octets bruts dans un fichier. Préparez un `FileOutputStream` où le EPS modifié sera enregistré.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Étape 5 : Enregistrer le document
La méthode `save` persiste les modifications. Elle écrit le paquet XMP mis à jour dans le fichier EPS, garantissant que la nouvelle valeur nommée fait partie des métadonnées du document.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Étape 6 : Fermer le flux du fichier EPS d'entrée
Fermer le descripteur de fichier d'origine évite les fuites de ressources et assure que le fichier n'est pas verrouillé pour les opérations ultérieures.

```java
psStream.close();
```

En suivant ces six étapes, vous avez réussi à **ajouter une valeur nommée dans les métadonnées XMP** avec **Aspose.Page for Java**.

## Problèmes courants & solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| `NullPointerException` sur `xmp` | Le fichier EPS ne contient pas de XMP et Aspose n'a pas pu en générer un | Assurez‑vous que le EPS contient au moins un commentaire PS ou créez manuellement une nouvelle instance `XmpMetadata`. |
| Le fichier de sortie est vide | Le flux de sortie n'est pas flushé/fermé | Vérifiez que `outPsStream.close()` est appelé dans un bloc `finally` (comme montré). |
| Erreur de clé dupliquée | La même valeur nommée a été ajoutée deux fois | Vérifiez si la clé existe déjà avec `xmp.containsNamedValue(...)` avant d'ajouter. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for Java avec d'autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçu pour fonctionner de manière transparente avec d'autres bibliothèques Java, offrant une flexibilité dans votre environnement de développement.

**Q : Une version d'essai gratuite est‑elle disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Page for Java sur la [page des releases Aspose](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Visitez la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour Aspose.Page for Java.

**Q : Où puis‑je trouver plus de tutoriels et d'exemples pour Aspose.Page for Java ?**  
R : Explorez la [documentation](https://reference.aspose.com/page/java/) pour des tutoriels et exemples complets.

**Q : Aspose.Page for Java convient‑il aux projets à grande échelle ?**  
R : Absolument, Aspose.Page for Java est conçu pour gérer efficacement les projets à grande échelle, offrant des capacités robustes de manipulation de documents.

## Conclusion
Dans ce guide, nous avons démontré comment **Aspose.Page for Java** simplifie l'**ajout de valeurs nommées aux métadonnées XMP** dans les fichiers EPS. Avec les étapes ci‑dessus, vous pouvez enrichir vos documents de métadonnées personnalisées, améliorer leur recherchabilité et permettre un traitement en aval plus intelligent.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutoriels associés

- [Comment ajouter un espace de noms XMP dans les fichiers EPS avec Aspose.Page – Tutoriel Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Ajouter des métadonnées XMP aux fichiers EPS avec Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Lire le XMP avec Aspose.Page – Guide Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}