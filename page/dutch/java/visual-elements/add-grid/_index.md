---
date: 2025-12-18
description: Leer hoe je een raster en een transparante rechthoek toevoegt in Java
  XPS‑documenten met Aspose.Page. Stapsgewijze handleiding om een XPS‑document efficiënt
  op te slaan.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Hoe een raster toevoegen met Visual Brush in Java
url: /nl/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een raster toevoegen met Visual Brush in Java

## Introductie
Als je op zoek bent naar **how to add grid** elementen voor je met Java gegenereerde XPS‑documenten, ben je op de juiste plek. In deze tutorial laten we je stap voor stap zien hoe je een raster toevoegt met een Visual Brush, een transparante rechthoek toevoegt, en uiteindelijk **save XPS document** met de Aspose.Page Java API. Aan het einde heb je een gepolijste visual die hergebruikt kan worden in rapporten, facturen of elke document‑intensieve toepassing.

## Snelle antwoorden
- **What does a Visual Brush do?** Het schildert een gedefinieerd gebied met herbruikbare visuele inhoud, perfect voor herhalende patronen zoals rasters.  
- **Can I change the grid color?** Ja – wijzig de solid‑color brush instellingen van de brush.  
- **How do I add a transparent rectangle on top of the grid?** Gebruik `setOpacity` op een pad gevuld met een effen kleur.  
- **What method saves the file?** `doc.save(...)` schrijft het XPS‑bestand naar schijf.  
- **Do I need a license?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.

## Wat is een Visual Brush Grid?
Een Visual Brush stelt je in staat een klein visueel element (het rasterpatroon) te definiëren en dit vervolgens over een groter gebied te herhalen. Deze aanpak is geheugen‑efficiënter dan elke lijn afzonderlijk te tekenen en biedt pixel‑perfecte herhaalbaarheid.

## Waarom Aspose.Page gebruiken voor deze taak?
- **Cross‑platform** – Werkt op elk OS dat Java ondersteunt.  
- **High‑fidelity rendering** – Precieze controle over kleuren, doorzichtigheid en tegelpatroon.  
- **No external dependencies** – Alles wordt afgehandeld via de Aspose.Page‑bibliotheek.

## Vereisten
Voordat we beginnen, zorg dat je het volgende hebt:

- Basiskennis van Java‑programmeren.  
- Aspose.Page‑bibliotheek geïnstalleerd – je kunt deze downloaden van de [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 of hoger geïnstalleerd op je ontwikkelmachine.

## Importer pakketten
First, import the required classes so the compiler knows where to find the types we’ll use:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Stapsgewijze handleiding

### Stap 1: Stel je project in
Maak een nieuw `XpsDocument`‑object aan en wijs de map aan waar je het uitvoerbestand wilt opslaan.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Stap 2: Maak een Magenta Raster Visual Brush
We definiëren een kleine magenta vorm die over het rastergebied wordt herhaald.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Stap 3: Definieer geometrie voor de Grid Brush
Stel het rechthoekige gebied in dat de herhaalde visual zal ontvangen.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Stap 4: Maak een nieuw canvas voor het document
Voeg een canvas toe aan het document en positioneer het waar het raster moet verschijnen.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Stap 5: Voeg het raster toe aan het canvas
Pas de visual brush toe op de geometrie, waardoor herhaling mogelijk wordt.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Stap 6: Voeg een transparante rode rechthoek toe (secundaire functie)
Hier demonstreren we **add transparent rectangle** bovenop het raster voor nadruk.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Stap 7: Sla het resulterende XPS‑document op
Schrijf tenslotte het document naar schijf — dit is de **save XPS document** stap.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Volg deze stappen en je hebt een professioneel uitziend raster met een transparante overlay, volledig geprogrammeerd.

## Veelvoorkomende problemen & tips

- **Incorrect tile size:** Zorg ervoor dat de `Rectangle2D` die voor de brush wordt gebruikt overeenkomt met de beoogde herhalingsgrootte; anders kan het patroon uitrekken.  
- **Opacity not applied:** Vergeet niet `setOpacity` aan te roepen op het pad dat je transparant wilt maken; dit beïnvloedt de brush zelf niet.  
- **File not saved:** Controleer of `dataDir` naar een bestaande map wijst en of je applicatie schrijfrechten heeft.

## Veelgestelde vragen

**Q: Is Aspose.Page geschikt voor professionele documentgeneratie?**  
A: Ja, Aspose.Page is een robuuste bibliotheek ontworpen voor hoogwaardige XPS- en PDF‑generatie in Java.

**Q: Kan ik de rasterkleuren aanpassen met Visual Brush?**  
A: Absoluut! Wijzig de `createColor`‑parameters in de `setFill`‑aanroep van de brush naar elke gewenste RGBA‑waarde.

**Q: Waar kan ik extra ondersteuning vinden voor Aspose.Page?**  
A: Bezoek het [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor community‑hulp en officiële antwoorden.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page?**  
A: Ja, je kunt de [free trial](https://.aspose.com/) gebruiken om alle functies te verkennen voordat je koopt.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor testen?**  
A: Verkrijg een [temporary license](https://purchase.aspose.com/temporary-license/) die werkt voor ontwikkeling en evaluatie.

---

**Laatst bijgewerkt:** 2025-12-18  
**Getest met:** Aspose.Page for Java 23.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}