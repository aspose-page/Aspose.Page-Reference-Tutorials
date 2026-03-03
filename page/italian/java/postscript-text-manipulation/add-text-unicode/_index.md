---
date: 2025-12-17
description: Scopri come aggiungere testo Unicode in Java PostScript usando Aspose.Page
  – una guida passo passo su come inserire stringhe Unicode senza sforzo.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Come aggiungere testo Unicode in Java PostScript con Aspose.Page
url: /it/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere testo Unicode in Java PostScript con Aspose.Page

## Introduzione
Se ti stai chiedendo **come aggiungere Unicode** caratteri a un flusso di lavoro PostScript (o XPS) basato su Java, sei nel posto giusto. In questo tutorial ti guideremo passo passo attraverso le operazioni necessarie per incorporare stringhe Unicode usando la libreria Aspose.Page per Java. Alla fine della guida sarai in grado di inserire qualsiasi testo specifico di lingua — arabo, cinese, emoji, quello che vuoi — direttamente nel tuo output PostScript.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso aggiungere script da destra a sinistra?** Sì, impostare il livello Bidi come mostrato nel codice  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione  
- **Quale IDE è il migliore?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **Il codice è cross‑platform?** Assolutamente—eseguilo su Windows, macOS o Linux

## Cos'è “come aggiungere Unicode” nel contesto di PostScript?
Aggiungere Unicode significa inserire caratteri rappresentati da punti di codice al di là dell'intervallo ASCII di base. Aspose.Page astrae i dettagli di codifica a basso livello, permettendoti di concentrarti sul contenuto testuale e sul suo posizionamento visivo.

## Perché usare Aspose.Page per testo Unicode?
- **Supporto Unicode completo** – Gestisce script complessi, legature e lingue da destra a sinistra.  
- **Nessuna dipendenza esterna** – Non è necessario gestire manualmente i file dei font; l'API funziona con i font di sistema.  
- **API semplice** – Basta poche chiamate di metodo per renderizzare testo multilingue.

## Prerequisiti
Prima di iniziare, assicurati di avere a disposizione i seguenti elementi:

1. **Java Development Kit (JDK)** – Qualsiasi versione recente (8 o superiore).  
2. **Aspose.Page for Java** – Scarica e installa la libreria dal [download link](https://releases.aspose.com/page/java/).  
3. **IDE a tua scelta** – IntelliJ IDEA, Eclipse o qualsiasi altro IDE Java che preferisci.

## Importare i pacchetti
Aggiungi le classi Aspose.Page necessarie al tuo file sorgente Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Passo 1: Configura il tuo progetto
Crea un nuovo progetto Java, aggiungi il JAR di Aspose.Page al percorso di compilazione del progetto e crea una cartella dove verrà salvato il file XPS generato. Questa cartella sarà poi referenziata come `dataDir`.

## Passo 2: Inizializza il documento XPS
Istanzia un documento XPS vuoto che conterrà il contenuto:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Passo 3: Aggiungi testo Unicode
Ora aggiungeremo effettivamente la stringa Unicode. L'esempio qui sotto scrive la frase invertita “AVAJ rof SPX.esopsA”, che contiene solo caratteri ASCII, ma puoi sostituirla con qualsiasi testo Unicode (ad es. arabo “مرحبا” o cinese “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Suggerimento professionale:** Per renderizzare correttamente le lingue da destra a sinistra, impostare `glyphs.setBidiLevel(1);`. Per gli script da sinistra a destra è possibile omettere questa riga.

## Passo 4: Salva il documento
Persisti il file XPS su disco:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Dopo aver eseguito il programma, apri il file `AddEncodingText_out.xps` generato con qualsiasi visualizzatore XPS per vedere il testo Unicode renderizzato alle coordinate specificate.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il testo appare come quadrati | Font non trovato o non supporta i caratteri | Usare un font che includa i glifi richiesti (es. “Arial Unicode MS”) |
| Il testo da destra a sinistra viene visualizzato da sinistra a destra | Livello Bidi non impostato | Call `glyphs.setBidiLevel(1);` |
| File non salvato | Il percorso `dataDir` è non valido o mancano i permessi di scrittura | Assicurarsi che la directory esista e che l'applicazione abbia i permessi di scrittura |

## Domande frequenti
### Posso usare Aspose.Page per Java con altri linguaggi di programmazione?
Aspose.Page è progettato principalmente per Java, ma Aspose fornisce librerie per vari linguaggi di programmazione.

### È disponibile una versione di prova gratuita?
Sì, puoi accedere a una versione di prova gratuita di Aspose.Page [qui](https://releases.aspose.com/).

### Dove posso trovare supporto e discussioni su Aspose.Page?
Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per supporto e discussioni.

### Come posso ottenere una licenza temporanea per Aspose.Page?
Puoi acquisire una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Quali sono gli stili di font disponibili in Aspose.Page?
Aspose.Page supporta stili di font come Regular, Bold, Italic e BoldItalic.

## Conclusione
Ora hai imparato **come aggiungere Unicode** testo a un documento Java PostScript (XPS) usando Aspose.Page. Questa funzionalità apre la porta a report multilingue, fatture internazionalizzate e qualsiasi scenario in cui siano richiesti caratteri non‑ASCII. Sentiti libero di esplorare funzionalità aggiuntive come rotazione del testo, percorsi di ritaglio o incorporamento di font personalizzati—i dettagli sono disponibili nella documentazione ufficiale [qui](https://reference.aspose.com/page/java/).

---

**Ultimo aggiornamento:** 2025-12-17  
**Testato con:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Autore:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
