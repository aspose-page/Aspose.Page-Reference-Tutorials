---
title: Ottieni metadati da XMP utilizzando Java
linktitle: Ottieni metadati da XMP utilizzando Java
second_title: API Java Aspose.Page
description: Sblocca la potenza di Aspose.Page per Java per estrarre facilmente i metadati XMP. Migliora l'analisi dei documenti con la nostra guida passo passo!
weight: 18
url: /it/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni metadati da XMP utilizzando Java

## introduzione
Benvenuti nella nostra guida passo passo sull'utilizzo di Aspose.Page per Java per estrarre metadati dai file XMP. XMP (Extensible Metadata Platform) fornisce un modo standardizzato di archiviare i metadati nei file. Questo tutorial si concentra sul recupero delle informazioni essenziali da XMP utilizzando Java, offrendo approfondimenti sui dettagli del documento.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Java Development Kit (JDK): assicurati di avere Java installato sul tuo computer.
-  Aspose.Page per Java: scarica e installa la libreria Aspose.Page, che puoi trovare[Qui](https://releases.aspose.com/page/java/).
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Passaggio 1: inizializzare il flusso di file EPS di input
Inizia impostando il percorso della directory dei documenti e inizializzando il flusso di file EPS di input.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Passaggio 2: ottieni i metadati XMP
Recupera i metadati XMP dal file EPS. Se il file non dispone di metadati XMP, ne verrà generato uno nuovo con i valori dei commenti dei metadati PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Passaggio 3: estrai le informazioni su CreatorTool
Controlla e stampa il valore "CreatorTool" dai metadati XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Passaggio 4: estrarre le informazioni su CreateDate
Controlla e stampa il valore "CreateDate" dai metadati XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Passaggio 5: recupera la larghezza della miniatura
Se esistono miniature, estrai e stampa la larghezza della prima miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Passaggio 6: estrarre le informazioni sul formato
Controlla e stampa il valore "formato" dai metadati XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Passaggio 7: ottieni l'ID documento
Controlla e stampa il valore "DocumentID" dai metadati XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Conclusione
Congratulazioni! Hai imparato con successo come estrarre i metadati XMP utilizzando Aspose.Page per Java. Questa guida fornisce una panoramica completa del processo, garantendoti la possibilità di recuperare in modo efficace le informazioni essenziali dai tuoi documenti.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java con altri linguaggi di programmazione?
 Sì, Aspose.Page supporta più lingue, tra cui Java, .NET e altro. Controlla il[documentazione](https://reference.aspose.com/page/java/) per dettagli.
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Page per Java?
 Visitare il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il sostegno della comunità.
### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Sono disponibili risorse aggiuntive per Aspose.Page per Java?
 Esplora il completo[documentazione](https://reference.aspose.com/page/java/) e scarica la libreria[Qui](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
