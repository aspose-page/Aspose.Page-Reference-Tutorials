---
date: 2026-02-13
description: Scopri come aggiungere un gradiente in Java PostScript usando Linear
  Gradient Paint Java con Aspose.Page per Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Come aggiungere un gradiente in Java PostScript con Linear Gradient Paint
url: /it/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente in Java PostScript con Linear Gradient Paint

## Introduzione
In questo tutorial completo scoprirai **come aggiungere un gradiente** a un documento PostScript usando Java. Ti guideremo nella creazione di un elegante gradiente orizzontale sfruttando **Linear Gradient Paint Java**, una classe che ti offre un controllo pixel‑perfect sulle transizioni di colore. Con Aspose.Page per Java puoi renderizzare gradienti sia su forme **che** su testo, conferendo ai tuoi documenti un aspetto rifinito e accattivante che si distingue.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page per Java (supporta Linear Gradient Paint Java).  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un gradiente di base.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione.  
- **Quale versione di JDK funziona?** Java 8 o versioni successive.  
- **Posso usare il gradiente sia su forme che su testo?** Sì – puoi riempire forme e tracciare o riempire il testo con lo stesso gradiente.

## Cos'è un gradiente orizzontale e perché usarlo?
Un gradiente orizzontale sfuma i colori da sinistra a destra su una forma o su del testo. È ideale per creare elementi UI moderni, intestazioni evidenziate o effetti di sfondo sottili nei report. Utilizzando **Linear Gradient Paint Java** puoi definire esattamente i colori di partenza e di fine, l'opacità e la scala, così il risultato appare nitido su qualsiasi dispositivo.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Page per Java. Puoi scaricarla dalla [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importazione dei pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java. Queste importazioni ti danno accesso alle primitive grafiche, alla gestione dei gradienti e all'API di Aspose.Page.

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

## Passo 1: Creare un rettangolo
Prima, imposta lo stream di output, il documento e un rettangolo che ospiterà il gradiente.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Passo 2: Creare un Linear Gradient Paint orizzontale
Qui costruiamo l'oggetto **Linear Gradient Paint Java** che definisce una transizione di colore orizzontale. L'`AffineTransform` scala il gradiente per adattarlo alla larghezza e all'altezza del rettangolo.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Passo 3: Riempire il rettangolo
Ora riempi il rettangolo con il gradiente appena definito.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Passo 4: Riempire un testo con il gradiente
Puoi anche applicare lo stesso gradiente al testo, creando un effetto visivo sorprendente.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Passo 5: Tracciare un testo con il gradiente
Infine, delinea il testo usando il gradiente come colore di contorno.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problemi comuni e soluzioni
| Problema | Perché si verifica | Soluzione |
|----------|--------------------|-----------|
| Il gradiente appare allungato | Scala `AffineTransform` errata | Assicurati che larghezza e altezza della trasformazione corrispondano alle dimensioni del rettangolo (200 × 100 nell'esempio). |
| I colori sembrano sbiaditi | Valori alpha impostati troppo bassi | Aumenta il componente alpha (il quarto valore in `new Color(r,g,b,alpha)`). |
| Il testo non è visibile | Paint non impostato prima del disegno del testo | Chiama `document.setPaint(paint)` **prima** di qualsiasi chiamata a `fillAndStrokeText` o `outlineText`. |

## Domande frequenti
**D:** Posso usare Aspose.Page per Java in progetti commerciali?  
**R:** Sì, Aspose.Page per Java può essere usato in progetti commerciali. Per i dettagli sulla licenza, visita [Aspose.Purchase](https://purchase.aspose.com/buy).

**D:** È disponibile una versione di prova gratuita?  
**R:** Sì, puoi accedere a una prova gratuita di Aspose.Page per Java [qui](https://releases.aspose.com/).

**D:** Dove posso trovare documentazione aggiuntiva e supporto?  
**R:** Visita la [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/) per risorse complete. Per il supporto della community, controlla il [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**D:** Come posso ottenere una licenza temporanea?  
**R:** Puoi ottenere una licenza temporanea da [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**D:** Quali sono i requisiti di sistema per Aspose.Page per Java?  
**R:** Consulta la [documentazione](https://reference.aspose.com/page/java/) per i requisiti di sistema dettagliati.

---

**Ultimo aggiornamento:** 2026-02-13  
**Testato con:** Aspose.Page per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}