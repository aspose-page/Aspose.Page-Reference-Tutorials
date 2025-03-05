---
title: Converti XPS in PNG in Java
linktitle: Converti XPS in PNG in Java
second_title: API Java Aspose.Page
description: Converti facilmente XPS in PNG in Java utilizzando Aspose.Page. Semplifica le attività relative ai documenti con questa soluzione affidabile e intuitiva per gli sviluppatori.
type: docs
weight: 13
url: /it/java/xps-conversion/to-png/
---
## introduzione
Nel dinamico mondo dello sviluppo software, la necessità di convertire documenti XPS (XML Paper Specifica) in immagini PNG (Portable Network Graphics) si presenta frequentemente. Per eseguire questa attività senza problemi in Java, Aspose.Page fornisce una soluzione potente. In questo tutorial, esamineremo il processo di conversione da XPS a PNG utilizzando Aspose.Page per Java.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Page per Java: scarica e installa la libreria Aspose.Page. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/page/java/).
3. Ambiente di sviluppo integrato (IDE): scegli un IDE compatibile con Java come IntelliJ IDEA o Eclipse.
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per utilizzare le funzionalità Aspose.Page. Aggiungi le seguenti istruzioni di importazione all'inizio del tuo file Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Passaggio 1: imposta la directory dei documenti
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
```
## Passaggio 2: caricare il documento XPS
```java
// Carica il documento XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Passaggio 3: inizializzare le opzioni
```java
// Inizializza l'oggetto opzioni con i parametri necessari.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Passaggio 4: crea il dispositivo di rendering
```java
// Crea dispositivo di rendering per il formato PDF
ImageDevice device = new ImageDevice();
```
## Passaggio 5: salvare e ripetere
```java
// Salva il documento XPS in PNG utilizzando le opzioni e il dispositivo
document.save(device, options);
//Scorri le partizioni dei documenti (documenti fissi, in termini XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Scorri le pagine delle partizioni
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inizializza il flusso di output dell'immagine
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Scrivi immagine
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Chiudi il flusso
        imageStream.close();
    }
}
```
Seguendo questi passaggi, puoi convertire facilmente documenti XPS in immagini PNG utilizzando Aspose.Page per Java.
## Conclusione
In conclusione, Aspose.Page per Java semplifica il processo di conversione da XPS a PNG, fornendo agli sviluppatori uno strumento affidabile ed efficiente. Incorpora questa libreria nei tuoi progetti Java per semplificare le attività di manipolazione dei documenti.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java in progetti commerciali?
 Sì, Aspose.Page è un prodotto commerciale. È possibile trovare informazioni sulla licenza[Qui](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita?
 Sì, puoi esplorare una prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Page per Java?
 La documentazione completa è disponibile[Qui](https://reference.aspose.com/page/java/).
### Come posso ottenere una licenza temporanea a scopo di test?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Esistono forum della community per le discussioni su Aspose.Page?
 Sì, visita i forum della community[Qui](https://forum.aspose.com/c/page/39).