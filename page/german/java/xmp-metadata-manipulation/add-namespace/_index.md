---
title: Namespace in XMP mit Java hinzufügen
linktitle: Namespace in XMP mit Java hinzufügen
second_title: Aspose.Page Java-API
description: Nutzen Sie die Möglichkeiten der Dokumentbearbeitung mit Aspose.Page für Java. Erfahren Sie in diesem umfassenden Leitfaden, wie Sie mühelos XMP-Namespaces hinzufügen.
weight: 13
url: /de/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Namespace in XMP mit Java hinzufügen


## Einführung

Im Bereich der Dokumentenmanipulation zeichnet sich Aspose.Page für Java als robustes Tool aus, das eine breite Palette an Funktionalitäten bietet. Eine leistungsstarke Funktion ist die Möglichkeit, Namespaces in XMP (Extensible Metadata Platform) mithilfe von Java hinzuzufügen. Dieses Tutorial führt Sie durch den Prozess und unterteilt ihn in leicht verständliche Schritte.

## Voraussetzungen

Bevor Sie sich mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für Java: Stellen Sie sicher, dass die Bibliothek installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).

- Java-Entwicklungsumgebung: Richten Sie eine Java-Umgebung auf Ihrem System ein.

- Dokumentdatei: Besitzen Sie eine EPS-Datei mit XMP-Metadaten. Wenn es keine XMP-Metadaten enthält, erstellt die Bibliothek eines basierend auf PS-Metadatenkommentaren.

## Pakete importieren

Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Schritt 1: XMP-Metadaten abrufen

```java

// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Initialisieren Sie den EPS-Eingabedateistream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erstellen Sie eine neue Datei mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 2: Neuen Namespace registrieren

```java
// Neuen XML-Namespace „http://www.some.org/schema/tmp#“ mit Präfix „tmp“ hinzufügen
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Schritt 3: Neue Eigenschaft hinzufügen

```java
// Fügen Sie die neue Eigenschaft „tmp:newKey“ im neuen XML-Namespace hinzu
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Schritt 4: Dokument speichern

```java
// Ausgabe-EPS-Dateistream initialisieren
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Dokument mit geänderten XMP-Metadaten speichern
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Schritt 5: Streams schließen

```java
// Schließen Sie den Eingabe-EPS-Stream
psStream.close();
```

Jetzt haben Sie mit Aspose.Page für Java erfolgreich einen Namespace in XMP hinzugefügt. Entdecken Sie gerne weitere Funktionen und nutzen Sie das volle Potenzial dieser Bibliothek.

## Abschluss

Aspose.Page für Java vereinfacht die komplexe Aufgabe der Bearbeitung von XMP-Metadaten in EPS-Dateien. Durch das Befolgen dieser Schritt-für-Schritt-Anleitung haben Sie wertvolle Fähigkeiten erworben, um Ihre Fähigkeiten zur Dokumentenverarbeitung zu verbessern.

## FAQs

### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, es sind jedoch Versionen für andere Sprachen wie .NET verfügbar.

### Gibt es eine kostenlose Testversion?
 Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).

### Wo finde ich eine umfassende Dokumentation?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/page/java/).

### Wie kann ich eine temporäre Lizenz erhalten?
 Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).

### Gibt es Community-Foren für Aspose.Page?
 Ja, Sie können mit der Community auf der interagieren[Aspose.Page-Forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
