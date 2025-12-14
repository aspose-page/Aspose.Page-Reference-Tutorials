---
date: 2025-12-14
description: Scopri come impostare il colore del testo in Java usando Aspose.Page
  per Java, aggiungere testo a PostScript e applicare il contorno al testo per una
  ricca formattazione dei documenti.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Imposta il colore del testo in Java con Aspose.Page – Guida alla manipolazione
  del testo
url: /it/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il colore del testo Java con Aspose.Page – Guida alla manipolazione del testo

## Introduzione
Benvenuti alla nostra guida passo‑passo su **set text color java** mentre si lavora con file PostScript usando Aspose.Page per Java. Aspose.Page per Java è una libreria potente che consente agli sviluppatori di creare e **generate postscript file** documenti, manipolare i font e stilizzare il testo con precisione. In questo tutorial imparerete ad aggiungere testo, cambiarne il colore, regolare la dimensione e persino **apply stroke text** per un aspetto rifinito.

## Risposte rapide
- **Quale libreria mi permette di impostare il colore del testo in Java?** Aspose.Page per Java.
- **Posso usare font di sistema e font personalizzati?** Sì, entrambi sono supportati.
- **Come cambio la dimensione del testo?** Specificando la dimensione del font quando si crea il `Font` o il `DrFont`.
- **È possibile contornare e riempire il testo insieme?** Assolutamente – usa `fillAndStrokeText`.
- **Quale formato di output produce questo tutorial?** Un documento PostScript (`.ps`).

## Cos'è “set text color java”?
Impostare il colore del testo in Java significa definire l'oggetto `Color` che il motore di rendering (qui, Aspose.Page) utilizza quando disegna i caratteri su una pagina. Questa operazione è essenziale per creare documenti visivamente distinti, soprattutto quando si generano **postscript documents** in modo programmatico.

## Perché usare Aspose.Page per Java?
- **Full control** sulla generazione di PostScript senza la necessità di un interprete PostScript nativo.
- **Support for both system and external fonts**, che ti consente di incorporare qualsiasi tipografia necessaria.
- **Easy API** per riempire, contornare e **fill and stroke text**, offrendoti flessibilità nello styling.
- **Cross‑platform** compatibility – scrivi una volta, esegui ovunque Java venga eseguito.

## Prerequisiti
Prima di immergerti, assicurati di avere:

- Conoscenza di base della programmazione Java.
- Libreria Aspose.Page per Java installata. Puoi scaricarla dalla [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Font necessari disponibili nella cartella specificata. Ulteriori dettagli sono nella [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Importa i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per Aspose.Page per Java:

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

## Passo 1: Configura il documento
Innanzitutto, creiamo un nuovo **PostScript document** e configuriamo le opzioni di output.

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

> **Suggerimento:** Il metodo `fillText` utilizza automaticamente il colore corrente se non passi un argomento `Color`, che di default è nero.

## Uso di un font personalizzato e modifica della dimensione del testo
Puoi anche **change text size** e usare un font personalizzato memorizzato nella tua cartella dei font.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Contornare (Stroke) il testo – Applicare Stroke Text
Il contorno del testo gli conferisce un bordo nitido. Qui **apply stroke text** usando un `BasicStroke`.

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

## Passo 6: Salva il documento
Infine, chiudi la pagina e scrivi il file su disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Font not found** | Assicurati che il file del font sia posizionato in `necessary_fonts` e che il percorso della cartella sia aggiunto correttamente tramite `options.setAdditionalFontsFolders`. |
| **Color not applied** | Verifica di chiamare la sovraccarico di `fillText` o `outlineText` che include un argomento `Color`. |
| **Stroke appears too thin** | Aumenta la larghezza del `BasicStroke` (ad esempio, `new BasicStroke(3)`). |
| **Document not opening** | Conferma che il file `.ps` generato sia salvato con l'estensione corretta e che il tuo visualizzatore supporti PostScript. |

## Domande frequenti

**Q:** Posso usare i miei font personalizzati con Aspose.Page per Java?  
A: Sì, puoi usare font personalizzati specificando il nome del font e la dimensione nella classe `DrFont`.

**Q:** Come posso cambiare il colore del testo?  
A: Puoi impostare il colore desiderato usando la classe `Color` quando riempi o contorni il testo.

**Q:** È possibile aggiungere più pagine a un documento PostScript?  
A: Assolutamente! Puoi creare più pagine ripetendo i passaggi di creazione del documento e salvataggio.

**Q:** Qual è lo scopo della classe `ExternalFontCache`?  
A: `ExternalFontCache` è usata per recuperare font personalizzati, garantendo che siano disponibili per la manipolazione del testo.

**Q:** Posso applicare diversi stroke al testo contornato?  
A: Sì, puoi personalizzare la larghezza e il colore dello stroke usando la classe `Stroke` e la classe `Color`, rispettivamente.

## Conclusione
Congratulazioni! Ora sai come **set text color java**, cambiare le dimensioni dei font, **apply stroke text**, e **create postscript document** file usando Aspose.Page per Java. Sperimenta con diversi font, colori e stili di contorno per produrre output PostScript dall'aspetto professionale.

---

**Ultimo aggiornamento:** 2025-12-14  
**Testato con:** Aspose.Page for Java 23.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}