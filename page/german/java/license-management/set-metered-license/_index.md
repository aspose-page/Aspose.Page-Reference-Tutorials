---
date: 2025-12-03
description: Erfahren Sie, wie Sie EPS mit Aspose.Page für Java als PNG speichern
  und dabei eine nutzungsbasierte Lizenz konfigurieren. Schritt‑für‑Schritt‑Anleitung
  mit vollständigem Codebeispiel.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: EPS als PNG mit Aspose.Page Java speichern (Metered‑Lizenz)
url: /de/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS als PNG speichern mit Aspose.Page Java (Metered License)

## Einführung
Wenn Sie **EPS als PNG speichern** in einer Java‑Anwendung benötigen und eine unkomplizierte Möglichkeit zur Lizenzverwaltung suchen, sind Sie hier genau richtig. Dieses Tutorial führt Sie Schritt für Schritt durch die Konfiguration einer metered Lizenz für Aspose.Page, das Laden einer PostScript‑ (EPS‑) Datei und die Konvertierung in ein PNG‑Bild – alles mit klaren, leicht nachvollziehbaren Schritten, die Sie sofort umsetzen können.

## Schnelle Antworten
- **Was bedeutet „EPS als PNG speichern“?** Es konvertiert eine vektorbasierte EPS‑Datei in ein Raster‑PNG‑Bild.  
- **Warum eine metered Lizenz verwenden?** Sie zahlen nur für die Seiten, die Sie verarbeiten, ideal für variable Arbeitslasten.  
- **Benötige ich eine Internetverbindung?** Nein, die metered Schlüssel werden lokal validiert.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.  
- **Wie lange dauert die Einrichtung?** Etwa 10 Minuten für eine Grundimplementierung.

## Was bedeutet „EPS als PNG speichern“?
Das Speichern von EPS als PNG wandelt ein skalierbares Encapsulated PostScript‑Dokument in ein weit verbreitetes Bitmap‑Format um. PNG behält Transparenz bei und bietet verlustfreie Kompression, was es ideal für Web‑Grafiken, Thumbnails und Druckvorschauen macht.

## Warum Aspose.Page für diese Aufgabe verwenden?
- **Pure Java API** – keine nativen Abhängigkeiten.  
- **Hohe Treue** – Vektorgrafiken werden exakt gerendert.  
- **Metered Lizenzierung** – Sie zahlen nur für das, was Sie konvertieren.  
- **Unterstützung mehrerer Ausgabeformate** – PNG, JPEG, TIFF usw.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Page‑Bibliothek installiert – laden Sie sie von [hier](https://releases.aspose.com/page/java/) herunter.  
- Metered öffentliche und private Schlüssel, die Sie über Ihr Aspose‑Konto erhalten können.

## Pakete importieren
Importieren Sie zuerst die Klassen, die wir benötigen. Lassen Sie den Import‑Block exakt so, wie er gezeigt wird, damit der Code ohne Änderungen kompiliert.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Schritt 1: Dokument und Bildformat initialisieren
Hier setzen wir die metered Schlüssel und definieren das Ausgabeformat (PNG). Dies ist die Grundlage für die **EPS als PNG speichern**‑Operation.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Schritt 2: PostScript‑Eingabestream initialisieren
Öffnen Sie die EPS‑Datei, die Sie konvertieren möchten. Der Stream liefert das Dokument an Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Schritt 3: Dokumentlizenz prüfen
Überprüfen Sie immer, dass die metered Lizenz korrekt angewendet wurde, bevor Sie mit der Verarbeitung beginnen.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Schritt 4: Optionen und Bild‑Device initialisieren
Erstellen Sie das Options‑Objekt, das die Konvertierungseinstellungen steuert, und das Device, das das gerenderte Bild empfängt.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Schritt 5: EPS‑Datei als Bild speichern
Dies ist der Kernaufruf für **EPS als PNG speichern**. Das Dokument wird mit den konfigurierten Optionen in das Bild‑Device gerendert.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Schritt 6: Bild‑Bytes abrufen und speichern
Extrahieren Sie die PNG‑Bytes aus dem Device und schreiben Sie sie auf die Festplatte.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Lizenz wird nicht erkannt** | Schlüssel sind falsch oder in falscher Reihenfolge angegeben. | Überprüfen Sie die öffentlichen/privaten Schlüssel‑Strings und stellen Sie sicher, dass `setMeteredKey` vor jeglicher Dokumentverarbeitung aufgerufen wird. |
| **Ausgabedatei ist leer** | `device.getImagesBytes()` hat `null` zurückgegeben. | Vergewissern Sie sich, dass die EPS‑Datei gültig ist und dass die `ImageSaveOptions` nicht auf eine Canvas‑Größe von Null gesetzt sind. |
| **OutOfMemoryError bei großen EPS** | Das Rendern großer Vektordateien verbraucht viel Speicher. | Verarbeiten Sie Seiten einzeln oder erhöhen Sie den JVM‑Heap (`-Xmx2g`). |

## Häufig gestellte Fragen

**F: Wie erhalte ich die metered öffentlichen und privaten Schlüssel?**  
A: Sie können diese Schlüssel über Ihr Aspose‑Konto erhalten.

**F: Ist die Aspose.Page‑Bibliothek kostenlos?**  
A: Aspose.Page bietet sowohl eine kostenlose Testversion als auch kostenpflichtige Versionen. Besuchen Sie [hier](https://releases.aspose.com/) für eine kostenlose Testversion.

**F: Kann ich Aspose.Page für kommerzielle Projekte nutzen?**  
A: Ja, Aspose.Page bietet kommerzielle Lizenzen. Sie können sie [hier](https://purchase.aspose.com/buy) erwerben.

**F: Wo finde ich zusätzliche Dokumentation?**  
A: Siehe die Dokumentation [hier](https://reference.aspose.com/page/java/).

**F: Wie kann ich temporäre Lizenzen erhalten?**  
A: Temporäre Lizenzen können Sie [hier](https://purchase.aspose.com/temporary-license/) erhalten.

---

**Zuletzt aktualisiert:** 2025-12-03  
**Getestet mit:** Aspose.Page 24.12 für Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}