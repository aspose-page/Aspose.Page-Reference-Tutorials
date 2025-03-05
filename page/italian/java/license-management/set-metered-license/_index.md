---
title: Integrazione semplice della licenza misurata con Aspose.Page Java
linktitle: Imposta la licenza a consumo in Java
second_title: API Java Aspose.Page
description: Esplora la perfetta integrazione di Aspose.Page con Java. Configura facilmente licenze a consumo e migliora le tue capacità di elaborazione dei documenti.
type: docs
weight: 10
url: /it/java/license-management/set-metered-license/
---
## introduzione
Benvenuti nella nostra guida completa sulla configurazione di una licenza misurata in Java utilizzando Aspose.Page. Se stai cercando di migliorare le tue capacità di elaborazione dei documenti e garantire una perfetta integrazione con Aspose.Page, sei nel posto giusto. In questo tutorial ti guideremo attraverso il processo, suddividendo ogni passaggio in parti facilmente digeribili.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
-  Libreria Aspose.Page installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/page/java/).
- Chiavi pubbliche e private misurate, che puoi ottenere tramite il tuo account Aspose.
## Importa pacchetti
Iniziamo importando i pacchetti necessari per il nostro programma Java. Assicurati di avere la libreria Aspose.Page integrata nel tuo progetto.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Passaggio 1: inizializza il formato del documento e dell'immagine
Il primo passo è impostare il documento e definire il formato immagine desiderato.
```java
// impostare chiavi pubbliche e private misurate
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Accedi alla proprietà setMeteredKey e passa le chiavi pubbliche e private come parametri
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Passaggio 2: inizializzare il flusso di input PostScript
In questo passaggio inizializziamo il flusso di input PostScript per l'elaborazione.
```java
// Inizializza il flusso di input PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Passaggio 3: verificare la licenza del documento
Prima di procedere, è fondamentale verificare se il documento dispone della corretta licenza.
```java
// Controlla se il documento è concesso in licenza
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Passaggio 4: inizializzare le opzioni e il dispositivo immagine
Ora inizializziamo le opzioni e il dispositivo immagine con i parametri predefiniti.
```java
// Inizializza l'oggetto opzioni con i parametri predefiniti.
ImageSaveOptions options = new ImageSaveOptions();
// Inizializza l'oggetto ImageDevice con i parametri predefiniti.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Passaggio 5: salva il file EPS come immagine
Salva il file EPS come immagine utilizzando le opzioni e il dispositivo definiti.
```java
// Salva il file EPS come immagine
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Passaggio 6: ottieni e salva byte di immagine
Recupera i byte di immagine e salvali in un file.
```java
// Ottieni byte di immagini. Un array di byte per una pagina. Nel nostro caso, abbiamo una pagina.
byte[][] imagesBytes = device.getImagesBytes();
// Salva i byte dell'immagine nel file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Conclusione
Congratulazioni! Hai configurato correttamente una licenza a consumo in Java utilizzando Aspose.Page. Questo tutorial fornisce una guida passo passo per garantire un processo di integrazione fluido.
## Domande frequenti
### D: Come posso ottenere chiavi pubbliche e private misurate?
Puoi ottenere queste chiavi tramite il tuo account Aspose.
### D: La libreria Aspose.Page è gratuita?
 Aspose.Page offre sia versioni di prova gratuite che versioni a pagamento. Visita[Qui](https://releases.aspose.com/) per una prova gratuita.
### D: Posso utilizzare Aspose.Page per progetti commerciali?
 Sì, Aspose.Page offre licenze commerciali. Puoi acquistarli[Qui](https://purchase.aspose.com/buy).
### D: Dove posso trovare ulteriore documentazione?
 Fare riferimento alla documentazione[Qui](https://reference.aspose.com/page/java/).
### D: Come posso ottenere licenze temporanee?
 È possibile ottenere licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).