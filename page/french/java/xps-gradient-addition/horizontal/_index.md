---
date: 2025-12-25
description: Apprenez à ajouter un dégradé aux documents XPS en Java avec Aspose.Page
  et à personnaliser les points d'arrêt du dégradé pour des effets horizontaux époustouflants.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Comment ajouter un dégradé – dégradé horizontal dans Java XPS
url: /fr/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé – Dégradé horizontal en Java XPS

## Introduction
Bienvenue dans ce guide étape par étape sur **comment ajouter un dégradé** à un document XPS en Java. Dans ce tutoriel, vous apprendrez comment ajouter un dégradé horizontal, pourquoi cela compte pour le rendu visuel, et comment **personnaliser les arrêts de dégradé** pour un contrôle précis des couleurs. Aspose.Page for Java simplifie le travail avec les documents XPS (XML Paper Specification), vous permettant de vous concentrer sur le design plutôt que sur la manipulation bas‑niveau des fichiers.

## Quick Answers
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Quelle version de Java fonctionne ?** Toute version Java 8+  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production  
- **Puis‑je changer la direction du dégradé ?** Oui – il suffit de modifier les points de départ/arrivée du pinceau linéaire  
- **Est‑il possible d’ajouter plusieurs dégradés ?** Absolument – répétez les étapes de création de chemin avec des pinceaux différents  

## Qu’est‑ce qu’un dégradé horizontal en XPS ?
Un dégradé horizontal est une transition douce des couleurs de la gauche vers la droite d’une forme. En XPS, il est représenté par un pinceau de dégradé linéaire qui interpole entre des **arrêts de dégradé** définis. Cet effet visuel est couramment utilisé pour les bannières, les boutons et les remplissages d’arrière‑plan.

## Pourquoi utiliser Aspose.Page for Java ?
- **Prise en charge complète du XPS** – créez, modifiez et rendez sans outils tiers.  
- **API simple** – des objets de haut niveau comme `XpsDocument`, `XpsPath` et `XpsGradientBrush` masquent la complexité XML.  
- **Performance** – optimisé pour les documents volumineux et le traitement par lots.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Environnement de développement Java** – Installez le dernier JDK depuis [java.com](https://www.java.com).  
2. **Bibliothèque Aspose.Page for Java** – Téléchargez le JAR depuis la [documentation Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## Import Packages
Commencez par importer les classes nécessaires. Ces imports vous donnent accès à la création de documents, à la gestion des dégradés et à la géométrie de base.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Étape 1 : Initialiser le document XPS
Créez une nouvelle instance `XpsDocument` et indiquez le dossier où vous souhaitez enregistrer le résultat.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Étape 2 : Créer le dégradé horizontal
Définissez une liste d’**arrêts de dégradé** qui contrôlent la couleur et la position de chaque point de transition. L’exemple ci‑dessous crée un dégradé arc‑en‑ciel vibrant.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Comment personnaliser les arrêts de dégradé
- **Couleur** – Utilisez `doc.createColor(alpha, red, green, blue)` pour définir n’importe quelle valeur ARGB.  
- **Position** – Le deuxième argument (`float` entre `0` et `1`) indique où l’arrêt apparaît le long de la ligne du dégradé. Ajustez ces valeurs pour déplacer les couleurs vers la gauche ou la droite.

## Étape 3 : Ajouter le chemin avec le dégradé
Créez un chemin rectangulaire, appliquez une transformation si nécessaire, et remplissez‑le avec le pinceau de dégradé linéaire. Le pinceau utilise deux points (`(10,0)` à `(228,0)`) pour produire un effet horizontal.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Astuce :** Réutiliser la même liste `stops` pour plusieurs chemins peut améliorer les performances, mais n’oubliez pas de l’appeler `clear()` avant d’ajouter de nouveaux arrêts.

## Étape 4 : Enregistrer le document
Persistez le fichier XPS sur le disque. Vous pouvez maintenant l’ouvrir avec n’importe quel visualiseur XPS pour voir le dégradé horizontal en action.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Problèmes courants & Solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| Le dégradé apparaît uni | Aucun arrêt de dégradé ajouté ou pinceau non défini | Assurez‑vous que `path.setFill(...)` utilise un `LinearGradientBrush` et que les arrêts sont ajoutés via `getGradientStops().addAll(stops)`. |
| Les couleurs semblent ternes | Valeur alpha incorrecte (premier paramètre) | Utilisez `255` pour des couleurs totalement opaques, sauf si la transparence est souhaitée. |
| La taille du chemin est incorrecte | Valeurs de la matrice de transformation erronées | Ajustez les paramètres de la matrice (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Questions fréquemment posées

**Q : Puis‑je appliquer plusieurs dégradés dans un même document XPS ?**  
R : Oui, vous pouvez ajouter plusieurs chemins, chacun avec son propre pinceau de dégradé, pour créer des conceptions superposées complexes.

**Q : Aspose.Page est‑il compatible avec les dernières versions de Java ?**  
R : Aspose.Page for Java est régulièrement mis à jour et fonctionne avec Java 8 et les versions ultérieures.

**Q : Existe‑t‑il d’autres types de dégradés disponibles dans Aspose.Page ?**  
R : En plus des dégradés linéaires, Aspose.Page prend également en charge les dégradés radiaux pour des transitions de couleur circulaires.

**Q : Puis‑je personnaliser les couleurs et les positions des arrêts de dégradé ?**  
R : Absolument ! Vous avez un contrôle total sur la couleur ARGB de chaque arrêt et sur sa position relative (intervalle 0‑1).

**Q : Y a‑t‑il un forum communautaire pour Aspose.Page où je peux demander de l’aide ?**  
R : Oui, vous pouvez visiter le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour rejoindre la communauté et obtenir de l’assistance.

---

**Dernière mise à jour :** 2025-12-25  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}