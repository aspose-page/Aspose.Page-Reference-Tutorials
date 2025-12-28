---
date: 2025-12-28
description: Lär dig hur du skapar XPS-dokument i Java med Aspose.Page och lägger
  till en kaklad bild utan ansträngning med den här steg‑för‑steg‑guiden.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Hur man skapar XPS-dokument med en mosaikbild i Java
url: /sv/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument och lägg till en kaklad bild i Java

## Introduktion
I modern Java-utveckling är förmågan att **skapa XPS-dokument** programatiskt en värdefull färdighet, särskilt när du behöver berika dem med grafik såsom kaklade bilder. Aspose.Page for Java gör denna process enkel, så att du kan fokusera på den visuella designen snarare än låg‑nivå filhantering. I den här handledningen kommer du att lära dig exakt hur du skapar ett XPS-dokument, **lägger till en kaklad bild**, och sparar resultatet, allt med tydliga, steg‑för‑steg kodexempel.

## Snabba svar
- **Vad gör Aspose.Page?** Det tillhandahåller ett hög‑nivå API för att generera och manipulera XPS-dokument i Java.  
- **Kan jag kakla en bild?** Ja – använd `XpsImageBrush` med `XpsTileMode.Tile`.  
- **Behöver jag en licens?** En tillfällig eller kommersiell licens krävs för produktionsanvändning.  
- **Vilken Java-version stöds?** Alla JDK 8+ är kompatibla.  
- **Hur lång tid tar implementeringen?** Ungefär 10–15 minuter för ett grundläggande kaklad‑bild‑scenario.

## Vad är “skapa XPS-dokument”?
En XPS (XML Paper Specification)-fil är ett fast‑layout dokumentformat liknande PDF. Att programatiskt skapa ett XPS-dokument låter dig generera utskrivbara, enhets‑oberoende filer direkt från Java‑kod.

## Varför lägga till en kaklad bild?
Att kakla en bild upprepar grafiken över ett definierat område, vilket är perfekt för bakgrunder, vattenstämplar eller mönsterfyllningar. Genom att använda Aspose.Page’s `XpsTileMode.Tile` kan du uppnå detta med bara några rader kod.

## Förutsättningar
1. **Java Development Kit (JDK)** – JDK 8 eller nyare installerat.  
2. **Aspose.Page for Java** – ladda ner från [webbplatsen](https://releases.aspose.com/page/java/).  
3. **En skrivbar katalog** – där den genererade XPS-filen kommer att sparas.

## Importera paket
I ditt Java‑projekt, importera de nödvändiga klasserna:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Steg‑för‑steg guide

### Steg 1: Ställ in ditt projekt
Lägg till Aspose.Page JAR-filerna i ditt projekts classpath och verifiera att import‑satserna kompilerar utan fel.

### Steg 2: Skapa XPS-dokument
Instansiera ett nytt `XpsDocument`‑objekt. Detta är den centrala behållaren som kommer att hålla alla sidor, vägar och resurser.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Steg 3: Definiera sökvägen för den kaklade bilden
Placera bilden du vill kakla (t.ex. `R08LN_NN.jpg`) i katalogen som refereras av `dataDir`. Bilden kommer att användas som ett penselmönster.

### Steg 4: Lägg till kaklad bild
Skapa en rektangulär bana och fyll den med en `XpsImageBrush`. Genom att sätta kakel‑läget till `Tile` upprepas bilden över rektangeln.

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
Spara XPS-filen till disk. Utdatafilen kommer att innehålla den kaklade bilden du just definierade.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Upprepa dessa steg när du behöver **lägga till en kaklad bild** på andra sidor eller former inom samma XPS-dokument.

## Vanliga problem och lösningar
| Problem | Lösning |
|---------|----------|
| Bild visas inte | Verifiera att filvägen (`dataDir + "R08LN_NN.jpg"`) är korrekt och att bilden är åtkomlig. |
| Kakelmönstret ser utdraget ut | Justera käll- och destinationsvärdena för `Rectangle2D` för att kontrollera kakelstorleken. |
| Opaciteten har ingen effekt | Se till att penselns opacitet är inställd **efter** kakel‑lägeskonfigurationen. |

## Vanliga frågor

### Är Aspose.Page kompatibel med alla Java-versioner?
Aspose.Page är designat för att fungera med olika Java-versioner. Säkerställ kompatibilitet genom att kontrollera dokumentationen [här](https://reference.aspose.com/page/java/).

### Kan jag använda Aspose.Page för kommersiella projekt?
Ja, Aspose.Page erbjuder kommersiella licenser. Köp dem [här](https://purchase.aspose.com/buy).

### Finns en gratis provversion tillgänglig?
Ja, utforska Aspose.Page-funktioner med en gratis provversion [här](https://releases.aspose.com/).

### Var kan jag hitta community‑stöd och diskussioner?
Engagera dig med Aspose.Page‑communityn på [forumet](https://forum.aspose.com/c/page/39).

### Hur kan jag skaffa en tillfällig licens för Aspose.Page?
Skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-28  
**Testat med:** Aspose.Page for Java 24.12 (latest)  
**Författare:** Aspose