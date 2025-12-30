---
date: 2025-12-30
description: Lär dig hur du skapar XPS‑dokument i Java genom att lägga till rektanglar
  med Aspose.Page. Följ den här steg‑för‑steg‑guiden för sömlös XPS‑dokumenthantering.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Skapa XPS-dokument Java – Lägg till rektangel med Aspose.Page
url: /sv/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa XPS-dokument Java – Lägg till rektangel

## Introduktion
I den här omfattande handledningen kommer du att **skapa XPS-dokument Java**-filer och lära dig hur du lägger till rektanglar med Aspose.Page-biblioteket. Oavsett om du bygger rapporter, fakturor eller anpassad grafik ger behärskning av rektangelskapande dig exakt kontroll över XPS-layouten. Vi går igenom varje steg, förklarar varför bakom varje kodrad och visar hur du anpassar färger och linjer för professionella resultat.

## Snabba svar
- **Vilket bibliotek rekommenderas?** Aspose.Page for Java  
- **Hur lång tid tar implementeringen?** Ungefär 10 minuter för en grundläggande rektangel  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion  
- **Vilken Java-version stöds?** Java 8 och senare  
- **Kan jag lägga till flera former?** Ja – upprepa stegen för varje form

## Förutsättningar
Innan vi dyker ner, se till att du har:

- Grundläggande kunskap om programmeringsspråket Java.  
- Aspose.Page-biblioteket installerat. Om inte, kan du ladda ner det från [Aspose.Page Java-dokumentationen](https://reference.aspose.com/page/java/).  
- En fungerande Java-utvecklingsmiljö (IDE, JDK och Maven/Gradle om du föredrar).

## Importera paket
För att komma igång, importera de nödvändiga paketen i ditt Java-projekt. Se till att Aspose.Page-biblioteket är korrekt tillagt i din classpath. Här är ett grundläggande exempel:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nu ska vi gå igenom det givna exemplet i flera steg för att lägga till en rektangel i Java XPS.

## Steg 1: Ange dokumentkatalogen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot sökvägen till den mapp där du vill lagra XPS-filerna.

## Steg 2: Skapa ett nytt XPS-dokument
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Denna rad **skapar** ett nytt XPS-dokument som du senare kan fylla med former, text eller bilder.

## Steg 3: Lägg till en CMYK-färgad konturrrektangel
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Detta steg lägger till en konturrrektangel med en CMYK-solid färg. Du kan ändra geometristrängen (`"M 20,10 L 220,10 220,100 20,100 Z"`) för att ändra storlek eller position, och justera färgvärdena i `createColor` för att passa din design.

## Steg 4: Spara det resulterande XPS-dokumentet
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Spara slutligen det modifierade XPS-dokumentet med den tillagda rektangeln i den katalog du angav tidigare.

## Vanliga användningsområden
- **Rapporthuvuden** – Använd rektanglar som bakgrundsblock för titlar.  
- **Fakturatafler** – Markera celler eller sektioner med färgade kanter.  
- **Anpassad grafik** – Kombinera flera rektanglar för att skapa komplexa former.

## Felsökningstips
- **Fil‑ej‑hittad‑fel:** Verifiera att `dataDir` pekar på en befintlig mapp och att ICC‑profilen (`uswebuncoated.icc`) finns.  
- **Felaktiga färger:** Se till att ICC‑profilen matchar färgrymden du avser att använda (CMYK vs. RGB).  
- **Oväntade dimensioner:** Justera geometristrängen så att den speglar korrekta koordinater.

## Slutsats
Grattis! Du har nu framgångsrikt lärt dig hur du **skapar XPS-dokument Java**-filer och lägger till rektanglar med Aspose.Page. Denna grund låter dig bygga rikare XPS-dokument, anpassa grafik och integrera former i större arbetsflöden.

## Vanliga frågor

### Kan jag lägga till flera rektanglar i ett enda XPS-dokument?
Ja, du kan lägga till så många rektanglar som behövs genom att upprepa stegen som beskrivs i handledningen.

### Hur kan jag ändra färgen på rektangeln?
Ändra färgvärdena i `createColor`-metoden för att uppnå önskad färg.

### Är Aspose.Page lämplig för att hantera komplexa XPS-dokumentmanipulationer?
Absolut! Aspose.Page erbjuder en robust uppsättning funktioner för att hantera olika XPS-dokumentuppgifter.

### Var kan jag hitta ytterligare exempel och support?
Utforska [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för fler exempel och sök hjälp från communityn.

### Kan jag prova Aspose.Page innan jag köper?
Ja, du kan utforska en [gratis provversion](https://releases.aspose.com/) för att uppleva Aspose.Page:s funktioner.

## Vanliga frågor

**Q: Fungerar detta tillvägagångssätt med Java 11 eller nyare?**  
A: Ja, Aspose.Page‑biblioteket är kompatibelt med Java 8 och senare, inklusive Java 11, 17 och framåt.

**Q: Kan jag bädda in bilder i rektangelområdet?**  
A: Du kan lägga till ett `XpsImage`‑element och placera det över eller i rektangeln med samma geometriska koordinater.

**Q: Hur sätter jag en fyllnadsfärg istället för bara en kantlinje?**  
A: Anropa `path.setFill(...)` med en solid färgborste skapad via `doc.createSolidColorBrush(...)`.

**Q: Är det möjligt att rotera rektangeln?**  
A: Applicera en transformationsmatris på vägen med `path.setTransform(...)` för att uppnå rotation eller skalning.

**Q: Vilken licens krävs för produktionsanvändning?**  
A: En kommersiell Aspose.Page‑licens krävs för distribution; den gratis provversionen är begränsad till utvärdering och utveckling.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-30  
**Testat med:** Aspose.Page for Java 24.12 (latest)  
**Författare:** Aspose