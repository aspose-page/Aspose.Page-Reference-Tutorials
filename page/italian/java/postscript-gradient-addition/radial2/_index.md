---
title: Gradiente radiale Java PostScript con Aspose.Page
linktitle: Gradiente radiale Java PostScript con Aspose.Page
second_title: API Java Aspose.Page
description: Esplora la guida passo passo per aggiungere il gradiente radiale in Java PostScript utilizzando Aspose.Page per una grafica straordinaria nelle tue applicazioni Java.
weight: 13
url: /it/java/postscript-gradient-addition/radial2/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gradiente radiale Java PostScript con Aspose.Page

## introduzione
Benvenuti nella nostra guida passo passo sull'aggiunta di Radial Gradient 2 in Java PostScript utilizzando Aspose.Page per Java. Questo tutorial ti guiderà attraverso il processo di creazione di un documento PostScript con un bellissimo gradiente radiale, migliorando le tue applicazioni Java con una grafica visivamente accattivante.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica della programmazione Java.
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Page per la libreria Java, che puoi scaricare da[Aspose.Page Documentazione Java](https://reference.aspose.com/page/java/).
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Passaggio 1: impostare la directory dei documenti
Definisci il percorso della directory dei tuoi documenti:
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: crea il flusso di output
Crea un flusso di output per il documento PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Passaggio 3: crea opzioni di salvataggio
Crea opzioni di salvataggio con il formato A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Passaggio 4: crea il documento PS
Crea un nuovo documento PS con la pagina aperta:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Passaggio 5: crea una cerchia
Definisci un cerchio utilizzando la classe Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Passaggio 6: definire i colori sfumati
Crea matrici di colori e frazioni per il gradiente radiale:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Passaggio 7: crea AffineTransform
Crea un AffineTransform per il gradiente radiale:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Passaggio 8: crea una pittura a gradiente radiale
Crea un RadialGradientPaint con i parametri specificati:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Passaggio 9: imposta il cerchio di pittura e riempimento
Imposta la vernice e riempi il cerchio con il gradiente radiale:
```java
document.setPaint(paint);
document.fill(circle);
```
## Passaggio 10: chiudi la pagina e salva il documento
Chiudi la pagina corrente e salva il documento:
```java
document.closePage();
document.save();
```
Congratulazioni! Hai aggiunto con successo Radial Gradient 2 in Java PostScript utilizzando Aspose.Page per Java.
## Conclusione
In questo tutorial, abbiamo esplorato come migliorare le tue applicazioni Java con gradienti radiali nei documenti PostScript. Aspose.Page per Java fornisce un potente set di strumenti per creare grafica straordinaria, permettendoti di portare i tuoi progetti Java al livello successivo.
## Domande frequenti
### D: Dove posso trovare la documentazione per Aspose.Page per Java?
 R: La documentazione è disponibile[Qui](https://reference.aspose.com/page/java/).
### D: Come posso scaricare Aspose.Page per Java?
 R: Puoi scaricarlo da[pagina delle uscite](https://releases.aspose.com/page/java/).
### D: È disponibile una prova gratuita?
 R: Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### D: Posso ottenere una licenza temporanea per Aspose.Page per Java?
 R: Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso cercare il sostegno della comunità e partecipare alle discussioni?
 R: Visita il[Forum Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
