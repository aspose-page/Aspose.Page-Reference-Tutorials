---
date: 2026-02-20
description: Scopri come impostare il colore del testo in Java usando Aspose.Page
  per Java, modificare la dimensione del carattere in Java, generare un file PostScript,
  riempire e tracciare il testo e utilizzare font personalizzati in Java durante la
  creazione di un documento PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Imposta il colore del testo in Java con Aspose.Page – Guida alla manipolazione
  del testo
url: /it/java/postscript-text-manipulation/add-text/
weight: 10
---

 Java con Aspose.Page – Guida alla manipolazione del testo"

- Introduction etc.

Make sure to keep markdown formatting.

Let's translate step by step.

Will keep shortcodes at top and bottom.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il colore del testo Java con Aspose.Page – Guida alla manipolazione del testo

## Introduzione
Benvenuti nella nostra guida passo‑passo su **set text color java** mentre lavorate con file PostScript utilizzando Aspose.Page per Java. Aspose.Page per Java è una libreria potente che consente agli sviluppatori di **create postscript document** file, manipolare i caratteri e stilizzare il testo con precisione. In questo tutorial imparerete ad aggiungere testo, cambiare il suo colore, **change font size java**, e persino **apply fill and stroke text** per un aspetto curato.

## Risposte rapide
- **Quale libreria mi permette di impostare il colore del testo in Java?** Aspose.Page per Java.  
- **Posso usare font di sistema e font personalizzati?** Sì, entrambi sono supportati, e potete **use custom fonts java** facilmente.  
- **Come cambio la dimensione del testo?** Specificando la dimensione del font quando create il `Font` o il `DrFont`.  
- **È possibile contornare e riempire il testo contemporaneamente?** Assolutamente – usate `fillAndStrokeText`.  
- **Quale formato di output produce questo tutorial?** Un documento PostScript (`.ps`), che potete **generate postscript file** programmaticamente.

## Che cosa è “set text color java”?
Impostare il colore del testo in Java significa definire l'oggetto `Color` che il motore di rendering (qui, Aspose.Page) utilizza quando disegna i caratteri su una pagina. Questa operazione è essenziale per creare documenti visivamente distinti, soprattutto quando è necessario **generate postscript file** programmaticamente.

## Perché usare Aspose.Page per Java?
- **Controllo totale** sulla generazione di PostScript senza bisogno di un interprete nativo.  
- **Supporto sia per i font di sistema che per quelli esterni**, consentendo di incorporare qualsiasi tipografia necessaria.  
- **API semplice** per riempire, contornare e **fill and stroke text**, offrendo flessibilità nello styling.  
- **Compatibilità cross‑platform** – scrivi una volta, esegui ovunque Java venga eseguito.  

## Prerequisiti
Prima di iniziare, assicuratevi di avere:

- Conoscenze di base della programmazione Java.  
- Libreria Aspose.Page per Java installata. Potete scaricarla dalla [pagina di download di Aspose.Page per Java](https://releases.aspose.com/page/java/).  
- Font necessari disponibili nella cartella specificata. Ulteriori dettagli sono nella [documentazione di Aspose.Page per Java](https://reference.aspose.com/page/java/).  

## Importare i pacchetti
Nel vostro progetto Java, importate i pacchetti necessari per Aspose.Page per Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Passo 1: Configurare il documento
Per prima cosa, creiamo un nuovo **PostScript document** e configuriamo le opzioni di output.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Come impostare il colore del testo Java usando un font di sistema
Ora dimostriamo **set text color java** con un font fornito dal sistema.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Suggerimento:** Il metodo `fillText` utilizza automaticamente il colore corrente se non passate un argomento `Color`, il cui valore predefinito è nero.

## Uso di un font personalizzato e modifica della dimensione del testo
Potete anche **change font size java** e usare un font personalizzato memorizzato nella vostra cartella dei font.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Contornare (Stroke) il testo – Applicare Stroke Text
Contornare il testo gli conferisce un bordo nitido. Qui **apply stroke text** usando un `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Contornare il testo con font personalizzato
La stessa tecnica funziona con i font personalizzati.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Passo 6: Salvare il documento
Infine, chiudete la pagina e scrivete il file su disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Perché è importante
Essere in grado di **set text color java** e combinare riempimento con contorno vi dà il pieno controllo artistico sull'output PostScript finale. Che stiate generando fatture, certificati o grafiche personalizzate, la capacità di **create postscript document** con styling preciso riduce la necessità di post‑produzione in editor grafici.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Font non trovato** | Assicuratevi che il file del font sia posizionato in `necessary_fonts` e che il percorso della cartella sia correttamente aggiunto tramite `options.setAdditionalFontsFolders`. |
| **Colore non applicato** | Verificate di chiamare la sovraccarico di `fillText` o `outlineText` che includa un argomento `Color`. |
| **Il contorno appare troppo sottile** | Incrementate la larghezza del `BasicStroke` (es., `new BasicStroke(3)`). |
| **Il documento non si apre** | Confermate che il file `.ps` generato sia salvato con l'estensione corretta e che il vostro visualizzatore supporti PostScript. |

## Domande frequenti

**D:** Posso usare i miei font personalizzati con Aspose.Page per Java?  
**R:** Sì, potete **use custom fonts java** specificando il nome e la dimensione del font nella classe `DrFont`.

**D:** Come posso cambiare il colore del testo?  
**R:** Potete impostare il colore desiderato usando la classe `Color` quando riempite o contornate il testo.

**D:** È possibile aggiungere più pagine a un documento PostScript?  
**R:** Assolutamente! Potete creare più pagine ripetendo i passaggi di creazione e salvataggio del documento.

**D:** Qual è lo scopo della classe `ExternalFontCache`?  
**R:** `ExternalFontCache` serve a recuperare font personalizzati, garantendo che siano disponibili per la manipolazione del testo.

**D:** Posso applicare diversi contorni al testo contornato?  
**R:** Sì, potete personalizzare larghezza e colore del contorno usando la classe `Stroke` e la classe `Color`, rispettivamente.

## Conclusione
Complimenti! Ora sapete come **set text color java**, **change font size java**, **apply fill and stroke text**, e **create postscript document** usando Aspose.Page per Java. Sperimentate con diversi font, colori e stili di contorno per produrre output PostScript dall'aspetto professionale.

---

**Ultimo aggiornamento:** 2026-02-20  
**Testato con:** Aspose.Page per Java 23.12 (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}