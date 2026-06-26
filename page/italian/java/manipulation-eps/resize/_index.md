---
date: 2026-02-07
description: Scopri come ridimensionare i file EPS in Java e modificare le dimensioni
  EPS usando Aspose.Page. Questa guida passo‑passo ti mostra come ridimensionare gli
  EPS in punti, pollici, millimetri o percentuali.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Come ridimensionare i file EPS in Java con Aspose.Page
url: /it/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare i file EPS in Java con Aspose.Page

## Introduzione
Se stai cercando un modo affidabile **come ridimensionare EPS** file programmaticamente, sei nel posto giusto. In questo tutorial vedremo come ridimensionare le immagini EPS in Java usando la libreria Aspose.Page. Che tu debba raddoppiare le dimensioni, ridurle a una misura specifica o lavorare con percentuali, i passaggi seguenti ti danno il pieno controllo sulle dimensioni di output. Comprendere **come ridimensionare eps** è essenziale quando è necessario adattare la grafica a diversi layout di stampa o risoluzioni dello schermo.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso ridimensionare usando punti, pollici o millimetri?** Sì – l'API supporta tutte e tre le unità più le percentuali.  
- **Ho bisogno di una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è necessaria una licenza per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o successiva.  
- **Il codice è thread‑safe?** Ogni istanza di `PsDocument` è isolata, quindi è possibile elaborare i file in parallelo.  

## Cos'è EPS e perché ridimensionarlo?
Encapsulated PostScript (EPS) è un formato di grafica vettoriale popolare usato nell'editoria e nella stampa. Talvolta il file EPS originale è creato con una dimensione che non corrisponde all'output desiderato – ad esempio, un logo progettato a 72 pts potrebbe dover essere a 144 pts per un opuscolo più grande. Conoscere **come ridimensionare eps** ti permette di mantenere la qualità vettoriale adattando le dimensioni a qualsiasi flusso di lavoro.

## Perché usare Aspose.Page per ridimensionare EPS?
- **Controllo totale sulle unità** – punti, pollici, millimetri o percentuali.  
- **Nessuna dipendenza esterna** – API Java pura, nessuna libreria nativa.  
- **Alte prestazioni** – adatto per l'elaborazione batch su server.  
- **Preserva la fedeltà vettoriale** – l'output rimane scalabile senza rasterizzazione.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Page for Java. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Una conoscenza di base della programmazione Java.  

## Importare i pacchetti
Nel tuo progetto Java, includi gli import necessari in modo da poter lavorare con gli oggetti Aspose.Page e i flussi I/O standard.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Come modificare le dimensioni EPS con unità diverse
La libreria ti consente di **modificare le dimensioni eps** semplicemente selezionando l'enumerazione `Units` appropriata. Di seguito vedremo lo stesso schema a cinque passaggi per punti, pollici, millimetri e percentuali. L'unica cosa che cambia è l'unità che passi a `resizeEps`.

## Come ridimensionare EPS usando i punti
Di seguito trovi un esempio completo, passo‑per‑passo, che raddoppia le dimensioni di un file EPS usando i punti come unità di misura.

### Passo 1: Configura lo stream di input
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Passo 2: Inizializza l'oggetto `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Passo 3: Estrai le dimensioni attuali dell'immagine EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Passo 4: Crea uno stream di output per il file ridimensionato
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Passo 5: Ridimensiona e salva l'EPS usando i punti
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Come ridimensionare EPS usando i pollici
Lo stesso schema a cinque passaggi si applica; basta sostituire `Units.Points` con `Units.Inches` e regolare il fattore di scala al valore in pollici desiderato.

## Come ridimensionare EPS usando i millimetri
Ancora, segui gli stessi passaggi, sostituendo l'unità con `Units.Millimeters`. È utile quando hai bisogno di dimensioni metriche per i flussi di lavoro di stampa.

## Come ridimensionare EPS usando le percentuali
Per il ridimensionamento basato su percentuali, mantieni l'unità come `Units.Percent`. Moltiplica la larghezza e l'altezza originali per la percentuale desiderata (ad esempio, `0.5` per una riduzione del 50 %).

## Problemi comuni e consigli
- **Chiudi sempre gli stream** – Nel codice di produzione, avvolgi gli stream in try‑with‑resources per evitare blocchi di file.  
- **Preserva il rapporto d'aspetto** – Moltiplica sia la larghezza che l'altezza per lo stesso fattore a meno che non desideri intenzionalmente una distorsione.  
- **Controlla il DPI** – Il ridimensionamento non cambia il DPI; se ti serve un DPI diverso, regolalo separatamente dopo il ridimensionamento.  
- **Sicurezza dei thread** – Crea un nuovo `PsDocument` per thread; condividere la stessa istanza può portare a risultati inattesi.  

## Domande frequenti

**D: Posso usare questa libreria per altri formati immagine?**  
R: No, Aspose.Page è specializzata solo per file PostScript ed EPS.

**D: È disponibile una prova gratuita per Aspose.Page for Java?**  
R: Sì, puoi esplorare la prova gratuita **[qui](https://releases.aspose.com/)**.

**D: Dove posso trovare ulteriore aiuto e discussioni?**  
R: Visita il **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** per il supporto della community.

**D: Come posso ottenere una licenza temporanea?**  
R: Puoi ottenere una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**D: Sono disponibili progetti di esempio?**  
R: Sì, controlla la documentazione **[qui](https://reference.aspose.com/page/java/)**.

---

**Ultimo aggiornamento:** 2026-02-07  
**Testato con:** Aspose.Page for Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}