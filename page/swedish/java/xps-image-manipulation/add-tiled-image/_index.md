---
date: 2026-05-30
description: Lär dig hur du skapar XPS-dokument i Java med Aspose.Page och lägger
  till en mosaikbild utan ansträngning med den här steg‑för‑steg‑guiden. Så skapar
  du XPS-filer snabbt.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Lägg till mosaikbild i Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hur man skapar XPS-dokument med en mosaikbild i Java
url: /sv/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar XPS-dokument med en kaklad bild i Java

## Introduktion
Att skapa XPS-dokument programatiskt är en grundläggande färdighet för Java‑utvecklare som behöver utskrivbart, enhetsoberoende resultat. **How to create XPS**‑filer effektivt besvaras av Aspose.Page för Java, som abstraherar de lågnivå‑XML Paper Specification‑detaljerna och låter dig fokusera på visuell design. I den här guiden kommer du att se exakt hur du skapar ett XPS-dokument, lägger till en kaklad bild som bakgrund eller mönster och sparar resultatet – allt med kortfattad, produktionsklar kod.

## Snabba svar
- **Vad gör Aspose.Page?** Det tillhandahåller ett hög‑nivå‑API för att generera och manipulera XPS‑dokument i Java.  
- **Kan jag kakla en bild?** Ja – använd `XpsImageBrush` med `XpsTileMode.Tile`.  
- **Behöver jag en licens?** En temporär eller kommersiell licens krävs för produktionsbruk.  
- **Vilken Java‑version stöds?** Alla JDK 8+ är kompatibla.  
- **Hur lång tid tar implementeringen?** Ungefär 10–15 minuter för ett grundläggande kaklat‑bild‑scenario.

## Vad är “create XPS document”?
`XpsDocument` är Aspose.Page:s övergripande objekt som representerar en enskild XPS‑fil i minnet. Det kapslar in sidor, resurser och metadata, vilket gör att du kan bygga dokumentet programatiskt. Att skapa ett XPS‑dokument innebär att instansiera denna klass, lägga till visuella element och slutligen anropa `save` för att skriva den fasta layout‑filen till disk. Detta tillvägagångssätt eliminerar manuell XML‑hantering och garanterar efterlevnad av XML Paper Specification.

## Varför lägga till en kaklad bild?
Kakling upprepar en grafik över ett definierat område, vilket är idealiskt för bakgrunder, vattenstämplar eller mönsterfyllningar. Med `XpsTileMode.Tile` upprepas bilden automatiskt utan manuell duplicering, vilket sparar utvecklingstid och säkerställer konsekvent rendering på alla enheter. Kaklade bilder håller även filstorleken låg eftersom samma bitmap‑resurs återanvänds snarare än att bäddas in flera gånger.

## Förutsättningar
Innan du dyker ner, se till att du har:

1. **Java Development Kit (JDK)** – JDK 8 eller nyare installerat.  
2. **Aspose.Page for Java** – ladda ner från [website](https://releases.aspose.com/page/java/).  
3. **En skrivbar katalog** – där den genererade XPS‑filen kommer att sparas.

## Importera paket
I ditt Java‑projekt, importera de nödvändiga klasserna:

`XpsDocument` är huvudobjektet som representerar en XPS‑fil.  
`XpsImageBrush` målar former med en bildkälla.  
`XpsTileMode` specificerar hur en bild kaklas.  
`Rectangle2D` beskriver ett rektangulärt område för positionering.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Steg‑för‑steg‑guide

### Steg 1: Ställ in ditt projekt
Lägg till Aspose.Page‑JAR‑filerna i ditt projekts classpath och verifiera att import‑satserna kompilerar utan fel.

### Steg 2: Skapa XPS-dokument
`XpsDocument` är kärnkontainern som innehåller sidor, vägar och resurser. Instansiera den med önskad sidstorlek, så kan du börja lägga till grafiska element.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Steg 3: Definiera sökvägen för den kaklade bilden
Placera bilden du vill kakla (t.ex. `R08LN_NN.jpg`) i katalogen som refereras av `dataDir`. Bilden kommer att användas som ett penselmönster.

### Steg 4: Lägg till kaklad bild
Skapa en rektangulär bana och fyll den med en `XpsImageBrush`. Genom att sätta kakel‑läget till `Tile` upprepas bilden över rektangeln. Justera käll‑ och destinationsrektanglarna för att kontrollera kakelstorlek och positionering.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Steg 5: Spara dokumentet
Spara XPS‑filen till disk. Utdatafilen kommer att innehålla den kaklade bilden du just definierade och kan öppnas med vilken XPS‑visare som helst.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Upprepa dessa steg när du behöver **add tiled image** till andra sidor eller former i samma XPS‑dokument.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| Bild visas inte | Verifiera att filvägen (`dataDir + "R08LN_NN.jpg"`) är korrekt och att bilden är åtkomlig. |
| Kakelmönster ser utdraget ut | Justera käll‑ och destinationsvärdena för `Rectangle2D` för att kontrollera kakelstorleken. |
| Opacitet har ingen effekt | Se till att penselns opacitet sätts **efter** konfigurationen av kakel‑läget. |

## Vanliga frågor

**Q:** Är Aspose.Page kompatibel med alla Java‑versioner?  
**A:** Aspose.Page supports Java 8 through Java 21; you can find the full compatibility matrix [here](https://reference.aspose.com/page/java/).

**Q:** Kan jag använda Aspose.Page för kommersiella projekt?  
**A:** Yes, a commercial license is required for production use. Purchase options are listed [here](https://purchase.aspose.com/buy).

**Q:** Finns en gratis provversion tillgänglig?  
**A:** A fully functional free trial can be downloaded from the Aspose releases page [here](https://releases.aspose.com/).

**Q:** Var kan jag få community‑support?  
**A:** Join the Aspose.Page community forum at [forum](https://forum.aspose.com/c/page/39) to ask questions and share examples.

**Q:** Hur får jag en temporär licens för utvärdering?  
**A:** Temporary licenses are provided on request via the Aspose portal [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
Du har nu ett komplett, produktionsklart arbetsflöde för **how to create XPS**‑dokument med kaklade bilder med hjälp av Aspose.Page för Java. Genom att utnyttja `XpsImageBrush` och `XpsTileMode.Tile` kan du generera rika, upprepade grafik utan att öka filstorleken. Experimentera med olika kakelstorlekar, opacitetsnivåer och former för att bygga sofistikerade dokumentlayouter. I nästa steg, utforska att lägga till vektorformer eller textöverlägg för att ytterligare förbättra dina XPS‑filer.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man lägger till bild i Java XPS-dokument – En enkel guide med Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java – Lägg till sidor i XPS‑handledning](/page/java/xps-page-manipulation/add-page/)
- [Konvertera XPS till PDF i Java med Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}