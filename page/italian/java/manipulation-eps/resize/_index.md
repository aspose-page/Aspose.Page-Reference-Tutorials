---
date: 2025-12-02
description: Scopri come ridimensionare i file EPS in Java senza sforzo con Aspose.Page.
  Questa guida passo‑passo ti mostra come ridimensionare gli EPS usando punti, pollici,
  millimetri o percentuali.
language: it
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Come ridimensionare i file EPS in Java con Aspose.Page
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ridimensionare i file EPS in Java con Aspose.Page

## Introduzione
Se stai cercando un modo affidabile **come ridimensionare EPS** file programmaticamente, sei nel posto giusto. In questo tutorial vedremo come ridimensionare le immagini EPS in Java usando la libreria Aspose.Page. Che tu debba raddoppiare le dimensioni, ridurle a una misura specifica o lavorare con percentuali, i passaggi seguenti ti danno il pieno controllo sulle dimensioni di output.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso ridimensionare usando punti, pollici o millimetri?** Sì – l'API supporta tutte e tre le unità più le percentuali.  
- **Ho bisogno di una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è necessaria una licenza per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o successiva.  
- **Il codice è thread‑safe?** Ogni istanza di `PsDocument` è isolata, quindi è possibile elaborare i file in parallelo.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere quanto segue:

- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Page per Java. Puoi scaricarla **[qui](https://releases.aspose.com/page/java/)**.  
- Una conoscenza di base della programmazione Java.  

## Importa pacchetti
Nel tuo progetto Java, includi le importazioni necessarie per poter lavorare con gli oggetti Aspose.Page e i flussi I/O standard.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

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
Lo stesso schema a cinque passaggi si applica; basta sostituire `Units.Points` con `Units.Inches` e regolare il fattore di scala secondo necessità.

## Come ridimensionare EPS usando i millimetri
Ancora, segui gli stessi passaggi, sostituendo l'unità con `Units.Millimeters`. È utile quando ti servono dimensioni metriche per i flussi di lavoro di stampa.

## Come ridimensionare EPS usando le percentuali
Per il ridimensionamento basato su percentuali, mantieni l'unità `Units.Percent`. Moltiplica la larghezza e l'altezza originali per la percentuale desiderata (ad es., `0.5` per una riduzione del 50 %).

## Problemi comuni e consigli
- **Chiudi sempre gli stream** – Nel codice di produzione, avvolgi gli stream in try‑with‑resources per evitare blocchi di file.  
- **Mantieni il rapporto d'aspetto** – Moltiplica sia la larghezza che l'altezza per lo stesso fattore a meno che tu non voglia intenzionalmente una distorsione.  
- **Controlla il DPI** – Il ridimensionamento non modifica il DPI; se ti serve un DPI diverso, regolarlo separatamente dopo il ridimensionamento.

## Conclusione
Ora sai **come ridimensionare i file EPS** in Java usando Aspose.Page, sia che tu preferisca punti, pollici, millimetri o percentuali. Questa flessibilità ti consente di integrare la manipolazione EPS in pipeline automatizzate, utility desktop o servizi lato server.

## Domande frequenti

**Q: Posso usare questa libreria per altri formati di immagine?**  
**A:** No, Aspose.Page è specializzata solo per file PostScript ed EPS.

**Q: È disponibile una prova gratuita per Aspose.Page per Java?**  
**A:** Sì, puoi esplorare la prova gratuita **[qui](https://releases.aspose.com/)**.

**Q: Dove posso trovare ulteriore assistenza e discussioni?**  
**A:** Visita il **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** per il supporto della community.

**Q: Come posso ottenere una licenza temporanea?**  
**A:** Puoi ottenere una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**Q: Sono disponibili progetti di esempio?**  
**A:** Sì, consulta la documentazione **[qui](https://reference.aspose.com/page/java/)**.

---

**Ultimo aggiornamento:** 2025-12-02  
**Testato con:** Aspose.Page for Java 24.12 (l'ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}