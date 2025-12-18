---
date: 2025-12-18
description: Apprenez comment ajouter des métadonnées en insérant des éléments de
  tableau dans les métadonnées XMP des fichiers EPS à l’aide d’Aspose.Page pour Java.
  Suivez notre guide étape par étape.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Comment ajouter des métadonnées – Ajouter des éléments de tableau dans XMP
  (Java)
url: /fr/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des éléments de tableau dans les métadonnées XMP avec Java

## Comment ajouter des métadonnées
Bienvenue dans notre guide pas‑à‑pas sur **comment ajouter des métadonnées** aux fichiers EPS avec Aspose.Page for Java. Dans ce tutoriel, nous vous expliquerons comment ajouter des éléments de tableau aux métadonnées XMP — une exigence courante lorsque vous devez enrichir les informations d’un document telles que les titres ou les créateurs. À la fin, vous comprendrez pourquoi XMP est précieux, comment le manipuler programmétiquement et comment enregistrer le fichier EPS mis à jour.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Page for Java  
- **Quel format de fichier est ciblé ?** EPS (Encapsulated PostScript)  
- **Puis‑je ajouter plusieurs titres ?** Oui, utilisez `xmp.addArrayItem("dc:title", ...)` à plusieurs reprises  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence valide d’Aspose.Page est requise  
- **Le code est‑il compatible avec Java 8+ ?** Absolument, il fonctionne avec toutes les versions modernes de Java  

## Prérequis
Avant de commencer le tutoriel, assurez‑vous de disposer des éléments suivants :
- Bibliothèque Aspose.Page for Java installée.  
- Connaissances de base en programmation Java.  
- Un fichier EPS valide contenant des métadonnées XMP existantes ou des commentaires de métadonnées PS.

## Importer les packages
Pour démarrer, vous devez importer les packages nécessaires pour travailler avec Aspose.Page. Ajoutez les lignes suivantes au début de votre fichier Java :
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Étape 1 : Obtenir les métadonnées XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Dans cette étape, nous récupérons les métadonnées XMP existantes du fichier EPS. Si le fichier EPS ne contient pas déjà de métadonnées XMP, Aspose.Page en génère de nouvelles et les remplit avec les valeurs provenant des commentaires de métadonnées PS.

## Étape 2 : Ajouter l’élément de tableau « dc:title »
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nous ajoutons maintenant un nouvel élément de tableau à la propriété **dc:title** des métadonnées XMP. Remplacez `"NewTitle"` par le titre souhaité.

## Étape 3 : Ajouter l’élément de tableau « dc:creator »
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
De la même façon, nous ajoutons un nouvel élément de tableau à la propriété **dc:creator** des métadonnées XMP. Remplacez `"NewCreator"` par les informations du créateur souhaitées.

## Étape 4 : Initialiser le flux du fichier EPS de sortie
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Préparez le flux du fichier EPS de sortie où le document modifié avec les métadonnées XMP mises à jour sera enregistré.

## Étape 5 : Enregistrer le document avec les métadonnées XMP modifiées
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Enregistrez le document avec les métadonnées XMP mises à jour dans le fichier EPS de sortie.

## Conclusion
Félicitations ! Vous avez appris avec succès **comment ajouter des métadonnées** en insérant des éléments de tableau dans les métadonnées XMP à l’aide d’Aspose.Page for Java. Cette puissante bibliothèque simplifie la manipulation des fichiers EPS et offre de nombreuses fonctionnalités pour le traitement de documents.

## Foire aux questions

### Puis‑je utiliser Aspose.Page for Java avec d’autres formats de documents ?
Oui, Aspose.Page prend en charge divers formats de documents, notamment EPS, PDF et XPS.

### Existe‑t‑il un essai gratuit d’Aspose.Page for Java ?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver la documentation d’Aspose.Page for Java ?
La documentation est disponible [ici](https://reference.aspose.com/page/java/).

### Comment puis‑je acheter Aspose.Page for Java ?
Vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

### Des licences temporaires sont‑elles disponibles pour Aspose.Page for Java ?
Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Questions supplémentaires fréquentes

**Q : Puis‑je ajouter plus d’un élément de tableau à la même propriété ?**  
R : Absolument. Appelez `xmp.addArrayItem` plusieurs fois pour la même propriété afin de constituer une liste de valeurs.

**Q : Cette approche fonctionne‑t‑elle avec des schémas XMP existants autres que Dublin Core ?**  
R : Oui, vous pouvez ajouter des éléments de tableau à n’importe quelle propriété XMP tant que l’espace de noms est correctement référencé.

**Q : Comment vérifier que les métadonnées ont été ajoutées correctement ?**  
R : Ouvrez le fichier EPS résultant dans un visualiseur prenant en charge XMP (par ex., Adobe Bridge) ou extrayez les métadonnées programmatiquement à l’aide des méthodes `XmpMetadata`.

---

**Dernière mise à jour :** 2025-12-18  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}