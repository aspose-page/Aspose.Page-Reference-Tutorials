---
date: 2026-01-02
description: Leer hoe u een opacity‑masker toevoegt aan XPS‑documenten met Aspose.Page
  Java. Stapsgewijze handleiding om een opacity‑maskerrechthoek te maken en de visuele
  kwaliteit te verbeteren.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Opaciteitsmasker instellen in Java XPS met Aspose.Page Java
url: /nl/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Instellen van Opaciteitsmasker in Java XPS met Aspose.Page Java

## Introductie
Welkom bij onze uitgebreide gids over **aspose page java** opaciteitsmaskers. In deze tutorial leer je hoe je een XPS‑document maakt, een canvas toevoegt en een opaciteitsmasker toepast op een rechthoek — alles met de krachtige Aspose.Page Java API. Aan het einde kun je opaciteitsmasker‑rechthoeken toevoegen die je XPS‑bestanden een gepolijste, halfdoorzichtige uitstraling geven.

## Snelle Antwoorden
- **Wat doet een opaciteitsmasker?** Het definieert verschillende transparantieniveaus voor een vorm, waardoor onderliggende inhoud zichtbaar wordt.
- **Welke bibliotheek is vereist?** Aspose.Page for Java (aspose page java).
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.
- **Hoeveel regels code?** Ongeveer 20 regels Java plus een paar setup‑statements.
- **Kan ik het masker hergebruiken voor meerdere vormen?** Ja, je kunt dezelfde ImageBrush toewijzen aan meerdere paden.

## Wat is een Opaciteitsmasker in XPS?
Een opaciteitsmasker is een bitmap of vector die de alfa (transparantie) van elk pixel in een vorm regelt. Wanneer het op een rechthoek wordt toegepast, worden delen van de rechthoek volledig ondoorzichtig, gedeeltelijk transparant of volledig transparant, waardoor verfijnde visuele effecten ontstaan.

## Waarom Aspose.Page Java gebruiken voor Opaciteitsmaskers?
- **Volledige .NET‑achtige API in Java** – intuïtief objectmodel.  
- **Geen externe afhankelijkheden** – werkt met pure Java.  
- **Hoge‑fidelity rendering** – maskers renderen exact volgens de XPS‑specificatie.  
- **Cross‑platform** – draait op Windows, Linux of macOS zonder aanpassingen.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:
- Een basisbegrip van Java‑programmeren.  
- Aspose.Page for Java‑bibliotheek geïnstalleerd. Je kunt deze **[hier](https://releases.aspose.com/page/java/)** downloaden.  
- Een geldige licentie voor Aspose.Page. Als je er geen hebt, verkrijg dan een tijdelijke licentie **[hier](https://purchase.aspose.com/temporary-license/)**.  
- Een ontwikkelomgeving die Java‑applicaties kan compileren en uitvoeren (bijv. IntelliJ IDEA, Eclipse of VS Code).

## Import Pakketten
Begin met het importeren van de benodigde klassen uit de Aspose.Page‑bibliotheek. Dit zorgt ervoor dat de API beschikbaar is voor je project.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Stapsgewijze Gids

### Stap 1: Maak een nieuw XPS‑document
Instantieer eerst een nieuw XPS‑document dat al onze graphics zal bevatten.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Stap 2: Voeg een Canvas toe
Een canvas fungeert als tekenoppervlak binnen de XPS‑pagina.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Stap 3: Voeg een Rechthoek toe en pas een solide vulling toe
Hier creëren we een rechthoekpad en geven het een solide rode vulling. Deze rechthoek krijgt later het opaciteitsmasker.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Stap 4: Voeg een Opaciteitsmasker toe met een ImageBrush
We laden een TIFF‑afbeelding, definiëren bron‑ en bestemmingsrechthoeken, en stellen de brush in op tile‑mode zodat het masker indien nodig herhaalt.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Stap 5: Sla het resulterende XPS‑document op
Sla tenslotte het document op schijf op. Het uitvoerbestand zal de rechthoek met het toegepaste opaciteitsmasker bevatten.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Volg deze stappen zorgvuldig om **add opacity mask** functionaliteit in je Java XPS‑document te integreren met Aspose.Page.

## Veelvoorkomende Problemen & Probleemoplossing
- **Afbeelding niet gevonden** – Controleer of `dataDir` naar de juiste map wijst en of `R08SY_NN.tif` bestaat.  
- **Masker lijkt solide** – Zorg ervoor dat de bronafbeelding daadwerkelijk variërende alfa‑waarden bevat; een volledig ondoorzichtige afbeelding toont geen transparantie.  
- **Tile‑mode wordt niet gerespecteerd** – De bestemmingsrechthoek moet kleiner zijn dan de bronrechthoek om tiling merkbaar te maken.

## Veelgestelde Vragen

**V: Is Aspose.Page compatibel met alle Java‑ontwikkelomgevingen?**  
A: Ja, Aspose.Page is ontworpen om naadloos te werken met diverse Java‑IDE’s en build‑tools.

**V: Kan ik Aspose.Page gebruiken zonder licentie?**  
A: Je kunt de bibliotheek evalueren met een tijdelijke licentie, maar een volledige licentie is vereist voor productie.

**V: Zijn er beperkingen in de proefversie?**  
A: De proefversie kan grootte‑ of functierestricties opleggen; raadpleeg de officiële documentatie voor details.

**V: Hoe krijg ik ondersteuning voor Aspose.Page?**  
A: Bezoek het **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** voor community‑hulp of koop een licentie voor premium‑ondersteuning.

**V: Is er een geld-terug‑garantie voor Aspose.Page?**  
A: Zie de **[aankooppagina](https://purchase.aspose.com/buy)** voor informatie over restitutiebeleid.

---

**Laatst bijgewerkt:** 2026-01-02  
**Getest met:** Aspose.Page Java 24.11 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}