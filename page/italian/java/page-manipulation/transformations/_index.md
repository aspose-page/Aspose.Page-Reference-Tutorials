---
date: 2025-12-07
description: Scopri come scalare un rettangolo, traslare una forma e applicare la
  trasformazione affine in Java usando Aspose.Page per creare documenti PostScript.
language: it
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Come scalare un rettangolo e applicare trasformazioni con Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare un rettangolo e applicare trasformazioni con Aspose.Page

## Introduzione
Benvenuti in una guida completa sull'utilizzo delle potenti funzionalità di **Aspose.Page for Java** per eseguire una varietà di trasformazioni di pagina. In questo tutorial imparerete **come ridimensionare un rettangolo**, tradurre forme, ruotare oggetti e **applicare trasformazioni affini** durante la creazione di un **documento PostScript**. Queste capacità vi consentono di costruire applicazioni Java ricche di grafica senza dover gestire codice di rendering a basso livello.

## Risposte rapide
- **Come faccio a ridimensionare un rettangolo in Java con Aspose.Page?** Utilizzate il metodo `document.scale()` prima di disegnare la forma.  
- **Posso spostare (tradurre) una forma senza influenzare altre grafiche?** Sì — salvate lo stato grafico, chiamate `document.translate(x, y)`, disegnate, quindi ripristinate lo stato.  
- **Quale classe crea un file PostScript?** `PsDocument` insieme a `PsSaveOptions`.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza valida di Aspose.Page per le distribuzioni commerciali.  
- **Quale versione di Java è supportata?** Aspose.Page funziona con Java 8 e versioni successive.

## Prerequisiti
Prima di immergerci nella guida passo‑passo, assicuratevi di avere i seguenti prerequisiti:

- Conoscenze di base della programmazione Java.  
- Libreria Aspose.Page for Java installata. Potete scaricarla dalla [documentazione di Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un ambiente di sviluppo integrato (IDE) Java configurato sulla vostra macchina.

## Importare i pacchetti
Nel vostro progetto Java, importate i pacchetti necessari per utilizzare Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cos'è “how to scale rectangle” in Aspose.Page?
Il ridimensionamento di un rettangolo ne modifica le dimensioni lungo gli assi X e Y mantenendo la forma. Aspose.Page espone il metodo `scale(float sx, float sy)`, che applica una **trasformazione affine** allo stato grafico corrente. Questa è la tecnica centrale dietro la keyword **how to scale rectangle**.

## Come tradurre una forma con Aspose.Page
La traduzione sposta una forma in una nuova posizione senza alterarne le dimensioni. Questo è il fulcro di **how to translate shape**. Salvando lo stato grafico, applicando `translate(dx, dy)`, disegnando e poi ripristinando lo stato, gli altri oggetti rimangono invariati.

## Esempio 1: Nessuna trasformazione
Il primo esempio disegna un semplice rettangolo senza alcuna trasformazione applicata. Serve come riferimento di base per il confronto con gli esempi successivi.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Esempio 2: Traslazione
Qui dimostriamo **how to translate shape** spostando il contesto grafico di 250 unità verso destra prima di disegnare un secondo rettangolo.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Esempio 3: Ridimensionamento
Questo esempio risponde alla domanda principale **how to scale rectangle**. Riduciamo il rettangolo al 50 % della sua larghezza originale e al 75 % della sua altezza.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Come ruotare una forma in Java (rotate shape java)
La rotazione è un'altra operazione affine comune. Sebbene gli snippet di codice per la rotazione siano omessi per brevità, il modello è identico: salvate lo stato grafico, chiamate `document.rotate(angle)`, disegnate la forma, quindi ripristinate. Questo dimostra **rotate shape java** e **how to rotate rectangle** in pratica.

## Perché usare Aspose.Page per queste trasformazioni?
- **Indipendente dal dispositivo**: Scrivi una volta, genera PostScript o XPS senza codice specifico per la piattaforma.  
- **Controllo fine‑grained**: L'accesso diretto allo stato grafico consente di combinare traduzione, ridimensionamento, shear e rotazione.  
- **Prestazioni**: API a basso overhead adatta per l'elaborazione batch di grandi documenti.  

## Casi d'uso comuni
- Generazione di fatture stampabili con codici a barre dinamici e loghi.  
- Creazione di diagrammi tecnici dove sono richiesti ridimensionamento e posizionamento precisi.  
- Automazione della produzione di report multipagina in formato PostScript.

## Conclusione
In questo tutorial abbiamo esplorato varie trasformazioni nella manipolazione di pagine Java usando Aspose.Page for Java, concentrandoci su **how to scale rectangle**, **how to translate shape** e altre operazioni affini. Seguendo questi esempi, potrete potenziare le vostre applicazioni Java con capacità avanzate di manipolazione di pagine e **creare documenti PostScript** che soddisfano gli standard professionali di pubblicazione.

## FAQ's
### Posso usare Aspose.Page for Java per altri formati di documento?
Aspose.Page si concentra principalmente sulla manipolazione di pagine per i formati PostScript e XPS.

### Dove posso trovare altri esempi e documentazione per Aspose.Page for Java?
Visitate la [documentazione di Aspose.Page for Java](https://reference.aspose.com/page/java/) per informazioni complete.

### È disponibile una versione di prova gratuita per Aspose.Page for Java?
Sì, potete accedere a una prova gratuita [qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Page for Java?
Ottenete una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso cercare supporto della community o fare domande su Aspose.Page for Java?
Visitate il [forum di Aspose.Page for Java](https://forum.aspose.com/c/page/39) per discussioni della community.

## Domande frequenti

**D: Qual è la differenza tra `translate` e `scale`?**  
R: `translate` sposta l'origine del sistema di coordinate, mentre `scale` modifica le dimensioni degli oggetti disegnati lungo gli assi X e/o Y.

**D: Posso combinare più trasformazioni in un unico stato grafico?**  
R: Sì — chiamando `translate`, `scale`, `rotate` o `shear` in sequenza prima del disegno, si crea una trasformazione affine combinata.

**D: Come resetto le trasformazioni dopo aver disegnato una forma?**  
R: Utilizzate `document.writeGraphicsRestore()` per tornare allo stato grafico precedentemente salvato.

**D: È possibile ruotare un rettangolo attorno al suo centro?**  
R: Assolutamente. Traslate il rettangolo all'origine, applicate `rotate(angle)`, quindi translate di nuovo nella posizione originale prima del disegno.

**D: Aspose.Page supporta l'anti‑aliasing per grafica più liscia?**  
R: Sì — impostate le opzioni di rendering appropriate in `PsSaveOptions` per abilitare l'anti‑aliasing.

---

**Ultimo aggiornamento:** 2025-12-07  
**Testato con:** Aspose.Page for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}