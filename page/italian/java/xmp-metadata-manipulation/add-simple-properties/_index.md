---
title: Aggiungi proprietà semplici in XMP utilizzando Java
linktitle: Aggiungi proprietà semplici in XMP utilizzando Java
second_title: API Java Aspose.Page
description: Sblocca Aspose.Page per il potenziale di Java con la nostra guida sull'aggiunta di proprietà ai metadati XMP nei file EPS. Migliora l'elaborazione dei documenti senza sforzo!
weight: 14
url: /it/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi proprietà semplici in XMP utilizzando Java

## introduzione
Nel panorama in continua evoluzione dell’elaborazione dei documenti, la gestione efficiente dei metadati è fondamentale. Aspose.Page per Java consente agli sviluppatori di manipolare i dati XMP (Extensible Metadata Platform) senza problemi. In questo tutorial esploreremo il processo di aggiunta di semplici proprietà a XMP utilizzando Java, fornendoti una guida passo passo completa.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Aspose.Page per la libreria Java installata. Puoi scaricarlo[Qui](https://releases.aspose.com/page/java/).
- Un file EPS di esempio contenente metadati. Se non ne hai uno, sentiti libero di utilizzare il file "xmp3.eps" fornito.
## Importa pacchetti
Assicurati di importare i pacchetti necessari per avviare il tuo progetto:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Passaggio 1: ottieni i metadati XMP
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Inizializza il flusso di file EPS di input
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Ottieni metadati XMP. Se il file EPS non contiene metadati XMP, ne otteniamo uno nuovo pieno di valori dai commenti sui metadati PS (%%Creator, %%CreateDate, %%Title, ecc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Passaggio 2: aggiungi la proprietà della data
```java
// Aggiungi il valore "xmp:Date1" alla proprietà della data
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Passaggio 3: aggiungi la proprietà intera
```java
// Aggiungi il valore della proprietà intera "xmp:Intg1".
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Passaggio 4: aggiungi la doppia proprietà
```java
// Aggiungi il valore della doppia proprietà "xmp:Double1".
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Passaggio 5: aggiungi la proprietà della stringa
```java
// Aggiungi il valore della proprietà stringa "xmp:String1".
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Passaggio 6: salva il documento
```java
// Inizializza il flusso di file EPS di output
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Salva il documento con i metadati XMP modificati
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Passaggio 7: chiudi i flussi
```java
// Chiudi il flusso EPS di input
psStream.close();
```
## Conclusione
Aspose.Page per Java semplifica il processo di manipolazione dei metadati XMP nei file EPS. Seguendo questa guida passo passo, puoi aggiungere facilmente proprietà semplici per migliorare i metadati del tuo documento.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java con altri linguaggi di programmazione?
Aspose.Page supporta principalmente Java, ma sono disponibili versioni per altri linguaggi come .NET.
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi esplorare le funzionalità di Aspose.Page ottenendo una prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione dettagliata per Aspose.Page per Java?
 La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 È possibile acquisire una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso acquistare Aspose.Page per Java?
 È possibile acquistare il prodotto[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
