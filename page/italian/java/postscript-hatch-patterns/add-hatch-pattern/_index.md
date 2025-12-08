---
date: 2025-12-08
description: Scopri come aggiungere motivi a trama ai documenti Java PostScript utilizzando
  Aspose.Page Java. Questa guida passo‑passo ti mostra come inserire grafiche a trama
  in modo efficiente.
language: it
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Aggiungi motivo a tratteggio in PostScript Java'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un motivo a trama in Java PostScript

## Introduzione
Se stai lavorando con **Aspose.Page Java** e hai bisogno di arricchire l'output PostScript con grafiche testurizzate, i motivi a trama sono una soluzione rapida e flessibile. In questo tutorial ti mostreremo **come aggiungere motivi a trama** a un documento PostScript, spiegheremo perché sono utili e ti forniremo un esempio di codice completo, pronto‑da‑eseguire. Alla fine, sarai in grado di creare forme e testo riempiti con motivi a trama visivamente accattivanti con poche righe di Java.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java (l'SDK “aspose page java”).  
- **Quale effetto visivo stiamo aggiungendo?** Motivi a trama (ad es. linee diagonali, reticolato).  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza per la produzione.  
- **Quante righe di codice?** Circa 70 righe, suddivise in passaggi chiari.  
- **Posso usare lo stesso approccio per i PDF?** Sì—Aspose.Page supporta più formati di output, incluso PDF.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Ambiente di sviluppo Java** – JDK 8 o superiore e un IDE a tua scelta.  
- **Libreria Aspose.Page for Java** – Scarica l'ultimo JAR dal sito ufficiale [qui](https://releases.aspose.com/page/java/).  
- **Accesso in scrittura** a una cartella dove verrà salvato il file PostScript generato.

## Importazione dei pacchetti
Per prima cosa, porta le classi necessarie nel tuo progetto. Queste importazioni ti danno accesso alle primitive di disegno, alla gestione dei colori e all'API Aspose.Page.

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
Crea lo stream di output, configura la dimensione della pagina (A4) e definisci alcune variabili di layout che saranno riutilizzate durante il disegno di ogni quadrato riempito a trama.

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

## Passo 2: Salvare lo stato grafico e traslare
Salvare lo stato grafico ci consente di tornare al sistema di coordinate originale in seguito, mentre `translate` sposta l'origine a un punto di partenza conveniente.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Passo 3: Creare il quadrato per ogni motivo
Definisci un rettangolo riutilizzabile che rappresenterà ogni cella riempita a trama.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Passo 4: Configurare la penna per il contorno del quadrato motivo
Un `BasicStroke` di 2 punti fornisce un contorno nitido attorno a ogni quadrato.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Passo 5: Iterare attraverso i motivi a trama
Scorri tutti i valori dell'enumerazione `HatchStyle`, riempi ogni quadrato con la texture corrispondente e poi disegna il suo contorno. Questo è il cuore della funzionalità di **aggiunta di motivi a trama**.

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

## Passo 7: Riempire il testo con un motivo a trama
Qui dimostriamo come dipingere il testo usando una texture a trama. L'esempio riempie la parola “ABC” con un motivo a croce diagonale.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Passo 8: Contornare il testo con un motivo a trama
Ora contorniamo lo stesso testo, ma questa volta usando uno stile a trama del 70 % e un tratto più spesso.

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

Segui questi passaggi e otterrai un file PostScript che mostra un set completo di motivi a trama applicati sia a forme che a testo—tutto alimentato da **aspose page java**.

## Perché utilizzare i motivi a trama con Aspose.Page Java?
- **Distinzione visiva** – I riempimenti a trama funzionano anche quando le stampanti sono limitate a output monocromatico.  
- **Prestazioni** – Le texture sono generate al volo, così eviti file immagine di grandi dimensioni.  
- **Supporto multi‑formato** – Lo stesso codice può generare PDF, EPS o SVG con modifiche minime.

## Problemi comuni e consigli
- **Errori nei percorsi file** – Assicurati che `dataDir` termini con il separatore di file appropriato (`/` o `\`).  
- **Colori non supportati** – Alcuni interpreter PostScript più vecchi potrebbero non gestire certi spazi colore; usa RGB di base per massima compatibilità.  
- **Avvisi di licenza** – Eseguire ilione senza licenza valida inserirà una filigrana nell'output.

## Conclusione
Incorporare i motivi a trama può migliorare drasticamente la leggibilità e l'estetica di disegni tecnici, mappe o qualsiasi grafica generata da Java. Con **Aspose.Page Java**, ottieni un'API concisa che astrae i comandi PostScript a basso livello, permettendoti di concentrarti sul design anziché sulle particolarità del formato file.

## Domande frequenti

**D: Posso usare Aspose.Page Java con altri framework Java?**  
R: Sì, la libreria è indipendente dal framework e funziona con Spring, Jakarta EE, Android (limitato) e Java SE puro.

**D: È disponibile una versione di prova per Aspose.Page Java?**  
R: Assolutamente. Scarica una prova gratuita di 30 giorni [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per lo sviluppo?**  
R: Richiedi una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/). Rimuove le filigrane di valutazione.

**D: Dove posso trovare altri tutorial e supporto della community?**  
R: Visita il forum ufficiale [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) per esempi aggiuntivi e Q&A.

**D: Esiste una documentazione completa per tutte le classi e i metodi?**  
R: Sì, il riferimento completo dell'API è disponibile [qui](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-08  
**Testato con:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autore:** Aspose