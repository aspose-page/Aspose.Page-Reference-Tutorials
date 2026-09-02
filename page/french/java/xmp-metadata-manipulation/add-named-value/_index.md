---
date: 2026-05-05
description: Apprenez comment ajouter des valeurs nommées XMP aux fichiers EPS à l'aide
  d'Aspose.Page pour Java – un guide étape par étape avec des exemples de code.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Ajouter une valeur nommée dans XMP avec Java
second_title: Aspose.Page Java API
title: Comment ajouter une valeur nommée XMP dans les fichiers EPS en Java
url: /fr/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une valeur nommée dans les métadonnées XMP avec Java

## Introduction
Dans le développement Java moderne, apprendre **comment ajouter des métadonnées XMP** dans les fichiers EPS est essentiel pour préserver la provenance des documents et améliorer leur recherchabilité. Avec **asp** (Aspose.Page for Java), vous pouvez injecter facilement des valeurs nommées personnalisées dans le paquet XMP. Ce tutoriel vous guide à travers les étapes exactes — avec des extraits de code — afin que vous puissiez commencer à ajouter des métadonnées XMP à vos documents EPS dès aujourd'hui.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java (asp)  
- **Quel type de fichier est ciblé ?** Fichiers EPS contenant des métadonnées XMP  
- **Cas d'utilisation principal ?** Ajouter des valeurs nommées personnalisées (p. ex., limites de taille de page) au XMP  
- **Prérequis ?** JDK 8+ et la bibliothèque Aspose.Page for Java  
- **Temps d'implémentation typique ?** 5–10 minutes une fois la bibliothèque configurée  

## Qu'est-ce que asp ?
*asp* est la forme courte de **Aspose**, une famille d'API .NET et Java qui simplifient le traitement de documents. Le composant Aspose.Page for Java vous permet de créer, modifier et convertir des fichiers PostScript et EPS tout en offrant un accès programmatique complet à leurs métadonnées, y compris XMP.

## Pourquoi ajouter des valeurs nommées aux métadonnées XMP ?
- **Facilité pour les moteurs de recherche :** Les balises personnalisées améliorent la découvrabilité.  
- **Automatisation du flux de travail :** Les outils en aval peuvent lire vos valeurs personnalisées pour prendre des décisions.  
- **Conformité :** Intégrer les informations réglementaires directement dans le paquet du document.  

## Pourquoi cela importe
Ajouter des valeurs nommées au XMP vous permet de stocker des paires clé‑valeur arbitraires qui peuvent être lues sans analyser l'intégralité du fichier EPS. Cette capacité est particulièrement précieuse dans les pipelines de publication automatisés, les systèmes de gestion d'actifs numériques et les flux de travail guidés par la conformité où les métadonnées pilotent les actions en aval.

## Prérequis
Avant de commencer, assurez‑vous de disposer de ce qui suit :

- **Java Development Kit (JDK) :** Un JDK récent (8 ou supérieur) installé sur votre machine.  
- **Bibliothèque Aspose.Page for Java :** Téléchargez‑la depuis le [download link](https://releases.aspose.com/page/java/). Ajoutez le JAR au classpath de votre projet.  
- **Un fichier EPS** qui contient déjà des métadonnées XMP ou qui les générera automatiquement.

## Importer les packages
Commencez par importer les packages Java nécessaires. Ces importations vous donnent accès aux flux de fichiers, au modèle de document EPS et aux classes de gestion du XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Comment ajouter une valeur nommée XMP dans les fichiers EPS avec Java
Ci-dessous se trouve un guide concis et numéroté qui montre exactement **comment ajouter des valeurs nommées XMP** à un document EPS.

### Étape 1 : Initialiser le flux de fichier EPS d'entrée
Chargez le fichier EPS source dans un `FileInputStream`. Ce flux alimente le document dans l'API d'Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Astuce :** Gardez la variable `dataDir` configurable afin que le même code fonctionne dans différents environnements.

### Étape 2 : Obtenir les métadonnées XMP
Récupérez le paquet XMP existant. Si le fichier EPS n'en possède pas, Aspose crée un nouvel objet XMP rempli à partir des commentaires PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Étape 3 : Ajouter une valeur nommée
Insérez une valeur nommée personnalisée dans la structure XMP. Dans cet exemple, nous ajoutons une nouvelle clé sous l'espace de noms `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Pourquoi c'est important :** Les valeurs nommées vous permettent de stocker des paires clé‑valeur arbitraires que les applications en aval peuvent lire sans analyser le document complet.

### Étape 4 : Initialiser le flux de fichier EPS de sortie
Préparez un `FileOutputStream` où l'EPS modifié sera enregistré.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Étape 5 : Enregistrer le document
Conservez les modifications. L'appel `save` écrit le paquet XMP mis à jour dans le fichier EPS.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Étape 6 : Fermer le flux EPS d'entrée
Libérez le descripteur de fichier original pour éviter les fuites de ressources.

```java
psStream.close();
```

En suivant ces six étapes, vous avez réussi à **ajouter une valeur nommée dans les métadonnées XMP** en utilisant **asp** (Aspose.Page for Java).

## Problèmes courants et solutions
| Problème | Cause | Solution |
|-------|-------|-----|
| `NullPointerException` sur `xmp` | Le fichier EPS ne contient pas de XMP et Aspose n'a pas pu en générer un | Assurez‑vous que l'EPS contient au moins un commentaire PS ou créez manuellement une nouvelle instance `XmpMetadata`. |
| Le fichier de sortie est vide | Le flux de sortie n'est pas vidé/fermé | Vérifiez que `outPsStream.close()` est appelé dans un bloc `finally` (comme indiqué). |
| Erreur de clé dupliquée | La même valeur nommée a été ajoutée deux fois | Vérifiez si la clé existe déjà avec `xmp.containsNamedValue(...)` avant d'ajouter. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for Java avec d'autres bibliothèques Java ?**  
R : Oui, Aspose.Page for Java est conçu pour fonctionner de manière transparente avec d'autres bibliothèques Java, offrant une flexibilité dans votre environnement de développement.

**Q : Une version d'essai gratuite est‑elle disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Page for Java [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour Aspose.Page for Java.

**Q : Où puis‑je trouver plus de tutoriels et d'exemples pour Aspose.Page for Java ?**  
R : Consultez la [documentation](https://reference.aspose.com/page/java/) pour des tutoriels et exemples complets.

**Q : Aspose.Page for Java convient‑il aux projets à grande échelle ?**  
R : Absolument, Aspose.Page for Java est conçu pour gérer efficacement les projets à grande échelle, offrant des capacités de manipulation de documents robustes.

## Conclusion
Dans ce guide, nous avons montré comment **asp** (Aspose.Page for Java) facilite l'**ajout de valeurs nommées aux métadonnées XMP** dans les fichiers EPS. Avec les étapes ci‑dessus, vous pouvez enrichir vos documents avec des métadonnées personnalisées, améliorer leur recherchabilité et permettre un traitement en aval plus intelligent.

---

**Dernière mise à jour :** 2026-05-05  
**Testé avec :** Aspose.Page for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}