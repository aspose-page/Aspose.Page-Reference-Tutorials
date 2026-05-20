---
date: 2026-04-24
description: Leer hoe je een XPS‑document in Java maakt met een ellips met radiale
  gradiënt. Deze stapsgewijze gids laat zien hoe je de lijndikte instelt en padgeometrie
  definieert met behulp van Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Ellips toevoegen in Java XPS
second_title: Aspose.Page Java API
title: XPS-document maken in Java – Radiale gradient-ellips toevoegen
url: /nl/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radiale gradient ellips toevoegen met Aspose.Page

## Introductie
In deze tutorial leer je hoe je **create XPS document Java** maakt met een prachtige radiale gradient‑omrande ellips met behulp van Aspose.Page voor Java. Aspose.Page is een robuuste bibliotheek die de low‑level XPS‑details abstraheert, zodat je je kunt concentreren op ontwerp in plaats van de intriciteiten van het bestandsformaat. Aan het einde van deze gids heb je een kant‑klaar XPS‑bestand dat je kunt insluiten in rapporten, facturen of elke document‑generatie‑workflow.

## Snelle Antwoorden
- **Wat produceert deze code?** Een één‑pagina XPS‑bestand met een ellips omrand met een meerkleurige radiale gradient.  
- **Welke primaire API wordt gebruikt?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.  
- **Wat zijn de belangrijkste eigenschappen die we instellen?** Stroke‑kwast (radiale gradient), spread‑methode, gradient‑stops en stroke‑dikte.  
- **Kan ik de grootte van de ellips wijzigen?** Ja – wijzig de pad‑geometrie‑string of de coördinaten van de gradient‑kwast.

## Wat is “create XPS document Java”?
Een XPS‑document maken in Java betekent het programmatisch genereren van een XML Paper Specification (XPS)‑bestand — een vaste‑indeling documentformaat vergelijkbaar met PDF — direct vanuit Java‑code. Aspose.Page biedt een high‑level objectmodel (`XpsDocument`, `XpsCanvas`, etc.) dat de XML‑markup abstraheert, waardoor het proces net zo eenvoudig is als werken met standaard Java‑objecten.

## Waarom een radiale gradient‑ellips gebruiken?
Een radiale gradient geeft een driedimensionaal gevoel, perfect voor visuele accenten, logo's of decoratieve elementen in rapporten. Vergeleken met een effen kleurstroke voegt de gradient diepte toe zonder de bestandsgrootte aanzienlijk te vergroten, en het XPS‑formaat behoudt de vectorkwaliteit bij elke schaalvergroting.

## Vereisten
- Java Development Kit (JDK) geïnstalleerd op je machine.
- Aspose.Page for Java bibliotheek gedownload. Je kunt het hier verkrijgen [here](https://releases.aspose.com/page/java/).
- Een code‑editor naar keuze (Eclipse, IntelliJ, etc.) voor het schrijven en uitvoeren van Java‑code.

## Pakketten Importeren
Zorg ervoor dat de benodigde pakketten zijn geïmporteerd in je Java‑project om Aspose.Page te gebruiken. Voeg de volgende import‑statements toe aan het begin van je Java‑bestand:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Stap 1: Documentmap Instellen
Bepaal het pad naar je documentmap waar het XPS‑document wordt opgeslagen:

```java
String dataDir = "Your Document Directory";
```

## Stap 2: XPS‑Document Maken
Initialiseer een nieuw XPS‑document met de volgende code:

```java
XpsDocument doc = new XpsDocument();
```

## Stap 3: Radiale Gradient‑Stops Definiëren
Maak een lijst van gradient‑stops voor de radiale gradient‑omrande ellips:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Stap 4: Pad‑Geometrie Maken
Definieer een radiale gradient‑omrande ellips met behulp van pad‑geometrie:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Stap 5: Canvas en Pad Toevoegen
Voeg een nieuw canvas toe aan het document en voeg het pad toe met de gedefinieerde geometrie:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Stap 6: Stroke en Gradient Instellen
Configureer de stroke van het pad met een radiale gradient‑kwast:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Stap 7: Stroke‑Dikte Instellen
Specificeer de **stroke‑dikte** van het pad:

```java
path.setStrokeThickness(12f);
```

## Stap 8: Document Opslaan
Sla het resulterende XPS‑document op:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Gefeliciteerd! Je hebt met succes een radiale gradient‑omrande ellips toegevoegd terwijl je **create XPS document Java** maakt met Aspose.Page.

## Veelvoorkomende Problemen en Oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Ellips lijkt plat** | Gebruik van `XpsSpreadMethod.Pad` in plaats van `Reflect` | Verander de spread‑methode naar `XpsSpreadMethod.Reflect` zoals getoond in Stap 6. |
| **Geen uitvoerbestand** | `dataDir` wijst naar een niet‑bestaande map | Zorg ervoor dat de map bestaat of gebruik een absoluut pad. |
| **Gradient‑kleuren zien er verkeerd uit** | Onjuiste volgorde van gradient‑stops | Controleer of de `offset`‑waarden (0 → 1) monotoon toenemen. |
| **Compilatiefouten** | Ontbrekende Aspose.Page JAR‑bestanden op het classpath | Voeg `aspose-page-xx.jar` toe aan de project‑afhankelijkheden. |

## Veelgestelde Vragen

**Q: Kan ik Aspose.Page for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Page for Java kan naadloos worden geïntegreerd met andere Java‑bibliotheken.

**Q: Is Aspose.Page geschikt voor grootschalige documentverwerking?**  
A: Absoluut! Aspose.Page is ontworpen om grootschalige documentverwerking efficiënt aan te kunnen.

**Q: Waar kan ik meer tutorials en voorbeelden vinden voor Aspose.Page for Java?**  
A: Bezoek de [Aspose.Page for Java documentatie](https://reference.aspose.com/page/java/) voor uitgebreide tutorials en voorbeelden.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Page for Java?**  
A: Je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).

**Q: Zijn er community‑forums voor Aspose.Page discussies?**  
A: Ja, word lid van het [Aspose.Page community‑forum](https://forum.aspose.com/c/page/39) om met andere ontwikkelaars in contact te komen en hulp te krijgen.

---

**Laatst bijgewerkt:** 2026-04-24  
**Getest met:** Aspose.Page for Java 24.11 (latest op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}