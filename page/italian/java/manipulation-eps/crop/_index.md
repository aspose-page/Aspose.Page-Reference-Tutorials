---
date: 2026-09-04
description: Scopri come ridurre le dimensioni del file EPS ritagliando i file EPS
  in Java con Aspose.Page – una guida passo‑passo che mostra come ritagliare EPS,
  ritagliare l'immagine EPS e rifinire il file EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Ritaglia file EPS in Java
og_description: Scopri come ridurre le dimensioni del file EPS ritagliando i file
  EPS in Java con Aspose.Page – una guida rapida con codice e consigli.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Come ritagliare i file EPS in Java per ridurre le dimensioni del file EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Come ritagliare i file EPS in Java per ridurre le dimensioni del file EPS
url: /it/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare file EPS in Java per ridurre le dimensioni del file EPS

## Introduzione
Se hai bisogno di **ritagliare EPS** file programmaticamente in un'applicazione Java e vuoi **ridurre le dimensioni del file EPS**, sei nel posto giusto. In questo tutorial percorreremo l'intero processo di ritaglio di un'immagine EPS utilizzando la potente libreria Aspose.Page per Java. Alla fine della guida comprenderai perché il ritaglio EPS è importante, vedrai il codice esatto di cui hai bisogno e sarai pronto a integrare la soluzione nei tuoi progetti.

## Risposte rapide
- **Quale libreria gestisce il ritaglio EPS in Java?** Aspose.Page for Java.  
- **Quanto tempo richiede implementare un ritaglio di base?** Approximately 5‑10 minutes.  
- **Ho bisogno di una licenza per lo sviluppo?** A free trial works for evaluation; a commercial license is required for production.  
- **Quali versioni di Java sono supportate?** Java 8 and newer.  
- **Posso definire un riquadro di delimitazione personalizzato?** Yes – you provide the coordinates you need.

## Cos'è il ritaglio EPS e perché usarlo?
**Il ritaglio EPS crea un nuovo riquadro di delimitazione che definisce la regione visibile di un file EPS.**  
Ritagliare un file EPS rimuove gli spazi bianchi indesiderati e taglia la grafica all'area di cui hai realmente bisogno, riducendo direttamente **le dimensioni del file EPS** e migliorando la coerenza del layout nei documenti successivi come PDF o report.

## Perché ritagliare i file EPS?
Ritagliare i file EPS ti consente di **ridurre le dimensioni del file fino al 30 %**, eliminare margini eccessivi e standardizzare le grafiche per le pipeline di elaborazione batch. È particolarmente utile quando devi incorporare molti asset EPS in un unico PDF o quando vuoi velocizzare il rendering su dispositivi a bassa potenza.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere:

- Libreria **Aspose.Page for Java** installata – scaricala dalla pagina ufficiale [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 o successivo installato sulla tua macchina.  
- **Una cartella** per memorizzare il tuo EPS di input (`input.eps`) e il file ritagliato risultante (`output_crop.eps`).

## Importa i pacchetti
Per prima cosa, importa le classi Java necessarie. Questo snippet rimane esattamente lo stesso dell'originale tutorial:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Come ritagliare un'immagine EPS in Java
Carica il tuo EPS di origine, definisci un nuovo riquadro di delimitazione e chiama l'API di ritaglio – l'intera operazione viene completata in cinque passaggi concisi.

### Passo 1: impostare la directory del documento e lo stream di input
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Qui indirizziamo il codice alla cartella che contiene il nostro file EPS di origine e apriamo uno stream per leggerlo.

### Passo 2: inizializzare l'oggetto PsDocument
La classe `PsDocument` rappresenta un file EPS in memoria, consentendoti di leggere e modificare le sue proprietà.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
L'oggetto ti dà accesso al riquadro di delimitazione originale e ad altri metadati.

### Passo 3: estrarre il riquadro di delimitazione iniziale
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Estrarre il riquadro di delimitazione originale ti fornisce le coordinate dell'area visibile corrente – utile per decidere quanto tagliare.

### Passo 4: creare lo stream di output
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Apriamo uno stream dove verrà scritto l'EPS ritagliato.

### Passo 5: definire il nuovo riquadro di delimitazione e ritagliare
Il metodo `cropEps` taglia il documento a un nuovo riquadro di delimitazione e scrive il risultato in uno stream di output.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Fornisci le quattro coordinate (x in basso a sinistra, y in basso a sinistra, x in alto a destra, y in alto a destra) che definiscono l'area da conservare. Il metodo esegue il ritaglio e scrive il risultato in `output_crop.eps`.

## Problemi comuni e soluzioni
- **Coordinate errate:** EPS utilizza punti (1/72 pollice). Se il ritaglio sembra sbagliato, ricontrolla la conversione delle unità.  
- **Errori di file non trovato:** Assicurati che `dataDir` termini con il separatore di percorso appropriato (`/` o `\`).  
- **Eccezioni di licenza:** Eseguire il codice senza una licenza valida può aggiungere una filigrana all'output. Applica la tua licenza temporanea o permanente prima dell'uso in produzione.

## Domande frequenti

**Q: Aspose.Page è compatibile con Java 8?**  
A: Sì, Aspose.Page funziona con Java 8 e qualsiasi versione successiva.

**Q: Posso usare Aspose.Page per progetti commerciali?**  
A: Absolutely. A commercial license is required for production deployments. You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Dove posso trovare risorse aggiuntive e supporto della community?**  
A: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39) for discussions, code samples, and troubleshooting tips.

**Q: È disponibile una prova gratuita per i test?**  
A: Yes, you can download a free trial of Aspose.Page from the releases page [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per una valutazione a breve termine?**  
A: A temporary license can be requested from the licensing portal [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora sai **come ritagliare file EPS** in Java usando Aspose.Page per **ridurre le dimensioni del file EPS**. Definendo un riquadro di delimitazione personalizzato e invocando `cropEps`, puoi tagliare i margini indesiderati o isolare parti specifiche di una grafica EPS con poche righe di codice. Integra questo snippet nelle tue più ampie pipeline di elaborazione documenti per automatizzare la manipolazione EPS, **ritagliare le immagini EPS** e **tagliare il contenuto del file EPS** in modo efficiente.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutorial correlati

- [Come ridimensionare i file EPS in Java con Aspose.Page](/page/java/manipulation-eps/resize/)
- [Converti EPS in PNG con Aspose.Page Java (licenza a consumo)](/page/java/license-management/set-metered-license/)
- [Tutorial Aspose Page Java – Aggiungi metadati XMP ai file EPS](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}