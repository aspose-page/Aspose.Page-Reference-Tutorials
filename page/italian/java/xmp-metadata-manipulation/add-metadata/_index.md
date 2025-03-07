---
title: Aggiungi metadati in XMP utilizzando Java
linktitle: Aggiungi metadati in XMP utilizzando Java
second_title: API Java Aspose.Page
description: Esplora la perfetta integrazione di Aspose.Page per Java e scopri come aggiungere metadati XMP ai tuoi file EPS senza sforzo. Migliora il tuo gioco di gestione dei documenti oggi!
weight: 11
url: /it/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi metadati in XMP utilizzando Java

## introduzione
Desideri migliorare i metadati del tuo documento aggiungendo informazioni XMP utilizzando Java? Non guardare oltre! Questa guida passo passo ti guiderà attraverso il processo di aggiunta di metadati a un file EPS utilizzando la libreria Aspose.Page per Java. Aspose.Page è un potente strumento che semplifica le attività di manipolazione dei documenti nelle applicazioni Java.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Aspose.Page per la libreria Java installata. Puoi scaricarlo[Qui](https://releases.aspose.com/page/java/).
- Un file EPS che desideri modificare.
## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nel tuo programma Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Passaggio 1: ottieni i metadati XMP
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Inizializza il flusso di file EPS di input
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Ottieni metadati XMP. Se il file EPS non contiene metadati XMP, ne viene creato uno nuovo utilizzando i valori dei commenti sui metadati PS (%%Creator, %%CreateDate, %%Title, ecc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Assicurati di sostituire la "Directory dei tuoi documenti" con il percorso effettivo in cui sono archiviati i tuoi documenti.

## Passaggio 2: recupera il valore di CreatorTool
```java
// Ottieni il valore "CreatorTool".
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Passaggio 3: recuperare il valore CreateDate
```java
// Ottieni il valore "CreateDate".
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Passaggio 4: recuperare il valore del titolo
```java
// Ottieni il valore "Titolo".
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Passaggio 5: recuperare il valore del formato
```java
//Ottieni il valore "formato".
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Passaggio 6: recupera il valore creativo
```java
// Ottieni il valore "creatore".
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Passaggio 7: recuperare il valore MetadataDate
```java
// Ottieni il valore "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Passaggio 8: salva il documento con i nuovi metadati XMP
```java
// Inizializza il flusso di file EPS di output
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Salva il documento con i nuovi metadati XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Infine, non dimenticare di chiudere il flusso EPS di input:
```java
// Chiudi il flusso EPS di input
psStream.close();
```
Ora hai aggiunto con successo i metadati al tuo file EPS utilizzando Aspose.Page per Java!
## Conclusione
In questo tutorial, abbiamo esplorato il processo di aggiunta di metadati XMP a un file EPS utilizzando la libreria Aspose.Page per Java. Questo potente strumento ti consente di manipolare i documenti senza problemi, migliorando la tua esperienza complessiva di gestione dei documenti.
## Domande frequenti
### D: Aspose.Page per Java è gratuito?
 R: Aspose.Page per Java è un prodotto commerciale. Puoi esplorare le sue funzionalità tramite una prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso trovare la documentazione per Aspose.Page per Java?
 R: La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 R: Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Quali formati di file supporta Aspose.Page per Java?
R: Aspose.Page per Java supporta vari formati, inclusi EPS, PDF e XPS.
### D: Posso acquistare Aspose.Page per Java?
 R: Sì, puoi acquistare Aspose.Page per Java[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
