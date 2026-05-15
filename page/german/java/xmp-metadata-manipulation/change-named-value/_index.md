---
date: 2026-05-15
description: Erfahren Sie, wie Sie XMP-Metadaten bearbeiten und XMP-Werte in EPS-Dateien
  mit Aspose.Page for Java ändern – ein klarer Schritt‑für‑Schritt‑Leitfaden.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Benannten Wert in XMP mit Java ändern
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP bearbeiten – Benannten Wert in XMP mit Java ändern
url: /de/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP bearbeiten – Benannten Wert in XMP mit Java ändern

In modernen Dokumenten‑Workflows macht **Aspose.Page for Java** das Lesen, Bearbeiten und Schreiben von XMP‑Metadaten in EPS‑Dateien einfach. **Dieses Tutorial zeigt, wie XMP‑Metadaten** in EPS‑Dokumenten mit der Aspose.Page‑API bearbeitet werden, sodass Sie Ihre Dokumentinformationen genau, durchsuchbar und konform mit Industriestandards halten können. Egal, ob Sie Seitenabmessungen, Autoreninformationen oder benutzerdefinierte Tags aktualisieren, die nachstehenden Schritte führen Sie durch den Prozess in Java.

## Schnelle Antworten
- **Was behandelt dieses Tutorial?** Ändern eines benannten XMP‑Werts in einer EPS‑Datei mit Aspose.Page für Java.  
- **Welche Bibliotheksversion ist erforderlich?** Jede aktuelle Aspose.Page‑Version für Java (die API ist seit mehreren Jahren stabil).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; ein kostenloser Testlauf funktioniert zum Testen.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen Entwickler, der mit Java‑I/O vertraut ist.  
- **Kann ich das mit anderen Dateiformaten verwenden?** Die XMP‑API ist auch für PDF, SVG und andere von Aspose.Page unterstützte Formate verfügbar.

## Was ist XMP‑Metadaten?
XMP (Extensible Metadata Platform) ist ein standardisiertes, XML‑basiertes Format zum Einbetten umfangreicher Metadaten – wie Ersteller, Titel und benutzerdefinierte Eigenschaften – direkt in Dateien. In EPS‑Dokumenten befindet sich XMP neben den traditionellen PostScript‑Kommentaren, sodass Anwendungen Metadaten lesen und ändern können, ohne den visuellen Inhalt zu verändern.

## Warum Aspose.Page für Java zum Bearbeiten von XMP verwenden?
Aspose.Page bietet **vollständige Kontrolle über mehr als 150 XMP‑Schema‑Eigenschaften** und funktioniert konsistent über EPS-, PDF- und SVG‑Formate hinweg. Es verarbeitet Dateien bis zu **500 MB**, ohne das gesamte Dokument in den Speicher zu laden, und enthält eine integrierte Validierung, die sicherstellt, dass das resultierende EPS den Standards entspricht. Keine externen XML‑Parser oder nativen Bibliotheken sind erforderlich.

## Einführung
Aspose.Page für Java ist eine robuste Bibliothek, die die Manipulation und Verarbeitung von EPS‑Dateien erleichtert. Beim Umgang mit XMP‑Metadaten in diesen Dateien gibt Aspose.Page Entwicklern ein umfassendes Funktionsset. In diesem Tutorial konzentrieren wir uns auf das Ändern eines benannten Werts in XMP und bieten eine klare und prägnante Anleitung für Entwickler, die ihre Dokumentenverarbeitungsfähigkeiten erweitern möchten.

## Voraussetzungen
1. **Java-Entwicklungsumgebung** – Ein JDK (8 oder höher) sowie eine IDE oder ein Build‑Tool (Maven/Gradle).  
2. **Aspose.Page für Java‑Bibliothek** – Laden Sie die Aspose.Page‑Bibliothek für Java herunter und integrieren Sie sie in Ihr Projekt. Die Bibliothek und die ausführliche Dokumentation finden Sie [hier](https://reference.aspose.com/page/java/).  
3. **Beispiel‑EPS‑Datei** – Haben Sie eine Beispiel‑EPS‑Datei für Experimente bereit. Wenn Sie keine haben, verwenden Sie die bereitgestellte Beispieldatei mit dem Namen **"xmp4.eps"**.

## Pakete importieren
Die `import`‑Anweisungen bringen die wesentlichen Aspose.Page‑Klassen in den Gültigkeitsbereich.

Die Klasse `PsDocument` ist das Kernobjekt von Aspose.Page, das ein EPS‑Dokument im Speicher repräsentiert.  
Die Klasse `XmpMetadata` bietet Zugriff auf das im EPS‑Datei eingebettete XMP‑Paket.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Wie bearbeitet man XMP‑Metadaten?
Laden Sie die EPS‑Datei, rufen Sie ihr XMP‑Paket ab, ändern Sie die gewünschte Eigenschaft und speichern Sie das Dokument – alles in wenigen einfachen Zeilen. Dieser Ansatz funktioniert für jeden benannten XMP‑Wert, egal ob es sich um ein Standard‑Dublin‑Core‑Feld oder einen von Ihnen definierten benutzerdefinierten Namensraum handelt.

## Schritt 1: Eingabestream für EPS‑Datei initialisieren
`FileInputStream` öffnet einen Nur‑Lese‑Stream zur Quell‑EPS‑Datei, sodass Aspose.Page das Dokument einlesen kann, ohne das Dateisystem zu sperren.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Schritt 2: PsDocument initialisieren
`PsDocument` ist das primäre Objekt, das den EPS‑Inhalt kapselt und Zugriff auf dessen Metadaten, Seiten und Ressourcen bietet.

```java
PsDocument document = new PsDocument(psStream);
```

## Schritt 3: XMP‑Metadaten abrufen
`XmpMetadata` repräsentiert das XMP‑Paket innerhalb der EPS‑Datei und bietet Methoden zum Lesen, Ändern oder Löschen einzelner Eigenschaften.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 4: Neuen Wert in XMP setzen
`setProperty` legt den Wert einer angegebenen XMP‑Eigenschaft im Metadaten‑Paket fest.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Schritt 5: Ausgabestream für EPS‑Datei initialisieren
`FileOutputStream` erstellt einen beschreibbaren Stream zum Speichern der modifizierten EPS‑Datei.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Schritt 6: Dokument mit geändertem XMP‑Metadaten speichern
`save` schreibt das im Speicher befindliche PsDocument, einschließlich des aktualisierten XMP, in den Ausgabestream.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Schritt 7: Eingabestream für EPS schließen
`close` gibt den Dateihandle frei und räumt die mit dem Eingabestream verbundenen Ressourcen auf.

```java
// Close input EPS stream
psStream.close();
```

## Häufige Probleme und Lösungen
- **FileNotFoundException** – Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner zeigt und dass `xmp4.eps` existiert.  
- **LicenseException** – Wenn Lizenzfehler auftreten, stellen Sie sicher, dass vor dem Erzeugen von `PsDocument` eine gültige Aspose.Page‑Lizenzdatei geladen wird.  
- **Metadata Not Updated** – Öffnen Sie nach dem Speichern das resultierende EPS in einem Metadaten‑Viewer (z. B. Adobe Bridge), um zu bestätigen, dass der neue Wert erscheint.

## Häufig gestellte Fragen
**Q: Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?**  
A: Aspose.Page unterstützt hauptsächlich Java, aber Aspose bietet äquivalente Bibliotheken für .NET, C++ und Python, die ähnliche XMP‑Manipulationsfunktionen bereitstellen.

**Q: Gibt es eine kostenlose Testversion von Aspose.Page für Java?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Page für Java [hier](https://releases.aspose.com/) ausprobieren.

**Q: Wo finde ich zusätzliche Unterstützung und Diskussionen zu Aspose.Page für Java?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**Q: Wo kann ich Aspose.Page für Java kaufen?**  
A: Um Aspose.Page für Java zu kaufen, besuchen Sie die [Kaufseite](https://purchase.aspose.com/buy).

**Zuletzt aktualisiert:** 2026-05-15  
**Getestet mit:** Aspose.Page für Java (neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man XMP‑Metadaten mit Java liest – Aspose.Page‑Leitfaden](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java‑Tutorial – XMP‑Metadaten zu EPS‑Dateien hinzufügen](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Werte in XMP mit Java ändern](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}