---
date: 2026-02-15
description: Scopri come aggiungere un motivo a tratteggio ai file PostScript Java
  usando Aspose.Page Java. Questa guida passo passo mostra il codice completo e i
  consigli.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Come aggiungere un motivo a tratteggio in Java PostScript con Aspose.Page
url: /it/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

 at top and bottom.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un hatch pattern in Java PostScript

## Introduzione
Se stai lavorando con **Aspose.Page Java** e ti chiedi **come aggiungere un hatch pattern** al tuo output PostScript, i hatch pattern sono una soluzione rapida e flessibile. In questo tutorial vedremo **come aggiungere hatch** ai disegni di un documento PostScript, spiegheremo perché sono utili e ti forniremo un esempio di codice completo, pronto all'uso. Alla fine, sarai in grado di creare forme e testo riempiti con hatch visivamente accattivanti con poche righe di Java.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page per Java (l'SDK “aspose page java”).  
- **Quale effetto visivo aggiungiamo?** Hatch pattern (ad es. linee diagonali, crosshatch).  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza per la produzione.  
- **Quante righe di codice?** Circa 70 righe, suddivise in passaggi chiari.  
- **Posso usare lo stesso approccio per i PDF?** Sì—Aspose.Page supporta più formati di output, incluso PDF.

## Come aggiungere un hatch pattern – Panoramica
Gli hatch pattern sono texture vettoriali che si rendono nitide a qualsiasi risoluzione e funzionano bene su stampanti monocromatiche. Con Aspose.Page Java, puoi applicare questi pattern a forme, percorsi e persino al testo senza dover gestire comandi PostScript a basso livello.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Ambiente di sviluppo Java** – JDK 8 o superiore e un IDE a tua scelta.  
- **Libreria Aspose.Page per Java** – Scarica l'ultimo JAR dal sito ufficiale [qui](https://releases.aspose.com/page/java/).  
- **Accesso in scrittura** a una cartella dove verrà salvato il file PostScript generato.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie nel tuo progetto. Queste importazioni ti danno accesso alle primitive di disegno, alla gestione dei colori e all'API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Passo 1: Impostare i parametri iniziali
Crea lo stream di output, configura la dimensione della pagina (A4) e definisci alcune variabili di layout che verranno riutilizzate durante il disegno di ogni quadrato riempito con hatch.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Passo 2: Salvare lo stato grafico e tradurre
Salvare lo stato grafico consente di tornare al sistema di coordinate originale in seguito, mentre `translate` sposta l'origine in un punto di partenza conveniente.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Passo 3: Creare il quadrato per ogni pattern
Definisci un rettangolo riutilizzabile che rappresenterà ogni cella riempita con hatch.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Passo 4: Configurare la penna per il contorno del quadrato di pattern
Un `BasicStroke` di 2 punti fornisce un contorno nitido attorno a ogni quadrato.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Passo 5: Iterare attraverso gli Hatch Pattern
Scorri tutti i valori dell'enumerazione `HatchStyle`, riempi ogni quadrato con la texture corrispondente e poi disegna il suo contorno. Questo è il cuore della funzionalità di **aggiunta di hatch pattern**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Passo 6: Ripristinare lo stato grafico
Ritorna al sistema di coordinate originale dopo aver terminato il disegno della griglia di quadrati.

```java
document.writeGraphicsRestore();
```

## Passo 7: Riempire il testo con Hatch Pattern
Qui dimostriamo come dipingere il testo usando una texture hatch. L'esempio riempie la parola “ABC” con un pattern a croce diagonale.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Passo 8: Contornare il testo con Hatch Pattern
Ora contorniamo lo stesso testo, ma questa volta usando uno stile hatch al 70 % e un tratto più spesso.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Passo 9: Chiudere e salvare il documento
Finalizza la pagina, scrivi il file su disco e rilascia le risorse.

```java
document.closePage();
document.save();
```

Segui questi passaggi e otterrai un file PostScript che mostra l'intera serie di hatch pattern applicati sia a forme che a testo—tutto alimentato da **aspose page java**.

## Perché usare gli Hatch Pattern con Aspose.Page Java?
- **Distinzione visiva** – I riempimenti hatch funzionano anche quando le stampanti sono limitate a output monocromatico.  
- **Prestazioni** – Le texture sono generate al volo, evitando grandi file immagine.  
- **Supporto cross‑format** – Lo stesso codice può puntare a PDF, EPS o SVG con modifiche minime.

## Problemi comuni e consigli
- **Errori di percorso file** – Assicurati che `dataDir` termini con il separatore di file appropriato (`/` o `\`).  
- **Colori non supportati** – Alcuni interpreti PostScript più vecchi potrebbero non gestire certi spazi colore; usa RGB di base per massima compatibilità.  
- **Avvisi di licenza** – Eseguire il campione senza licenza valida inserirà una filigrana nell'output.

## Conclusione
L'integrazione degli hatch pattern può migliorare notevolmente la leggibilità e l'estetica di disegni tecnici, mappe o qualsiasi grafica generata da Java. Con **Aspose.Page Java**, ottieni un'API concisa che astrae i comandi PostScript di basso livello, permettendoti di concentrarti sul design anziché sulle particolarità del formato file. Ora sai **come aggiungere un hatch pattern** ai tuoi documenti PostScript—sperimenta con diversi valori di `HatchStyle` per ottenere l'aspetto esatto di cui hai bisogno.

## Domande frequenti

**D: Posso usare Aspose.Page Java con altri framework Java?**  
R: Sì, la libreria è indipendente dal framework e funziona con Spring, Jakarta EE, Android (limitato) e Java SE puro.

**D: È disponibile una versione di prova per Aspose.Page Java?**  
R: Assolutamente. Scarica una prova gratuita di 30 giorni [qui](https://releases.aspose.com/).

**D: Come ottengo una licenza temporanea per lo sviluppo?**  
R: Richiedi una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/). Rimuove le filigrane di valutazione.

**D: Dove posso trovare altri tutorial e supporto della community?**  
R: Visita il forum ufficiale [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) per esempi aggiuntivi e Q&A.

**D: Esiste una documentazione completa per tutte le classi e i metodi?**  
R: Sì, il riferimento API completo è disponibile [qui](https://reference.aspose.com/page/java/).

**D: Posso renderizzare lo stesso hatch pattern in PDF invece di PostScript?**  
R: Certamente. Cambia `PsSaveOptions` in `PdfSaveOptions` (o l'equivalente) e il resto del codice rimane invariato.

**D: Cosa fare se il file generato è vuoto?**  
R: Verifica che lo stream di output punti a una directory scrivibile e che `document.save()` sia chiamato dopo tutte le operazioni di disegno.

---

**Ultimo aggiornamento:** 2026-02-15  
**Testato con:** Aspose.Page per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}