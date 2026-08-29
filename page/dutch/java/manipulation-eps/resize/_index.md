---
date: 2026-08-29
description: Leer hoe je EPS-bestanden in Java vector kunt schalen met Aspose.Page.
  Deze stapsgewijze handleiding laat zien hoe je EPS kunt schalen met points, inches,
  millimeters of percentages.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Resize EPS-bestand in Java
og_description: Java vector resize stelt je in staat om EPS-bestandsdimensies direct
  in Java aan te passen. Met Aspose.Page kun je resize met points, inches, millimeters
  of percentages, terwijl je de vector quality behoudt.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Java vector resize: EPS-dimensies wijzigen met Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Hoe je EPS-bestanden in Java vector kunt schalen met Aspose.Page
url: /nl/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Java vector EPS-bestanden te verkleinen met Aspose.Page

## Introductie
Als u **java vector resize** EPS‑bestanden programmatisch wilt verkleinen, bent u hier aan het juiste adres. Deze tutorial leidt u stap voor stap door het verkleinen van EPS‑afbeeldingen in Java met behulp van de Aspose.Page‑bibliotheek. Of u nu de grootte wilt verdubbelen, wilt verkleinen tot een specifieke maat, of wilt werken met percentages, de onderstaande stappen geven u volledige controle over de uitvoerafmetingen. Het beheersen van het verkleinen van EPS is essentieel bij het aanpassen van graphics voor verschillende printlay-outs, schermresoluties of merk‑richtlijnen.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Page for Java  
- **Kan ik verkleinen met punten, inches of millimeters?** Ja – de API ondersteunt alle drie de eenheden plus percentages.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of later.  
- **Is de code thread‑safe?** Elke `PsDocument`‑instantie is geïsoleerd, dus u kunt bestanden parallel verwerken.  

## Wat is EPS en waarom verkleinen?
Encapsulated PostScript (EPS) is een vector‑grafisch formaat dat veel wordt gebruikt voor print en publicatie. Soms wordt het oorspronkelijke EPS‑bestand gemaakt in een grootte die niet overeenkomt met uw gewenste output – bijvoorbeeld, een logo ontworpen op 72 pts moet mogelijk 144 pts zijn voor een grotere brochure. Weten **hoe EPS te verkleinen** laat u de vector‑kwaliteit behouden terwijl u de afmetingen aanpast aan elke workflow.

## Waarom Aspose.Page gebruiken voor het verkleinen van EPS?
Aspose.Page biedt een eenvoudige API waarmee u de doelgrootte in een van de ondersteunde eenheden kunt opgeven, terwijl de vectorstructuur automatisch behouden blijft. De bibliotheek handelt eenheidsconversie intern af, zodat u zich kunt concentreren op de gewenste afmetingen zonder handmatige berekeningen.

- **Ondersteunt vier meeteenheden** – Points, Inches, Millimeters, en Percent.  
- **Geen externe afhankelijkheden** – pure Java API, geen native bibliotheken vereist.  
- **Hoge‑prestaties verwerking** – kan tot 500 EPS‑bestanden per minuut verwerken op een standaard 8‑core server.  
- **Behoudt vectorfidelity** – de output blijft volledig schaalbaar zonder rasterisatie.

## Vereisten
Voordat we in de code duiken, zorg dat u het volgende heeft:

- Java Development Kit (JDK) geïnstalleerd op uw machine.  
- Aspose.Page for Java bibliotheek. U kunt het downloaden op **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Een basisbegrip van Java‑programmeren.  

## Importeer pakketten
Neem in uw Java‑project de benodigde imports op zodat u met Aspose.Page‑objecten en standaard I/O‑streams kunt werken.

`PsDocument` vertegenwoordigt een EPS‑document dat in het geheugen is geladen.  
`Units` is een enumeratie die de meeteenheden definieert die door de API worden geaccepteerd.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hoe EPS-dimensies te wijzigen met verschillende eenheden
U kunt EPS‑dimensies wijzigen door de `resizeEps`‑methode aan te roepen met de gewenste breedte, hoogte en een `Units`‑enum‑waarde; dit werkt voor punten, inches, millimeters of percentages. Hetzelfde vijf‑stappen‑patroon geldt voor elke eenheid, waardoor de API voorspelbaar en eenvoudig te integreren is.

`resizeEps` verkleint het EPS‑canvas naar de opgegeven afmetingen terwijl de interne vectordata behouden blijft.

## Hoe EPS te verkleinen met punten
Laad uw EPS, geef de nieuwe grootte in punten op en sla het resultaat op. Deze aanpak verdubbelt de oorspronkelijke afmetingen terwijl de beeldverhouding behouden blijft. Werken met punten geeft u precieze controle over print‑klare maten, wat vooral nuttig is voor typografische lay-outs en output met hoge resolutie.

### Stap 1: stel de invoerstroom in
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Stap 2: initialiseert het `PsDocument`‑object
`PsDocument` laadt het bron‑EPS‑bestand en biedt methoden voor manipulatie.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Stap 3: haal de huidige grootte van de EPS-afbeelding op
```java
Dimension oldSize = doc.extractEpsSize();
```

### Stap 4: maak een uitvoerstroom voor het verkleinde bestand
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Stap 5: verklein en sla de EPS op met punten
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hoe EPS te verkleinen met inches
Verkleinen met inches laat u specificaties volgen die in imperiale eenheden zijn gedefinieerd, zoals brochure‑lay-outs of Amerikaanse printnormen. Geef de doelbreedte en -hoogte in inches op, en de API converteert deze naar de juiste interne eenheden voordat de transformatie wordt toegepast.

## Hoe EPS te verkleinen met millimeters
Bij het werken met metrische workflows zorgt het specificeren van afmetingen in millimeters voor consistentie met papierformaten en printapparatuur buiten de Verenigde Staten. De bibliotheek handelt de conversie van millimeters naar het interne coördinatensysteem automatisch af.

## Hoe EPS te verkleinen met percentages
Verkleinen op basis van percentage schaalt de oorspronkelijke afmetingen proportioneel, wat handig is voor snelle aanpassingen zonder absolute waarden te berekenen. Bijvoorbeeld, een factor van `0.5` verkleint zowel breedte als hoogte met 50 %.

## Veelvoorkomende valkuilen & tips
- **Sluit altijd streams** – In productiecodel, wikkel streams in try‑with‑resources om bestandsvergrendelingen te voorkomen.  
- **Behoud aspectratio** – Vermenigvuldig zowel breedte als hoogte met dezelfde factor tenzij u opzettelijk vervorming wilt.  
- **Controleer DPI** – Verkleinen verandert de DPI niet; als u een andere DPI nodig heeft, pas deze dan apart aan na het verkleinen.  
- **Thread‑veiligheid** – Maak een nieuwe `PsDocument` per thread; het delen van dezelfde instantie kan onverwachte resultaten opleveren.  

## Veelgestelde vragen

**Q: Kan ik deze bibliotheek voor andere afbeeldingsformaten gebruiken?**  
A: Nee, Aspose.Page is uitsluitend gespecialiseerd in PostScript‑ en EPS‑bestanden.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Page for Java?**  
A: Ja, u kunt de gratis proefversie verkennen **[Aspose free trial page](https://releases.aspose.com/)**.

**Q: Waar kan ik extra hulp en discussies vinden?**  
A: Bezoek het **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** voor community‑ondersteuning.

**Q: Hoe kan ik een tijdelijke licentie verkrijgen?**  
A: U kunt een tijdelijke licentie aanvragen via **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Zijn er voorbeeldprojecten beschikbaar?**  
A: Ja, bekijk de documentatie **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Gerelateerde tutorials

- [EPS verkleinen met Aspose.Page – Java EPS-manipulatie](/page/java/manipulation-eps/)
- [Hoe EPS-bestanden bijsnijden in Java – Aspose.Page-gids](/page/java/manipulation-eps/crop/)
- [Hoe rechthoek schalen met Aspose.Page voor Java](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}