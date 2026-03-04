---
date: 2025-12-21
description: Aspose Page XMP‑Tutorial – Erfahren Sie, wie Sie XMP‑Metadaten in EPS‑Dateien
  mit Aspose.Page für Java in einer klaren, Schritt‑für‑Schritt‑Anleitung ändern.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page XMP Tutorial – Benannten Wert in XMP mit Java ändern
url: /de/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Page XMP Tutorial – Benannten Wert in XMP mit Java ändern

In modernen Dokumenten-Workflows ermöglicht **Aspose.Page for Java** das einfache Lesen, Bearbeiten und Schreiben von XMP-Metadaten in EPS-Dateien. Dieses **aspose page xmp tutorial** führt Sie durch das Ändern eines benannten Werts im XMP-Paket, sodass Sie Ihre Dokumenten‑Metadaten genau und durchsuchbar halten können. Egal, ob Sie Seitenabmessungen, Autoreninformationen oder benutzerdefinierte Tags aktualisieren, die nachstehenden Schritte zeigen genau, wie Sie dies in Java erledigen.

## Schnelle Antworten
- **Was behandelt dieses Tutorial?** Ändern eines benannten XMP‑Werts in einer EPS‑Datei mit Aspose.Page for Java.  
- **Welche Bibliotheksversion ist erforderlich?** Jede aktuelle Aspose.Page for Java‑Version (die API ist seit mehreren Jahren stabil).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; ein kostenloser Testzeitraum funktioniert zum Testen.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen Entwickler, der mit Java‑I/O vertraut ist.  
- **Kann ich das mit anderen Dateiformaten verwenden?** Die XMP‑API ist auch für PDF, SVG und andere von Aspose.Page unterstützte Formate verfügbar.

## Was ist XMP‑Metadaten?
XMP (Extensible Metadata Platform) ist ein standardisiertes Format zum Einbetten umfangreicher Metadaten – wie Ersteller, Titel und benutzerdefinierte Eigenschaften – direkt in Dateien. In EPS‑Dokumenten befindet sich XMP neben traditionellen PostScript‑Kommentaren, sodass Anwendungen Metadaten lesen und ändern können, ohne den visuellen Inhalt zu verändern.

## Warum Aspose.Page for Java zum Bearbeiten von XMP verwenden?
- **Vollständige Kontrolle** – Zugriff auf jede XMP‑Eigenschaft, einschließlich benutzerdefinierter Strukturen, ohne rohes XML zu parsen.  
- **Konsistenz über Formate hinweg** – dieselbe API funktioniert für EPS, PDF und SVG und vereinfacht die Code‑Wartung.  
- **Keine externen Abhängigkeiten** – reine Java‑Bibliothek, kein nativer Code oder zusätzliche Parser erforderlich.  
- **Robuste Fehlerbehandlung** – integrierte Validierung stellt sicher, dass das resultierende EPS den Standards entspricht.

## Einführung
Aspose.Page for Java ist eine robuste Java‑Bibliothek, die die Manipulation und Verarbeitung von EPS‑Dateien erleichtert. Beim Umgang mit XMP‑Metadaten in diesen Dateien bietet Aspose.Page Entwicklern einen umfassenden Funktionsumfang. In diesem Tutorial konzentrieren wir uns auf das Ändern eines benannten Werts in XMP und bieten eine klare und prägnante Anleitung für Entwickler, die ihre Dokumenten‑Verarbeitungsfähigkeiten erweitern möchten.

## Voraussetzungen
Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Java-Entwicklungsumgebung** – Stellen Sie sicher, dass Sie eine Java‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben.  
2. **Aspose.Page for Java Bibliothek** – Laden Sie die Aspose.Page for Java‑Bibliothek herunter und integrieren Sie sie in Ihr Projekt. Die Bibliothek und ausführliche Dokumentation finden Sie [hier](https://reference.aspose.com/page/java/).  
3. **Beispiel‑EPS‑Datei** – Haben Sie eine Beispiel‑EPS‑Datei für Experimente bereit. Falls Sie keine haben, können Sie die bereitgestellte Beispieldatei mit dem Namen **"xmp4.eps"** verwenden.

## Pakete importieren
Um den Prozess zu starten, importieren Sie die erforderlichen Pakete in Ihrem Java‑Code. Diese Pakete sind für die Interaktion mit Aspose.Page for Java notwendig. Fügen Sie die folgenden Zeilen am Anfang Ihrer Java‑Datei ein:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Nun zerlegen wir den Prozess des Änderns eines benannten Werts in XMP mit Aspose.Page for Java in mehrere Schritte:

## Schritt 1: Eingabestream für EPS‑Datei initialisieren
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Schritt 2: PsDocument initialisieren
```java
PsDocument document = new PsDocument(psStream);
```

## Schritt 3: XMP‑Metadaten abrufen
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 4: Neuen Wert in XMP setzen
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Schritt 5: Ausgabestream für EPS‑Datei initialisieren
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Schritt 6: Dokument mit geändertem XMP‑Metadaten speichern
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Schritt 7: Eingabestream für EPS schließen
```java
// Close input EPS stream
psStream.close();
```

Diese Schritt‑für‑Schritt‑Anleitung gewährleistet einen systematischen Ansatz zum Ändern eines benannten Werts in XMP mit Aspose.Page for Java. Durch das Befolgen dieser Schritte können Sie diese Funktionalität nahtlos in Ihre Java‑Anwendungen integrieren.

## Häufige Probleme und Lösungen
- **FileNotFoundException** – Stellen Sie sicher, dass `dataDir` auf den korrekten Ordner verweist und dass `xmp4.eps` existiert.  
- **LicenseException** – Wenn Lizenzfehler auftreten, stellen Sie sicher, dass vor dem Erzeugen von `PsDocument` eine gültige Aspose.Page‑Lizenzdatei geladen wird.  
- **Metadata Not Updated** – Öffnen Sie nach dem Speichern das resultierende EPS in einem Metadaten‑Viewer (z. B. Adobe Bridge), um zu bestätigen, dass der neue Wert angezeigt wird.

## Fazit
Zusammenfassend vereinfacht Aspose.Page for Java den Umgang mit XMP‑Metadaten in EPS‑Dateien. Dieses Tutorial hat Ihnen das Wissen vermittelt, um effizient einen benannten Wert in XMP zu ändern und Ihre Dokumenten‑Verarbeitungsfähigkeiten zu erweitern.

## Häufig gestellte Fragen
### Kann ich Aspose.Page for Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, aber Aspose bietet ähnliche Bibliotheken für verschiedene Programmiersprachen.

### Gibt es eine kostenlose Testversion von Aspose.Page for Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java [hier](https://releases.aspose.com/) ausprobieren.

### Wo finde ich zusätzliche Unterstützung und Diskussionen zu Aspose.Page for Java?
Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

### Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?
Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Wo kann ich Aspose.Page for Java kaufen?
Um Aspose.Page for Java zu kaufen, besuchen Sie die [Kaufseite](https://purchase.aspose.com/buy).

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.Page for Java (latest release)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
