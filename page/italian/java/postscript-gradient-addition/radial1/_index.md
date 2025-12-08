---
date: 2025-12-08
description: Scopri come aggiungere un gradiente radiale in Java PostScript con Aspose.Page.
  Questa guida passo passo ti mostra come creare effetti di gradiente sorprendenti
  nei tuoi documenti.
language: it
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Come aggiungere un gradiente radiale in Java PostScript con Aspose.Page
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un gradiente radiale in Java PostScript con Aspose.Page

## Introduzione
Se hai mai avuto bisogno di dare al tuo output PostScript una transizione di colore fluida e accattivante, imparare **come aggiungere un gradiente radiale** è il punto di partenza perfetto. In questo tutorial percorreremo passo dopo passo tutto il necessario per generare un file PostScript che contenga un bellissimo gradiente radiale, utilizzando la libreria **Aspose.Page for Java**. Alla fine comprenderai l'API, vedrai un esempio completo eseguibile e saprai come modificare colori, posizioni e raggi per adattarli a qualsiasi design.

## Risposte rapide
- **Quale libreria crea gradienti radiali in PostScript?** Aspose.Page for Java.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base.  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.  
- **Posso cambiare la forma del gradiente?** Sì – regola il raggio e il punto centrale nel costruttore `RadialGradientPaint`.

## Che cos'è un gradiente radiale?
Un gradiente radiale dipinge i colori che si irradiano da un punto centrale, sfumando gradualmente verso i bordi. A differenza dei gradienti lineari, la transizione di colore segue un pattern circolare (o ellittico), ideale per evidenziare, fare spotlights o riempimenti di sfondo morbidi.

## Perché usare Aspose.Page per i gradienti radiali?
- **Controllo totale sull'output PostScript** – non è necessario scrivere manualmente comandi PS a basso livello.  
- **Cross‑platform** – funziona su qualsiasi OS che esegue Java.  
- **Gestione avanzata dei colori** – supporta più fermate di colore, diversi spazi colore e metodi di ciclo.  
- **Pronto per l'integrazione** – combinabile con altre funzionalità di Aspose.Page come testo, immagini e forme vettoriali.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere tutto il necessario:

- **Java Development Kit (JDK) 8+** – verifica con `java -version`.  
- **Aspose.Page for Java** – scarica l'ultima JAR dalla pagina ufficiale di [download di Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE a tua scelta** – Eclipse, IntelliJ IDEA o VS Code con estensioni Java.  
- **Una cartella scrivibile** – dove verrà salvato il file `.ps` generato.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Il pacchetto `java.awt` fornisce gli oggetti per il paint del gradiente, mentre `com.aspose.eps` contiene le classi per la gestione dei documenti PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

 Guida passo‑passo

### Passo 1: Creare un rettangolo e aprire un documento PS
Iniziamo creando uno stream di output, configurando la dimensione della pagina (A4 di default) e definendo un rettangolo che ospiterà il gradiente.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Suggerimento:** Regola le coordinate del rettangolo (`200, 100, 200, 200`) per posizionare il gradiente ovunque sulla pagina.

### Passo 2: Definire colori e frazioni
Un gradiente radiale è costruito da *fermate di colore* (i colori) e *frazioni* (le posizioni relative di tali fermate). Qui creiamo un array di sei colori e le loro frazioni corrispondenti.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Perché è importante:** Modificando le `fractions` controlli la rapidità della transizione dei colori, consentendo effetti sottili o drammatici.

### Passo 3: Creare il Radial Gradient Paint
Ora costruiamo l'oggetto `RadialGradientPaint`. Il costruttore accetta il punto centrale del gradiente, il raggio, il punto di messa a fuoco, le frazioni, i colori, il metodo di ciclo, lo spazio colore e un eventuale trasform.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Nota:** `transform` può essere `null` se non ti servono scalature o rotazioni aggiuntive. Sentiti libero di sperimentare con `AffineTransform` per gradienti inclinati.

### Passo 4: Impostare il paint e riempire il rettangolo
Con il paint pronto, diciamo al `PsDocument` di usarlo e poi riempiamo il rettangolo definito in precedenza.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

A questo punto la pagina PostScript contiene un rettangolo riempito uniformemente con il gradiente radiale configurato.

### Passo 5: Chiudere e salvare il documento
Infine, chiudi la pagina corrente e scrivi il file su disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Apri `RadialGradient1_outPS.ps` in qualsiasi visualizzatore PostScript (ad es., Ghostscript) e vedrai il gradiente renderizzato esattamente come definito.

## Problemi comuni e soluzioni
| Sintomo | Probabile causa | Soluzione |
|---------|-----------------|-----------|
| Il gradiente appare come un colore solido | L'array `fractions` non inizia con `0.0f` o non termina con `1.0f` | Assicurati che la prima frazione sia `0.0f` e l'ultima `1.0f`. |
| I colori sembrano sbiaditi | Uso di `ColorSpaceType` errato | Passa a `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` per un output più vivace. |
| Nessun file di output generato | Il percorso di `FileOutputStream` è invalido o non scrivibile | Verifica che `dataDir` esista e che l'applicazione abbia i permessi di scrittura. |

## Domande frequenti

**D: Posso usare Aspose.Page for Java in progetti commerciali?**  
R: Sì. È necessaria una licenza commerciale per l'uso in produzione. Puoi acquistarla dalla [pagina di licenza Aspose](https://purchase.aspose.com/buy).

**D: Dove posso trovare il riferimento API ufficiale?**  
R: La documentazione completa è disponibile [qui](https://reference.aspose.com/page/java/).

**D: È disponibile una versione di prova gratuita per i test?**  
R: Assolutamente. Scarica una versione di prova dalla [pagina di rilascio di Aspose.Page](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per la valutazione?**  
R: Una licenza temporanea può essere richiesta [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare supporto dalla community?**  
R: Unisciti al forum della community Aspose.Page su [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusione
Ora sai **come aggiungere un gradiente radiale** a un documento Java PostScript usando Aspose.Page. Regolando la dimensione del rettangolo, le fermate di colore e il raggio del gradiente, puoi creare innumerevoli effetti visivi—da riempimenti di sfondo delicati a grafiche di spotlight audaci. Sperimenta con diversi valori di `AffineTransform` per ruotare o inclinare il gradiente e combina questa tecnica con testo e immagini per output PDF o EPS più ricchi.

---

**Ultimo aggiornamento:** 2025-12-08  
**Testato con:** Aspose.Page for Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}