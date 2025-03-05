---
title: Intégration sans effort de licences mesurées avec Aspose.Page Java
linktitle: Définir une licence limitée en Java
second_title: API Java Aspose.Page
description: Découvrez l'intégration transparente d'Aspose.Page avec Java. Configurez facilement des licences limitées et améliorez vos capacités de traitement de documents.
type: docs
weight: 10
url: /fr/java/license-management/set-metered-license/
---
## Introduction
Bienvenue dans notre guide complet sur la configuration d'une licence limitée en Java à l'aide d'Aspose.Page. Si vous souhaitez améliorer vos capacités de traitement de documents et assurer une intégration transparente avec Aspose.Page, vous êtes au bon endroit. Dans ce didacticiel, nous vous guiderons tout au long du processus, en décomposant chaque étape en morceaux faciles à digérer.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Connaissance de base de la programmation Java.
-  Bibliothèque Aspose.Page installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/java/).
- Clés publiques et privées mesurées, que vous pouvez obtenir via votre compte Aspose.
## Importer des packages
Commençons par importer les packages nécessaires à notre programme Java. Assurez-vous que la bibliothèque Aspose.Page est intégrée à votre projet.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Étape 1 : Initialiser le format du document et de l'image
La première étape consiste à paramétrer le document et à définir le format d'image souhaité.
```java
// définir des clés publiques et privées mesurées
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Accédez à la propriété setMeteredKey et transmettez les clés publiques et privées comme paramètres
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Étape 2 : initialiser le flux d'entrée PostScript
Dans cette étape, nous initialisons le flux d'entrée PostScript pour le traitement.
```java
// Initialiser le flux d'entrée PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Étape 3 : Vérifier la licence du document
Avant de continuer, il est crucial de vérifier si le document est correctement autorisé.
```java
// Vérifiez si le document est sous licence
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Étape 4 : initialiser les options et le périphérique d'image
Maintenant, initialisons les options et le périphérique d'image avec les paramètres par défaut.
```java
// Initialisez l'objet d'options avec les paramètres par défaut.
ImageSaveOptions options = new ImageSaveOptions();
// Initialisez l'objet ImageDevice avec les paramètres par défaut.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Étape 5 : Enregistrer le fichier EPS en tant qu'image
Enregistrez le fichier EPS en tant qu'image en utilisant les options et le périphérique définis.
```java
// Enregistrer le fichier EPS en tant qu'image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Étape 6 : obtenir et enregistrer les octets d'image
Récupérez les octets de l'image et enregistrez-les dans un fichier.
```java
// Obtenez des octets d’images. Tableau d'un octet pour une page. Dans notre cas, nous avons une page.
byte[][] imagesBytes = device.getImagesBytes();
// Enregistrer les octets de l'image dans un fichier
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Conclusion
Toutes nos félicitations! Vous avez configuré avec succès une licence limitée en Java à l'aide d'Aspose.Page. Ce didacticiel a fourni un guide étape par étape pour garantir un processus d'intégration fluide.
## FAQ
### Q : Comment puis-je obtenir des clés publiques et privées mesurées ?
Vous pouvez obtenir ces clés via votre compte Aspose.
### Q : La bibliothèque Aspose.Page est-elle gratuite ?
 Aspose.Page propose à la fois des versions d'essai gratuites et payantes. Visite[ici](https://releases.aspose.com/) pour un essai gratuit.
### Q : Puis-je utiliser Aspose.Page pour des projets commerciaux ?
 Oui, Aspose.Page propose des licences commerciales. Vous pouvez les acheter[ici](https://purchase.aspose.com/buy).
### Q : Où puis-je trouver de la documentation supplémentaire ?
 Se référer à la documentation[ici](https://reference.aspose.com/page/java/).
### Q : Comment puis-je obtenir des licences temporaires ?
 Des licences temporaires peuvent être obtenues[ici](https://purchase.aspose.com/temporary-license/).