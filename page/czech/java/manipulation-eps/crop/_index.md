---
date: 2026-09-04
description: Naučte se, jak snížit velikost souboru EPS ořezáním souborů EPS v Javě
  pomocí Aspose.Page – podrobný návod, který ukazuje, jak oříznout EPS, oříznout obrázek
  EPS a oříznout soubor EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Oříznout soubor EPS v Javě
og_description: Naučte se, jak snížit velikost souboru EPS ořezáním souborů EPS v
  Javě pomocí Aspose.Page – stručný návod s kódem a tipy.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Jak oříznout soubory EPS v Javě pro snížení velikosti souboru EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Jak oříznout soubory EPS v Javě pro snížení velikosti souboru EPS
url: /cs/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak oříznout soubory EPS v Javě a snížit velikost souboru EPS

## Úvod
Pokud potřebujete **ořezávat EPS** soubory programově v aplikaci Java a chcete **snížit velikost souboru EPS**, jste na správném místě. V tomto tutoriálu projdeme celý proces ořezávání EPS obrázku pomocí výkonné knihovny Aspose.Page pro Java. Na konci průvodce pochopíte, proč je ořezávání EPS důležité, uvidíte přesný kód, který potřebujete, a budete připraveni integrovat řešení do vlastních projektů.

## Rychlé odpovědi
- **Jaká knihovna provádí ořezávání EPS v Javě?** Aspose.Page for Java.  
- **Jak dlouho trvá implementace základního ořezu?** Approximately 5‑10 minutes.  
- **Potřebuji licenci pro vývoj?** A free trial works for evaluation; a commercial license is required for production.  
- **Které verze Javy jsou podporovány?** Java 8 and newer.  
- **Mohu definovat vlastní ohraničující rámeček?** Yes – you provide the coordinates you need.

## Co je ořezávání EPS a proč jej používat?
**Ořezávání EPS vytváří nový ohraničující rámeček, který určuje viditelnou oblast souboru EPS.**  
Ořezání souboru EPS odstraňuje nežádoucí prázdný prostor a ořezává grafiku na oblast, kterou skutečně potřebujete, což přímo **snižuje velikost souboru EPS** a zlepšuje konzistenci rozvržení v následných dokumentech, jako jsou PDF nebo zprávy.

## Proč ořezávat soubory EPS?
Ořezávání souborů EPS vám umožní **zmenšit velikost souboru až o 30 %**, odstranit nadbytečné okraje a standardizovat grafiku pro dávkové zpracování. Je to zvláště užitečné, když potřebujete vložit mnoho EPS zdrojů do jednoho PDF nebo když chcete urychlit vykreslování na zařízeních s nízkým výkonem.

## Požadavky
Než se ponoříme do kódu, ujistěte se, že máte:

- **Aspose.Page for Java** knihovnu nainstalovanou – stáhněte ji z oficiální stránky [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 nebo novější nainstalovaný na vašem počítači.  
- **Složku** pro uložení vstupního EPS (`input.eps`) a výsledného oříznutého souboru (`output_crop.eps`).

## Import balíčků
Nejprve importujte potřebné třídy Java. Tento úryvek zůstává přesně stejný jako v originálním tutoriálu:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Jak oříznout EPS obrázek v Javě
Načtěte svůj zdrojový EPS, definujte nový ohraničující rámeček a zavolejte API pro ořezávání – celá operace je dokončena v pěti stručných krocích.

### Krok 1: nastavit adresář dokumentu a vstupní stream
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Zde ukazujeme kód na složku, která obsahuje náš zdrojový EPS soubor, a otevíráme stream pro jeho čtení.

### Krok 2: inicializovat objekt PsDocument
Třída `PsDocument` představuje EPS soubor v paměti, což vám umožňuje číst a měnit jeho vlastnosti.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
Objekt vám poskytuje přístup k původnímu ohraničujícímu rámečku a dalším metadatům.

### Krok 3: extrahovat počáteční ohraničující rámeček
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extrahování původního ohraničujícího rámečku vám poskytne souřadnice aktuální viditelné oblasti – užitečné pro rozhodnutí, kolik chcete oříznout.

### Krok 4: vytvořit výstupní stream
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Otevřeme stream, do kterého bude oříznutý EPS zapsán.

### Krok 5: definovat nový ohraničující rámeček a oříznout
Metoda `cropEps` ořízne dokument na nový ohraničující rámeček a zapíše výsledek do výstupního streamu.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Zadejte čtyři souřadnice (dolní‑levý x, dolní‑levý y, horní‑pravý x, horní‑pravý y), které definují oblast, kterou chcete zachovat. Metoda provede ořez a zapíše výsledek do `output_crop.eps`.

## Časté problémy a řešení
- **Nesprávné souřadnice:** EPS používá body (1/72 palce). Pokud ořez vypadá nesprávně, zkontrolujte převod jednotek.  
- **Chyby souboru nenalezen:** Ujistěte se, že `dataDir` končí správným oddělovačem cesty (`/` nebo `\`).  
- **Výjimky licence:** Spuštění kódu bez platné licence může do výstupu přidat vodoznak. Použijte svou dočasnou nebo trvalou licenci před nasazením do výroby.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s Java 8?**  
A: Ano, Aspose.Page funguje s Java 8 a jakoukoliv novější verzí.

**Q: Mohu používat Aspose.Page pro komerční projekty?**  
A: Rozhodně. Pro nasazení do výroby je vyžadována komerční licence. Můžete ji získat na [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Kde mohu najít další zdroje a podporu komunity?**  
A: Navštivte oficiální [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro diskuze, ukázky kódu a tipy na řešení problémů.

**Q: Je k dispozici bezplatná zkušební verze pro testování?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Page ze stránky vydání [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro krátkodobé hodnocení?**  
A: Dočasnou licenci lze požádat prostřednictvím portálu licencí [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní víte, **jak ořezávat soubory EPS** v Javě pomocí Aspose.Page k **snížení velikosti souboru EPS**. Definováním vlastního ohraničujícího rámečku a voláním `cropEps` můžete odstranit nežádoucí okraje nebo izolovat konkrétní části EPS grafiky pomocí několika řádků kódu. Začleňte tento úryvek do svých větších pipeline pro zpracování dokumentů, abyste automatizovali manipulaci s EPS, **ořezávali EPS obrázky** a **zkracovali obsah EPS souborů** efektivně.

---

**Poslední aktualizace:** 2026-09-04  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Jak změnit velikost EPS souborů v Javě s Aspose.Page](/page/java/manipulation-eps/resize/)
- [Převést EPS na PNG pomocí Aspose.Page Java (Měřená licence)](/page/java/license-management/set-metered-license/)
- [Aspose Page Java tutoriál – Přidat XMP metadata do EPS souborů](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}