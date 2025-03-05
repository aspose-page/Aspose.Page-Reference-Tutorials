---
title: Aggiungi gradiente orizzontale in Java PostScript
linktitle: Aggiungi gradiente orizzontale in Java PostScript
second_title: API Java Aspose.Page
description: Scopri come aggiungere un gradiente orizzontale in Java PostScript con Aspose.Page per Java. Crea documenti visivamente sbalorditivi senza sforzo.
type: docs
weight: 11
url: /it/java/postscript-gradient-addition/horizontal/
---
## introduzione
Benvenuti in questo tutorial completo sull'aggiunta di un gradiente orizzontale in Java PostScript utilizzando Aspose.Page per Java. Aspose.Page è una potente libreria Java che consente agli sviluppatori di lavorare con PostScript e altri formati di documenti. In questo tutorial ti guideremo attraverso il processo di creazione di un documento PostScript con gradiente orizzontale utilizzando esempi passo passo.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
- Aspose.Page per la libreria Java. Puoi scaricarlo da[Aspose.Page Documentazione Java](https://reference.aspose.com/page/java/).
## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java. Questi pacchetti sono fondamentali per lavorare con Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Passaggio 1: crea un rettangolo
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea flusso di output per il documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Crea opzioni di salvataggio con il formato A4
PsSaveOptions options = new PsSaveOptions();
// Crea un nuovo documento PS con la pagina aperta
PsDocument document = new PsDocument(outPsStream, options, false);
//Crea un rettangolo
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Passaggio 2: crea una pittura a gradiente lineare orizzontale
```java
// Crea una vernice sfumata lineare orizzontale. I componenti di scala nella trasformazione devono essere uguali alla larghezza e all'altezza del rettangolo.
// I componenti di traslazione sono offset del rettangolo.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Imposta la vernice
document.setPaint(paint);
```
## Passaggio 3: riempire il rettangolo
```java
// Riempi il rettangolo
document.fill(rectangle);
```
## Passaggio 4: riempi un testo con il gradiente
```java
// Riempi un testo con il gradiente
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Passaggio 5: traccia un testo con il gradiente
```java
// Traccia un testo con il gradiente
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusione
Congratulazioni! Hai aggiunto con successo un gradiente orizzontale in Java PostScript utilizzando Aspose.Page per Java. Questo tutorial ti ha fornito una guida dettagliata passo passo per aiutarti a creare documenti PostScript visivamente accattivanti.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java in progetti commerciali?
Sì, Aspose.Page per Java può essere utilizzato in progetti commerciali. Per i dettagli sulla licenza, visitare[Aspose.Acquisto](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita?
 Sì, puoi accedere a una prova gratuita di Aspose.Page per Java[Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione e supporto?
 Visitare il[Aspose.Page Documentazione Java](https://reference.aspose.com/page/java/) per risorse complete. Per il supporto della comunità, controlla il[Forum Aspose.Page](https://forum.aspose.com/c/page/39).
### Come posso ottenere una licenza temporanea?
 È possibile ottenere una licenza temporanea da[Aspose.Acquisto](https://purchase.aspose.com/temporary-license/).
### Quali sono i requisiti di sistema per Aspose.Page per Java?
 Fare riferimento al[documentazione](https://reference.aspose.com/page/java/) per i requisiti di sistema dettagliati.