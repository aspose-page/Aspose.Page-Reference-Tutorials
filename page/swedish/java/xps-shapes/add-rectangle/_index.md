---
date: 2026-04-24
description: Lär dig hur du anger rektangelns färg och lägger till en rektangel i
  Java XPS med Aspose.Page. Denna guide täcker hur man lägger till en rektangel i
  Java och ändrar rektangelns linje.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Lägg till rektangel i Java XPS
second_title: Aspose.Page Java API
title: Ställ in rektangelns färg och lägg till rektangel i Java XPS
url: /sv/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in rektangelns färg och lägg till rektangel i Java XPS

## Introduktion
I den här guiden kommer du att lära dig hur du **set rectangle color** och **add a rectangle** i Java XPS med hjälp av Aspose.Page-biblioteket. Oavsett om du behöver rita enkla former för en rapport eller skapa komplexa vektorgrafik, ger behärskning av rektangelstilar exakt kontroll över dina XPS-dokument.  

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page for Java  
- **Kan jag ändra rektangelns kontur?** Ja, med `setStroke` och `setStrokeThickness`  
- **Stöds en CMYK-färgprofil?** Absolut – du kan ladda ICC-profiler som visas  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens krävs för icke‑utvärderingsbruk  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter för en grundläggande rektangel

## Vad är **set rectangle color**?
Att sätta en rektangels färg innebär att definiera fyllnings‑ eller konturfärgen som formen kommer att renderas med i det slutgiltiga XPS-dokumentet. Med Aspose.Page kan du använda RGB, CMYK eller till och med anpassade ICC-färgprofiler för att uppnå exakt färgmatchning.

## Varför använda Aspose.Page för att **add rectangle java** och **change rectangle stroke**?
- **Full‑featured API** – stödjer både solida färger och gradienter.  
- **Cross‑platform** – fungerar på alla Java‑runtime utan inhemska beroenden.  
- **Rich geometry support** – skapa komplexa banor, applicera transformationer och hantera konturens tjocklek enkelt.  

## Förutsättningar
Innan vi dyker ner i koden, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page‑biblioteket installerat. Om inte, ladda ner det från [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- En fungerande Java‑utvecklingsmiljö (IDE, JDK, osv.).  

## Importera paket
För att komma igång, importera de nödvändiga paketen i ditt Java‑projekt. Säkerställ att Aspose.Page‑biblioteket är korrekt tillagt i din classpath. Här är ett grundläggande exempel:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nu ska vi gå igenom exemplet i flera steg för att **add a rectangle** och **set its color** i Java XPS.

## Steg 1: Ställ in dokumentkatalogen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Byt ut `"Your Document Directory"` mot den absoluta sökvägen där du vill läsa/skriva XPS‑filer.

## Steg 2: Skapa ett nytt XPS‑dokument
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Denna rad initierar ett nytt XPS‑dokument som kommer att innehålla våra former.

## Steg 3: Lägg till en CMYK-solidfärgad konturrektangel
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Detta steg lägger till en **stroked rectangle** med en CMYK‑solid färg. Metoden `setStroke` definierar rektangelns konturfärg, medan `setStrokeThickness` styr linjebredden – perfekt för **changing rectangle stroke**.

### Pro tip:
Om du föredrar en RGB‑färg, ersätt anropet `createColor` med `doc.createColor(0, 0, 255)` för en solid blå fyllning.

## Steg 4: Spara det resulterande XPS‑dokumentet
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Till sist sparas XPS‑dokumentet till disk. Filen `AddRectangle_out.xps` innehåller nu en rektangel vars färg och kontur du har definierat.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|----------|
| **Rectangle not visible** | Felaktig path‑geometri eller kontur‑tjocklek satt till 0 | Verifiera path‑strängen (`"M 20,10 L 220,10 220,100 20,100 Z"`) och säkerställ att `setStrokeThickness` är större än 0. |
| **Wrong color** | Använder en ICC‑profil som inte matchar det avsedda färgrymdet | Använd `doc.createColor(r, g, b)` för RGB eller dubbelkolla ICC‑filens sökväg. |
| **File not saved** | `dataDir` pekar på en icke‑existerande mapp eller saknar skrivbehörighet | Skapa mappen i förväg eller välj en skrivbar plats. |

## Vanliga frågor

**Q:** *Kan jag lägga till flera rektanglar i ett enda XPS‑dokument?*  
**A:** Ja. Upprepa helt enkelt geometrisk skapande‑ och stiliseringssteg för varje rektangel du behöver.

**Q:** *Hur kan jag ändra rektangelns fyllningsfärg istället för konturen?*  
**A:** Använd `path.setFill(...)` med en solid färgborste, på samma sätt som `setStroke` används.

**Q:** *Är Aspose.Page lämpligt för komplexa XPS‑dokumentmanipulationer?*  
**A:** Absolut. Biblioteket stödjer avancerade funktioner som gradienter, transformationer och inbäddade typsnitt.

**Q:** *Var kan jag hitta fler exempel och gemenskapsstöd?*  
**A:** Utforska [Aspose.Page forum](https://forum.aspose.com/c/page/39) för fler kodexempel och hjälp från andra användare.

**Q:** *Kan jag prova Aspose.Page innan jag köper?*  
**A:** Ja, du kan utforska en [free trial](https://releases.aspose.com/) för att utvärdera API‑funktionerna.

---

**Senast uppdaterad:** 2026-04-24  
**Testat med:** Aspose.Page for Java 24.12  
**Författare:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}