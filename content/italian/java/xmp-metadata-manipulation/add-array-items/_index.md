---
title: Aggiungi elementi dell'array nei metadati XMP utilizzando Java
linktitle: Aggiungi elementi dell'array nei metadati XMP utilizzando Java
second_title: API Java Aspose.Page
description: Migliora i file EPS con Aspose.Page per Java. Impara ad aggiungere elementi dell'array ai metadati XMP senza sforzo. Segui subito la nostra guida passo passo!
type: docs
weight: 10
url: /it/java/xmp-metadata-manipulation/add-array-items/
---
## introduzione
Benvenuti nella nostra guida passo passo sull'utilizzo di Aspose.Page per Java per aggiungere elementi dell'array nei metadati XMP. Aspose.Page è una potente libreria Java che ti consente di manipolare e lavorare con vari formati di documenti, inclusi i file EPS. In questo tutorial ci concentreremo sull'attività specifica di aggiunta di elementi dell'array nei metadati XMP utilizzando Java.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Page per la libreria Java installata.
- Conoscenza di base della programmazione Java.
- Un file EPS valido con metadati XMP esistenti o commenti sui metadati PS.
## Importa pacchetti
Per iniziare, è necessario importare i pacchetti necessari per lavorare con Aspose.Page. Includi le seguenti righe all'inizio del tuo file Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
In questo passaggio, recuperiamo i metadati XMP esistenti dal file EPS. Se il file EPS non contiene già metadati XMP, Aspose.Page ne genera uno nuovo e lo riempie con i valori dei commenti dei metadati PS.
## Passaggio 2: aggiungere l'elemento dell'array "dc:title".
```java
// Aggiungi un altro elemento dell'array "dc:title".
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Ora aggiungiamo un nuovo elemento dell'array alla proprietà "dc:title" nei metadati XMP. Sostituisci "Nuovo Titolo" con il titolo desiderato.
## Passaggio 3: aggiungere l'elemento dell'array "dc:creator".
```java
// Aggiungi un altro elemento dell'array "dc:creator".
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Allo stesso modo, aggiungiamo un nuovo elemento dell'array alla proprietà "dc:creator" nei metadati XMP. Sostituisci "NewCreator" con le informazioni sul creatore desiderate.
## Passaggio 4: inizializzare il flusso di file EPS di output
```java
// Inizializza il flusso di file EPS di output
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Preparare il flusso di file EPS di output in cui verrà salvato il documento modificato con metadati XMP aggiornati.
## Passaggio 5: salva il documento con i metadati XMP modificati
```java
//Salva il documento con i metadati XMP modificati
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Salva il documento con i metadati XMP aggiornati nel file EPS di output.
## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere elementi dell'array nei metadati XMP utilizzando Aspose.Page per Java. Questa potente libreria semplifica il processo di manipolazione dei file EPS e fornisce funzionalità estese per l'elaborazione dei documenti.
## Domande frequenti

### Posso utilizzare Aspose.Page per Java con altri formati di documenti?
Sì, Aspose.Page supporta vari formati di documenti, inclusi EPS, PDF e XPS.
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Page per Java?
 La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### Come posso acquistare Aspose.Page per Java?
 Puoi acquistare il prodotto[Qui](https://purchase.aspose.com/buy).
### Sono disponibili licenze temporanee per Aspose.Page per Java?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).