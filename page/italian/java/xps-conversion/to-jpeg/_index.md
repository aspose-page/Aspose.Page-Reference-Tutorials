---
title: Converti XPS in JPEG in Java
linktitle: Converti XPS in JPEG in Java
second_title: API Java Aspose.Page
description: Scopri come convertire XPS in JPEG in Java utilizzando Aspose.Page. Una guida completa con istruzioni dettagliate per un'integrazione perfetta.
type: docs
weight: 11
url: /it/java/xps-conversion/to-jpeg/
---
## introduzione
In questo tutorial esploreremo come convertire file XPS (XML Paper Specifica) in immagini JPEG utilizzando Aspose.Page per Java. Aspose.Page è una potente libreria Java che consente agli sviluppatori di lavorare senza problemi con XPS e altri formati di documenti. Questa guida passo passo ti aiuterà a comprendere il processo e a implementarlo nelle tue applicazioni Java.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Ambiente di sviluppo Java: assicurati di avere un ambiente di sviluppo Java configurato sul tuo computer.
-  Aspose.Page per la libreria Java: scarica e installa la libreria Aspose.Page per Java. Puoi trovare la biblioteca[Qui](https://releases.aspose.com/page/java/).
- Documento XPS di esempio: disponi di un documento XPS di esempio che desideri convertire in JPEG.
## Importa pacchetti
Inizia importando i pacchetti necessari nella tua classe Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Passaggio 1: inizializza percorsi e documento XPS
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Inizializza il flusso di input XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Passaggio 2: imposta JpegSaveOptions
```java
// Inizializza l'oggetto opzioni con i parametri necessari.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Passaggio 3: crea il dispositivo di rendering
```java
// Crea dispositivo di rendering per il formato PDF
ImageDevice device = new ImageDevice();
```
## Passaggio 4: salva XPS come JPEG
```java
document.save(device, options);
```
## Passaggio 5: iterazione e salvataggio delle pagine JPEG
```java
//Scorri le partizioni dei documenti (documenti fissi, in termini XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Scorri le pagine delle partizioni
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Inizializza il flusso di output dell'immagine
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Scrivi immagine
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //chiudere il flusso
        imageStream.close();
    }
}
```
Questa serie di passaggi convertirà in modo efficace il tuo documento XPS in immagini JPEG, ciascuna salvata separatamente.
## Conclusione
Congratulazioni! Hai imparato con successo come convertire XPS in JPEG in Java utilizzando Aspose.Page. Questo processo ha un valore inestimabile per gli sviluppatori che lavorano con la conversione di documenti nelle applicazioni Java.
## Domande frequenti

### D: Aspose.Page è adatto a progetti commerciali?
 R: Sì, Aspose.Page è un prodotto commerciale con opzioni di licenza disponibili. Controllo[Qui](https://purchase.aspose.com/buy) per dettagli.
### D: Posso provare Aspose.Page prima dell'acquisto?
 R: Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso trovare la documentazione di Aspose.Page?
 R: La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### D: Come posso ottenere supporto per Aspose.Page?
 R: Visita il[Aspose.Page Forum](https://forum.aspose.com/c/page/39) per il sostegno basato sulla comunità.
### D: Ho bisogno di una licenza temporanea per i test?
 R: Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).