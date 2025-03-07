---
title: Converti XSP in TIFF in Java
linktitle: Converti XSP in TIFF in Java
second_title: API Java Aspose.Page
description: Converti XPS in TIFF senza sforzo con Aspose.Page per Java. Segui la nostra guida passo passo per un'integrazione perfetta. Scarica ora!
weight: 14
url: /it/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti XSP in TIFF in Java

Nell'era digitale di oggi, la conversione dei documenti gioca un ruolo cruciale in varie applicazioni. Se sei uno sviluppatore Java alla ricerca di una soluzione solida per convertire documenti XPS (XML Paper Specifica) in TIFF (Tagged Image File Format), Aspose.Page per Java è la libreria di riferimento. In questa guida passo passo ti guideremo attraverso il processo, assicurandoti un'esperienza fluida con spiegazioni dettagliate e snippet di codice.
## Prerequisiti
Prima di immergerti nel processo di conversione, assicurati di disporre dei seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Page per la libreria Java. Puoi scaricarlo[Qui](https://releases.aspose.com/page/java/).
-  Una licenza valida per Aspose.Page per Java. È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) o acquistare una licenza completa[Qui](https://purchase.aspose.com/buy).
## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java. Assicurati di aver aggiunto la libreria Aspose.Page per Java al tuo progetto.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Passaggio 1: impostare la directory dei documenti
Definire il percorso della directory dei documenti in cui si trova il file XPS di input.
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: caricare il documento XPS
Caricare il documento XPS utilizzando la libreria Aspose.Page.
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Passaggio 3: inizializza TiffSaveOptions
Inizializza l'oggetto TiffSaveOptions con i parametri necessari, come modalità di smussamento, risoluzione e numeri di pagina specifici.
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Passaggio 4: crea il dispositivo di rendering
Crea un dispositivo di rendering per il formato TIFF utilizzando la classe ImageDevice.
```java
ImageDevice device = new ImageDevice();
```
## Passaggio 5: salva il documento in TIFF
Salva il documento XPS in formato TIFF utilizzando le opzioni e il dispositivo di rendering specificati.
```java
document.save(device, options);
```
## Passaggio 6: iterazione e salvataggio di immagini TIFF
Scorri le partizioni e le pagine del documento, inizializzando i flussi di output delle immagini e salvando le immagini TIFF.
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 Congratulazioni! Hai convertito con successo XPS in TIFF in Java utilizzando Aspose.Page. Sentiti libero di esplorare ulteriori caratteristiche e funzionalità della libreria nel[documentazione](https://reference.aspose.com/page/java/).
## Conclusione
In questo tutorial, abbiamo trattato i passaggi essenziali per convertire XPS in TIFF in Java utilizzando Aspose.Page. La conversione dei documenti è ora a portata di mano, consentendoti di migliorare le tue applicazioni con il supporto versatile dei formati di file.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java senza licenza?
 Sebbene sia possibile ottenere una licenza temporanea per la valutazione, è necessaria una licenza valida per l'utilizzo in produzione. Ottieni la tua licenza[Qui](https://purchase.aspose.com/buy).
### Esistono limitazioni sulla dimensione dei file XPS per la conversione?
Aspose.Page per Java gestisce documenti di varie dimensioni, ma è consigliabile testare file più grandi nel tuo ambiente specifico.
### Come posso ottenere supporto o porre domande su Aspose.Page per Java?
 Visitare il[Forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto e le discussioni della comunità.
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi esplorare la libreria con una prova gratuita. Scaricalo[Qui](https://releases.aspose.com/).
### Qual è la risoluzione consigliata per le immagini TIFF in questa conversione?
L'esempio fornito utilizza una risoluzione di 300 DPI, ma puoi regolarla in base ai tuoi requisiti specifici.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
