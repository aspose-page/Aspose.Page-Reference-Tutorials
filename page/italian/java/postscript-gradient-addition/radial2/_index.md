---
date: 2025-12-08
description: Scopri come creare un esempio di gradiente radiale in Java PostScript
  usando Aspose.Page. Guida passo‑passo con codice completo e risoluzione dei problemi.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Esempio di gradiente radiale: Java PostScript con Aspose.Page'
url: /it/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di Gradiente Radiale: Java PostScript con Aspose.Page

## Introduzione
In questo tutorial costruirai un **esempio di gradiente radiale** per un documento PostScript usando Aspose.Page per Java. Ti guideremo passo passo—dalla configurazione del progetto al rendering di un cerchio riempito con un gradiente radiale uniforme—così potrai aggiungere grafiche accattivanti alle tue applicazioni Java all'istante.

## Risposte Veloci
- **Cosa crea questo tutorial?** Un file PostScript (`.ps`) contenente un cerchio riempito con un gradiente radiale.  
- **Quale libreria è necessaria?** Aspose.Page per Java (ultima versione).  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio funzionante.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione; una versione di prova gratuita è sufficiente per lo sviluppo.  
- **Posso riutilizzare il codice per PDF o SVG?** Sì—Aspose.Page supporta più formati di output con modifiche minime.

## Cos'è un Gradiente Radiale?
Un gradiente radiale trasforma i colori dal punto centrale verso l'esterno, creando una fusione liscia e circolare. È ideale per evidenziazioni, sfondi di pulsanti o qualsiasi elemento visivo che richieda un effetto “bagliore” naturale.

## Perché usare Aspose.Page per i Gradienti Radiali?
- **Rendering indipendente dal dispositivo** – funziona allo stesso modo su PostScript, PDF, SVG e altri.  
- **Integrazione completa Java** – nessun codice nativo, solo API Java pure.  
- **Output di alta qualità** – supporta anti‑aliasing e controllo dello spazio colore.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Familiarità di base con la programmazione Java.  
- JDK 8 o versioni successive installato sulla tua macchina.  
- Libreria Aspose.Page per Java (scaricabile dalla [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/)).

## Importa Pacchetti
Per prima cosa, importa le classi necessarie. Queste includono i tipi grafici standard AWT e l'API Aspose.Page.

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

## Passo 1: Configura la Directory del Documento
Definisci la cartella in cui verrà salvato il file PostScript generato. Sostituisci il segnaposto con un percorso reale sul tuo sistema.

```java
String dataDir = "Your Document Directory";
```

## Passo 2: Crea lo Stream di Output
Apri un `FileOutputStream` che punti al file `.ps` di destinazione. Questo stream fornisce i dati binari generati da Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Passo 3: Crea le Opzioni di Salvataggio
Istanzia `PsSaveOptions`. Puoi personalizzare la dimensione della pagina, la compressione, ecc., ma le impostazioni predefinite vanno bene per questo esempio.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Passo 4: Crea il Documento PS
Crea l'oggetto `PsDocument`, passando lo stream di output e le opzioni di salvataggio. Il flag `false` indica ad Aspose.Page di non aprire automaticamente una pagina (la apriremo manualmente).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Passo 5: Crea un Cerchio
Disegneremo un cerchio usando `Ellipse2D.Float`. I parametri sono `(x, y, width, height)`. Impostare width = height crea un cerchio perfetto.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Passo 6: Definisci i Colori del Gradiente
Prepara due array: uno per i colori che appariranno nel gradiente e un altro per le corrispondenti posizioni frazionarie (0 = centro, 1 = bordo).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Passo 7: Crea l'AffineTransform
L'`AffineTransform` scala e trasla il gradiente per adattarlo al nostro cerchio. La matrice `(scaleX, 0, 0, scaleY, translateX, translateY)` svolge il compito.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Passo 8: Crea il RadialGradientPaint
Ora costruiamo l'oggetto `RadialGradientPaint`. Accetta il punto centrale, il raggio, il punto di messa a fuoco, le frazioni di colore, l'array di colori, il metodo di ciclo, lo spazio colore e la trasformazione appena definita.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Passo 9: Imposta il Paint e Riempie il Cerchio
Applica il paint del gradiente al documento e riempi il cerchio precedentemente definito. Questo è il cuore del nostro **esempio di gradiente radiale**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Passo 10: Chiudi la Pagina e Salva il Documento
Finalizza la pagina, scrivi il contenuto su disco e chiudi lo stream. Il tuo file PostScript è ora pronto per essere visualizzato con qualsiasi visualizzatore PS.

```java
document.closePage();
document.save();
```

Congratulazioni! Hai creato con successo un esempio di gradiente radiale in Java PostScript usando Aspose.Page.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **FileNotFoundException** durante l'apertura dello stream di output | Verifica che `dataDir` punti a una cartella esistente e che tu abbia i permessi di scrittura. |
| Il gradiente appare piatto o mancante | Assicurati che l'array `fractions` corrisponda alla lunghezza dell'array `colors` e che l'`AffineTransform` scala correttamente. |
| I colori appaiono invertiti | Scambia l'ordine dei colori nell'array `colors` o regola le coordinate del punto `focus`. |

## Domande Frequenti

**Q: Dove posso trovare la documentazione per Aspose.Page per Java?**  
A: Il riferimento completo dell'API è disponibile [qui](https://reference.aspose.com/page/java/).

**Q: Come posso scaricare Aspose.Page per Java?**  
A: Scarica l'ultimo JAR dalla [pagina dei rilasci](https://releases.aspose.com/page/java/).

**Q: È disponibile una versione di prova gratuita?**  
A: Sì—scarica una versione di prova [qui](https://releases.aspose.com/).

**Q: Posso ottenere una licenza temporanea per i test?**  
A: Assolutamente, richiedila dalla [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso ottenere supporto dalla community?**  
A: Partecipa alla discussione sul [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusione
In questa guida abbiamo costruito un **esempio completo di gradiente radiale** per un documento PostScript usando Aspose.Page per Java. Seguendo i passaggi ora disponi di un modello riutilizzabile per creare gradienti sofisticati, che puoi adattare a PDF, SVG o altri formati supportati. Sperimenta con colori, raggi e forme diversi per arricchire i tuoi progetti grafici Java.

---

**Ultimo Aggiornamento:** 2025-12-08  
**Testato Con:** Aspose.Page per Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}