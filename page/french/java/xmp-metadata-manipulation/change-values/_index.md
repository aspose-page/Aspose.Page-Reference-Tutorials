---
title: Modifier les valeurs dans XMP à l'aide de Java
linktitle: Modifier les valeurs dans XMP à l'aide de Java
second_title: API Java Aspose.Page
description: Améliorez les documents EPS avec Aspose.Page pour Java. Modifiez sans effort les métadonnées XMP pour un contenu personnalisé et professionnel. #JavaDéveloppement
type: docs
weight: 17
url: /fr/java/xmp-metadata-manipulation/change-values/
---
## Introduction
Dans le domaine du traitement et de la manipulation de documents, Aspose.Page pour Java s'impose comme un outil puissant. Ce didacticiel explore le processus de modification des valeurs XMP (Extensible Metadata Platform) dans les documents EPS (Encapsulated PostScript) à l'aide de Java avec la bibliothèque Aspose.Page. En suivant le guide étape par étape fourni, vous apprendrez comment modifier sans effort les métadonnées, garantissant ainsi que vos documents sont adaptés à vos besoins spécifiques.
## Conditions préalables
Avant de commencer ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Environnement de développement Java : assurez-vous de disposer d'un environnement de développement Java fonctionnel sur votre machine.
2.  Bibliothèque Aspose.Page pour Java : téléchargez et installez la bibliothèque Aspose.Page pour Java. Vous pouvez trouver le package nécessaire[ici](https://releases.aspose.com/page/java/).
## Importer des packages
Commencez par importer les packages requis dans votre projet Java. Ces packages sont essentiels pour interagir et manipuler les documents EPS.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Étape 1 : Obtenez les métadonnées XMP
Récupérez les métadonnées XMP du document EPS. Si le fichier EPS ne contient pas de métadonnées XMP, un nouveau fichier sera créé avec les valeurs des commentaires de métadonnées PS telles que %%Creator, %%CreateDate et %%Title.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Initialiser le flux de fichiers EPS d'entrée
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Obtenez les métadonnées XMP. Si le fichier EPS ne contient pas de métadonnées XMP, un nouveau fichier est créé avec les valeurs des commentaires de métadonnées PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Étape 2 : Modifier la valeur « ModifyDate »
Modifiez la valeur "ModifyDate" dans les métadonnées XMP pour refléter la date souhaitée.
```java
// Changer la valeur "ModifyDate"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Étape 3 : Modifier la valeur « Créateur »
Mettez à jour la valeur "Créateur" dans les métadonnées XMP pour spécifier le créateur du document.
```java
// Changer la valeur "créateur"
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Étape 4 : Modifier la valeur « Titre »
Modifiez la valeur "Titre" dans les métadonnées XMP pour définir un titre approprié pour le document.
```java
//Changer la valeur du "titre"
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Étape 5 : Enregistrer le document avec les métadonnées XMP modifiées
Enregistrez le document avec les métadonnées XMP mises à jour dans un nouveau fichier EPS.
```java
// Initialiser le flux de fichiers EPS de sortie
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Enregistrer le document avec les métadonnées XMP modifiées
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusion
Toutes nos félicitations! Vous avez suivi avec succès le processus de modification des valeurs XMP dans les documents EPS à l'aide d'Aspose.Page pour Java. Ce didacticiel vous a doté des connaissances nécessaires pour modifier les métadonnées, garantissant ainsi que vos documents correspondent parfaitement à vos exigences spécifiques.
## FAQ
### Q : Comment puis-je gérer les considérations de fuseau horaire lors de la modification des valeurs XMP ?
 Utiliser`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` pour garantir la cohérence des paramètres de fuseau horaire.
### Q : Puis-je modifier plusieurs valeurs XMP en une seule opération ?
 Oui, en utilisant le`put` méthode pour chaque valeur souhaitée, vous pouvez modifier plusieurs valeurs XMP simultanément.
### Q : Où puis-je trouver de la documentation supplémentaire pour Aspose.Page pour Java ?
 Explorez la documentation complète[ici](https://reference.aspose.com/page/java/).
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Page pour Java ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour Java ?
 Obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).