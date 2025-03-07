---
title: Aggiungi gradiente verticale in Java PostScript
linktitle: Aggiungi gradiente verticale in Java PostScript
second_title: API Java Aspose.Page
description: Esplora la guida passo passo per aggiungere gradienti verticali in Java PostScript con Aspose.Page per Java. Migliora i tuoi documenti senza sforzo con immagini vivaci.
weight: 14
url: /it/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi gradiente verticale in Java PostScript

## introduzione
Benvenuti in questa guida passo passo sull'aggiunta di un gradiente verticale in Java PostScript utilizzando Aspose.Page per Java. Se vuoi migliorare il tuo documento con sfumature accattivanti, questo tutorial fa per te. Aspose.Page per Java fornisce potenti strumenti per manipolare documenti PostScript senza problemi.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Page per la libreria Java. Puoi scaricarlo[Qui](https://releases.aspose.com/page/java/).
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per iniziare:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Ora suddividiamo il processo di aggiunta di un gradiente verticale in Java PostScript in più passaggi.
## Passaggio 1: configura la directory dei documenti
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
```
## Passaggio 2: crea il flusso di output per il documento PostScript
```java
// Crea flusso di output per il documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Passaggio 3: crea opzioni di salvataggio con formato A4
```java
// Crea opzioni di salvataggio con il formato A4
PsSaveOptions options = new PsSaveOptions();
```
## Passaggio 4: crea un nuovo documento PS
```java
// Crea un nuovo documento PS con la pagina aperta
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Passaggio 5: crea un rettangolo
```java
//Crea un rettangolo
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Passaggio 6: imposta i colori e le frazioni per il gradiente
```java
// Crea matrici di colori e frazioni per il gradiente.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Passaggio 7: crea la trasformazione gradiente
```java
// Crea la trasformazione del gradiente. I componenti di scala nella trasformazione devono essere uguali alla larghezza e all'altezza del rettangolo.
// I componenti di traslazione sono offset del rettangolo.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Ruota il gradiente di 90 gradi attorno a un'origine
transform.rotate(90 * (Math.PI / 180));
```
## Passaggio 8: crea una pittura a gradiente lineare verticale
```java
// Crea una vernice sfumata lineare verticale.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Passaggio 9: imposta Vernice e riempi il rettangolo
```java
// Imposta la vernice
document.setPaint(paint);
// Riempi il rettangolo
document.fill(rectangle);
```
## Passaggio 10: chiudi la pagina corrente e salva il documento
```java
// Chiudi la pagina corrente
document.closePage();
// Salva il documento
document.save();
```
Congratulazioni! Hai aggiunto con successo un gradiente verticale al tuo documento Java PostScript utilizzando Aspose.Page per Java.
## Conclusione
In questo tutorial, abbiamo esplorato il processo di miglioramento dei tuoi documenti con vivaci gradienti verticali utilizzando Aspose.Page per Java. Ora puoi portare la manipolazione dei tuoi documenti a un livello superiore incorporando immagini straordinarie.
## Domande frequenti
### Posso utilizzare Aspose.Page per Java con altre librerie Java?
Sì, Aspose.Page per Java è progettato per funzionare perfettamente con altre librerie Java.
### È disponibile una prova gratuita per Aspose.Page per Java?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione?
 È disponibile la documentazione dettagliata[Qui](https://reference.aspose.com/page/java/).
### Come posso acquistare Aspose.Page per Java?
 È possibile acquistare Aspose.Page per Java[Qui](https://purchase.aspose.com/buy).
### Esiste un forum per le discussioni su Aspose.Page?
 Sì, puoi unirti al forum della community[Qui](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
