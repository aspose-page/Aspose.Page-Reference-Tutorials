---
date: 2026-03-13
description: Lär dig hur du lägger till gradient i XPS-dokument i Java med Aspose.Page
  och hur du anpassar gradientstopp för fantastiska horisontella effekter.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Hur man lägger till en gradient – Horisontell gradient i Java XPS
url: /sv/java/xps-gradient-addition/horizontal/
weight: 11
---

 all.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så lägger du till gradient – Horisontell gradient i Java XPS

## Introduktion
Välkommen till denna steg‑för‑steg‑guide om **hur man lägger till gradient** i ett XPS‑dokument med Java. I den här handledningen kommer du att lära dig hur du lägger till en horisontell gradient, varför den är viktig för visuell förfinning, och hur du **anpassar gradientstopp** för exakt färgkontroll. Aspose.Page for Java gör det enkelt att arbeta med XPS (XML Paper Specification)-dokument, så att du kan fokusera på design snarare än låg‑nivå filhantering.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page for Java  
- **Vilken Java‑version fungerar?** Alla Java 8+‑runtime  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion  
- **Kan jag ändra gradientens riktning?** Ja – ändra bara start‑/slutpunkterna för den linjära penseln  
- **Är det möjligt att lägga till flera gradienter?** Absolut – upprepa stegen för att skapa sökväg med olika penslar  

## Vad är en horisontell gradient i XPS?
En horisontell gradient är en mjuk övergång av färger från vänster till höger över en form. I XPS representeras den av en linjär gradientpensel som interpolerar mellan definierade **gradientstopp**. Denna visuella effekt används ofta för bannrar, knappar och bakgrundsfyllningar.

## Varför använda Aspose.Page for Java?
- **Fullt XPS‑stöd** – skapa, redigera och rendera utan tredjepartsverktyg.  
- **Enkelt API** – hög‑nivå‑objekt som `XpsDocument`, `XpsPath` och `XpsGradientBrush` döljer XML‑komplexiteten.  
- **Prestanda** – optimerad för stora dokument och batch‑behandling.  

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java‑utvecklingsmiljö** – Installera den senaste JDK:n från [java.com](https://www.java.com).  
2. **Aspose.Page for Java‑bibliotek** – Ladda ner JAR‑filen från [Aspose.Page for Java-dokumentationen](https://reference.aspose.com/page/java/).  

## Importera paket
Börja med att importera de nödvändiga klasserna. Dessa importeringar ger dig åtkomst till dokumentskapande, gradienthantering och grundläggande geometri.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Steg 1: Initiera XPS‑dokumentet
Skapa en ny `XpsDocument`‑instans och ange mappen där du vill spara resultatet.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Steg 2: Skapa horisontell gradient
Definiera en lista med **gradientstopp** som styr färg och position för varje övergångspunkt. Exemplet nedan bygger en livfull regnbågs‑liknande gradient.

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

### Hur man anpassar gradientstopp
- **Färg** – Använd `doc.createColor(alpha, red, green, blue)` för att ange vilket ARGB‑värde som helst.  
- **Position** – Det andra argumentet (`float` mellan `0` och `1`) definierar var stoppet visas längs gradientlinjen. Justera dessa värden för att flytta färger åt vänster eller höger.

## Steg 3: Lägg till sökväg med gradient
Skapa en rektangulär sökväg, applicera en transformering om det behövs, och fyll den med den linjära gradientpenseln. Penseln använder två punkter (`(10,0)` till `(228,0)`) för att skapa en horisontell effekt. Eftersom Y‑koordinaterna är identiska fungerar denna pensel som en **horisontell gradientpensel**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Proffstips:** Att återanvända samma `stops`‑lista för flera sökvägar kan förbättra prestandan, men kom ihåg att `clear()` den innan du lägger till nya stopp.

## Steg 4: Spara dokumentet
Spara XPS‑filen på disk. Du kan nu öppna den med vilken XPS‑visare som helst för att se den horisontella gradienten i aktion.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Hur man applicerar flera gradienter
Om du vill **applicera flera gradienter** i samma XPS‑dokument, upprepa helt enkelt stegen “Skapa horisontell gradient” och “Lägg till sökväg med gradient” för varje ny form. Använd en ny lista med `XpsGradientStop`‑objekt (eller rensa den befintliga listan) och tilldela en ny `LinearGradientBrush` med egna start‑/slutpunkter. Detta tillvägagångssätt låter dig lagra gradienter, skapa komplexa bakgrunder eller markera olika UI‑element på en enda sida.

## Varför detta är viktigt – Fördelar med den horisontella gradientpenseln
- **Visuell djup:** En horisontell gradientpensel ger en subtil tredimensionell känsla utan extra bilder.  
- **Filstorleks‑effektivitet:** Gradienter lagras som vektordefinitioner, vilket håller XPS‑filen lätt.  
- **Skalbarhet:** Eftersom gradienten är vektorbaserad skalas den rent på högupplösta skärmar.  

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| Gradienten visas som solid | Inga gradientstopp har lagts till eller penseln är inte inställd | Se till att `path.setFill(...)` använder en `LinearGradientBrush` och att stopp läggs till via `getGradientStops().addAll(stops)`. |
| Färgerna ser dämpade ut | Felaktigt alfa‑värde (första parametern) | Använd `255` för helt ogenomskinliga färger om inte transparens önskas. |
| Sökvägens storlek är fel | Värdena i transform‑matrisen är felaktiga | Justera matrisparametrarna (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Vanliga frågor

**Q: Kan jag applicera flera gradienter i ett enda XPS‑dokument?**  
A: Ja, du kan lägga till flera sökvägar, var och en med sin egen gradientpensel, för att skapa komplexa lagerdesigns.

**Q: Är Aspose.Page kompatibel med de senaste Java‑versionerna?**  
A: Aspose.Page for Java uppdateras regelbundet och fungerar med Java 8 och nyare versioner.

**Q: Finns det andra gradienttyper tillgängliga i Aspose.Page?**  
A: Förutom linjära gradienter stödjer Aspose.Page även radiella gradienter för cirkulära färgövergångar.

**Q: Kan jag anpassa färgerna och positionerna för gradientstopp?**  
A: Absolut! Du har full kontroll över varje stopp’s ARGB‑färg och dess relativa position (0‑1‑intervall).

**Q: Finns det ett community‑forum för Aspose.Page där jag kan få hjälp?**  
A: Ja, du kan besöka [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för att ansluta till communityn och få hjälp.

**Senast uppdaterad:** 2026-03-13  
**Testad med:** Aspose.Page for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}