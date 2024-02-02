---
title: Modifica i valori in XMP utilizzando Java
linktitle: Modifica i valori in XMP utilizzando Java
second_title: API Java Aspose.Page
description: Migliora i documenti EPS con Aspose.Page per Java. Modifica facilmente i metadati XMP per contenuti personalizzati e professionali. #SviluppoJava
type: docs
weight: 17
url: /it/java/xmp-metadata-manipulation/change-values/
---
## introduzione
Nel campo dell'elaborazione e manipolazione dei documenti, Aspose.Page per Java si distingue come un potente strumento. Questo tutorial approfondisce il processo di modifica dei valori XMP (Extensible Metadata Platform) nei documenti EPS (Encapsulated PostScript) utilizzando Java con la libreria Aspose.Page. Seguendo la guida passo passo fornita, imparerai come modificare facilmente i metadati, assicurandoti che i tuoi documenti siano adattati alle tue esigenze specifiche.
## Prerequisiti
Prima di intraprendere questo tutorial, assicurati di disporre dei seguenti prerequisiti:
1. Ambiente di sviluppo Java: assicurati di avere un ambiente di sviluppo Java funzionante sul tuo computer.
2.  Aspose.Page per la libreria Java: scarica e installa la libreria Aspose.Page per Java. Puoi trovare il pacchetto necessario[Qui](https://releases.aspose.com/page/java/).
## Importa pacchetti
Inizia importando i pacchetti richiesti nel tuo progetto Java. Questi pacchetti sono vitali per interagire e manipolare i documenti EPS.
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
Recupera i metadati XMP dal documento EPS. Se il file EPS non contiene metadati XMP, ne verrà creato uno nuovo con i valori dei commenti sui metadati PS come %%Creator, %%CreateDate e %%Title.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Inizializza il flusso di file EPS di input
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Ottieni metadati XMP. Se il file EPS non contiene metadati XMP, ne viene creato uno nuovo con i valori dei commenti dei metadati PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Passaggio 2: modifica il valore "ModifyDate".
Modifica il valore "ModifyDate" nei metadati XMP per riflettere la data desiderata.
```java
// Modificare il valore "ModifyDate".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Passaggio 3: modifica il valore "Creatore".
Aggiorna il valore "Creatore" nei metadati XMP per specificare il creatore del documento.
```java
// Cambia il valore "creatore".
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Passaggio 4: modifica il valore "Titolo".
Modifica il valore "Titolo" nei metadati XMP per impostare un titolo appropriato per il documento.
```java
//Cambia il valore del "titolo".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Passaggio 5: salva il documento con i metadati XMP modificati
Salva il documento con i metadati XMP aggiornati in un nuovo file EPS.
```java
// Inizializza il flusso di file EPS di output
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Salva il documento con i metadati XMP modificati
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusione
Congratulazioni! Hai completato con successo il processo di modifica dei valori XMP nei documenti EPS utilizzando Aspose.Page per Java. Questo tutorial ti ha fornito le conoscenze necessarie per modificare i metadati, garantendo che i tuoi documenti si allineino perfettamente ai tuoi requisiti specifici.
## Domande frequenti
### D: Come posso gestire le considerazioni sul fuso orario durante la modifica dei valori XMP?
 Utilizzare`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` per garantire la coerenza nelle impostazioni del fuso orario.
### D: Posso modificare più valori XMP in un'unica operazione?
 Sì, utilizzando il`put` metodo per ciascun valore desiderato, è possibile modificare più valori XMP contemporaneamente.
### D: Dove posso trovare documentazione aggiuntiva per Aspose.Page per Java?
 Esplora la documentazione completa[Qui](https://reference.aspose.com/page/java/).
### D: È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### D: Come posso ottenere una licenza temporanea per Aspose.Page per Java?
 Ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).