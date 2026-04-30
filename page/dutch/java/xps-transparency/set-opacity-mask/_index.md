---
date: 2026-04-30
description: Leer hoe je een XPS‑document in Java maakt en een opaciteitsmasker toevoegt
  met Aspose.Page Java. Stapsgewijze gids met codevoorbeelden.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Opaciteitsmasker instellen in Java XPS
second_title: Aspose.Page Java API
title: XPS-document maken met Java – Opaciteitsmasker instellen met Aspose.Page
url: /nl/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel Opaciteitsmasker in Java XPS met Aspose.Page Java

## Introductie
In deze tutorial maak je **create XPS document Java** bestanden en leer je hoe je een opaciteitsmasker toepast dat je grafische elementen een gepolijste, half‑transparante uitstraling geeft. We lopen het volledige proces door—van het initialiseren van een XPS-document, het toevoegen van een canvas, het tekenen van een rechthoek, tot het koppelen van een op afbeelding gebaseerd opaciteitsmasker—met behulp van de intuïtieve Aspose.Page Java API. Aan het einde kun je professioneel XPS-bestanden programmatically genereren en het masker hergebruiken op elke gewenste vorm.

## Snelle Antwoorden
- **Wat doet een opaciteitsmasker?** Het definieert variërende transparantieniveaus voor een vorm, waardoor onderliggende inhoud zichtbaar wordt.  
- **Welke bibliotheek is vereist?** Aspose.Page for Java (aspose page java).  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Hoeveel regels code?** Ongeveer 20 regels Java plus een paar setup‑instructies.  
- **Kan ik het masker hergebruiken op meerdere vormen?** Ja, je kunt dezelfde `ImageBrush` aan meerdere paden toewijzen.

## Wat is een Opaciteitsmasker in XPS?
Een opaciteitsmasker is een bitmap of vector die de alfa (transparantie) van elke pixel in een vorm regelt. Wanneer toegepast op een rechthoek, worden delen van de rechthoek volledig ondoorzichtig, gedeeltelijk transparant, of volledig transparant, waardoor geavanceerde visuele effecten ontstaan zonder extra tekenlagen.

## Waarom Aspose.Page Java gebruiken om **create XPS document java**?
- **Pure Java API** – Geen native afhankelijkheden, dus dezelfde code draait op Windows, Linux of macOS.  
- **Volledige XPS-specificatie‑naleving** – Maskers renderen precies zoals gedefinieerd in de XPS-standaard.  
- **Object‑georiënteerd ontwerp** – Vergelijkbaar met .NET, waardoor het gemakkelijk op te pakken is als je Aspose in andere talen hebt gebruikt.  
- **Hoge prestaties** – Geoptimaliseerd voor grote documenten en batchverwerking.

## Veelvoorkomende Toepassingsgevallen
- **Watermerken** – Een half‑transparant logo over pagina's toepassen.  
- **Dynamisch thematiseren** – De visuele stijl van UI‑elementen in gegenereerde rapporten wijzigen.  
- **Print‑klare previews** – Tonen hoe een ontwerp eruitziet met variërende opacity voordat het naar een printer wordt gestuurd.

## Voorvereisten
- Een basisbegrip van Java-programmeren.  
- Aspose.Page for Java bibliotheek geïnstalleerd. Je kunt het downloaden **[hier](https://releases.aspose.com/page/java/)**.  
- Een geldige licentie voor Aspose.Page. Als je er geen hebt, verkrijg een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)**.  
- Een ontwikkelomgeving die Java‑toepassingen kan compileren en uitvoeren (bijv. IntelliJ IDEA, Eclipse of VS Code).

## Pakketten Importeren
Begin met het importeren van de benodigde klassen uit de Aspose.Page-bibliotheek. Dit zorgt ervoor dat de API beschikbaar is voor je project.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Stapsgewijze Gids

### Stap 1: Maak een nieuw XPS-document
Eerst maak je een nieuw XPS-document aan dat al onze grafische elementen zal bevatten.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Stap 2: Voeg een Canvas toe
Een canvas fungeert als een tekenoppervlak binnen de XPS-pagina.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Stap 3: Voeg een Rechthoek toe en pas een Vaste Vulling toe
Hier maken we een rechthoekpad aan en geven het een vaste rode vulling. Deze rechthoek zal later het opaciteitsmasker ontvangen.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Stap 4: Voeg een Opaciteitsmasker toe met een ImageBrush
We laden een TIFF-afbeelding, definiëren bron- en bestemmingsrechthoeken, en stellen de brush in op tegelmodus zodat het masker indien nodig herhaalt.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Stap 5: Sla het resulterende XPS-document op
Ten slotte sla je het document op schijf op. Het uitvoerbestand zal de rechthoek met het toegepaste opaciteitsmasker bevatten.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Volg deze stappen zorgvuldig om **add opacity mask** functionaliteit in je Java XPS-document te integreren met Aspose.Page.

## Veelvoorkomende Problemen & Probleemoplossing
- **Afbeelding niet gevonden** – Controleer of `dataDir` naar de juiste map wijst en of `R08SY_NN.tif` bestaat.  
- **Masker lijkt solide** – Zorg ervoor dat de bronafbeelding daadwerkelijk variërende alfa‑waarden bevat; een volledig ondoorzichtige afbeelding toont geen transparantie.  
- **Tegelmodus wordt niet gerespecteerd** – De bestemmingsrechthoek moet kleiner zijn dan de bronrechthoek om tegelvorming merkbaar te maken.

## Veelgestelde Vragen

**V: Is Aspose.Page compatibel met alle Java‑ontwikkelomgevingen?**  
A: Ja, Aspose.Page is ontworpen om naadloos te werken met verschillende Java‑IDE's en build‑tools.

**V: Kan ik Aspose.Page gebruiken zonder licentie?**  
A: Hoewel je de bibliotheek kunt evalueren met een tijdelijke licentie, is een volledige licentie vereist voor productiegebruik.

**V: Zijn er beperkingen in de proefversie?**  
A: De proefversie kan beperkingen opleggen op grootte of functies; raadpleeg de officiële documentatie voor details.

**V: Hoe kan ik ondersteuning krijgen voor Aspose.Page?**  
A: Bezoek het **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** voor community‑hulp of koop een licentie voor premium‑ondersteuning.

**V: Is er een geld‑terug‑garantie voor Aspose.Page?**  
A: Raadpleeg de **[aankooppagina](https://purchase.aspose.com/buy)** voor informatie over terugbetalingsbeleid.

---

**Laatst bijgewerkt:** 2026-04-30  
**Getest met:** Aspose.Page Java 24.11 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}