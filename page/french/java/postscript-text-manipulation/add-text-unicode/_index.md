---
date: 2025-12-13
description: Apprenez comment ajouter du texte à une page Aspose en Java, définir
  le style de police en Java, et comment ajouter du texte Unicode à l’aide d’Aspose.Page.
  Suivez notre guide étape par étape.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Ajouter du texte à une page asp – Unicode dans Java PostScript
url: /fr/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode in Java PostScript

## Introduction
Si vous devez **asp page add text** dans un flux de travail Java PostScript tout en conservant les caractères Unicode, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ajout de texte Unicode, la définition du style de police et l’enregistrement du résultat à l’aide de **Aspose.Page for Java**. À la fin, vous comprendrez comment définir le style de police java et comment ajouter du texte Unicode efficacement dans vos projets.

## Quick Answers
- **Quelle bibliothèque permet d’ajouter du texte Unicode en Java PostScript ?** Aspose.Page for Java.  
- **Quelle méthode principale ajoute du texte ?** `doc.addGlyphs(...)` avec un objet `XpsGlyphs`.  
- **Ai‑je besoin d’une police spéciale pour Unicode ?** Toute police TrueType/OpenType qui prend en charge les points de code requis (par ex., Arial).  
- **Puis‑je changer le style de la police ?** Oui, en utilisant `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **Une licence est‑elle requise pour la production ?** Oui, une licence valide d’Aspose.Page est nécessaire pour une utilisation non‑trial.

## What is asp page add text?
`asp page add text` désigne le processus d’insertion de chaînes de texte dans un document PostScript ou XPS à l’aide de l’API Aspose.Page. L’API abstrait les commandes PostScript de bas niveau, vous permettant de travailler avec des objets de haut niveau comme `XpsGlyphs`.

## Why use Aspose.Page to set font style java and add Unicode text?
- **Support complet Unicode** – Gère les scripts de droite à gauche et les glyphes complexes.  
- **API simple** – Appels en une ligne pour ajouter du texte et appliquer des styles.  
- **Multiplateforme** – Fonctionne dans tout environnement compatible Java.  
- **Aucune dépendance externe** – Pas besoin de moteurs de rendu supplémentaires.

## Prerequisites
Avant de commencer le tutoriel, assurez‑vous que les prérequis suivants sont en place :

1. **Java Development Kit (JDK)** – Vérifiez que Java est installé sur votre machine.  
2. **Aspose.Page for Java** – Téléchargez et installez la bibliothèque Aspose.Page depuis le [lien de téléchargement](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Choisissez votre IDE Java préféré, tel qu’IntelliJ IDEA ou Eclipse.

## Import Packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Page. Ajoutez les lignes suivantes à votre code :

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
Créez un nouveau projet Java dans votre IDE et configurez la structure du projet. Assurez‑vous d’inclure la bibliothèque Aspose.Page dans les dépendances de votre projet.

## Step 2: Initialize XPS Document
Commencez par initialiser un nouveau document XPS dans votre projet :

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Ajoutons maintenant du texte Unicode à votre document XPS à l’aide de la bibliothèque Aspose.Page. Utilisez le fragment de code suivant :

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Ce segment de code ajoute le texte Unicode **"AVAJ rof SPX.esopsA"** au document XPS aux coordonnées (400, 200) avec la police et le style spécifiés. Notez que l’appel `setBidiLevel(1)` active le rendu de droite à gauche pour un affichage Unicode correct.

## Step 4: Save the Document
Enregistrez le document XPS résultant à l’aide du code suivant :

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
Félicitations ! Vous avez réussi à **asp page add text** et à définir le style de police dans un scénario Java PostScript en utilisant Aspose.Page. Cette méthode vous offre un contrôle fin sur le rendu Unicode et le style, ce qui la rend idéale pour les rapports, factures et graphiques internationalisés.

N’hésitez pas à explorer davantage les fonctionnalités d’Aspose.Page dans la [documentation](https://reference.aspose.com/page/java/).

## Frequently Asked Questions

**Q :** Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?  
**R :** Aspose.Page est principalement conçu pour Java, mais Aspose propose des bibliothèques pour divers langages de programmation.

**Q :** Existe‑t‑il une version d’essai gratuite ?  
**R :** Oui, vous pouvez accéder à un essai gratuit d’Aspose.Page [ici](https://releases.aspose.com/).

**Q :** Où puis‑je trouver du support et des discussions sur Aspose.Page ?  
**R :** Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support et les discussions.

**Q :** Comment obtenir une licence temporaire pour Aspose.Page ?  
**R :** Vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q :** Quels sont les styles de police disponibles dans Aspose.Page ?  
**R :** Aspose.Page prend en charge les styles de police tels que Regular, Bold, Italic et BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---