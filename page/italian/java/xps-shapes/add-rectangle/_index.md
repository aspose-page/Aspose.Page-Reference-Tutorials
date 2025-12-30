---
date: 2025-12-30
description: Scopri come creare documenti XPS in Java aggiungendo rettangoli con Aspose.Page.
  Segui questa guida passo passo per una manipolazione fluida dei documenti XPS.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Crea documento XPS Java – Aggiungi rettangolo con Aspose.Page
url: /it/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS Java – Aggiungi rettangolo

## Introduzione
In questo tutorial completo **creerai file XPS document Java** e imparerai come aggiungere rettangoli usando la libreria Aspose.Page. Che tu stia creando report, fatture o grafiche personalizzate, padroneggiare la creazione di rettangoli ti offre un controllo preciso sul layout XPS. Ti guideremo passo passo, spiegheremo il perché di ogni riga di codice e ti mostreremo come personalizzare colori e tratti per risultati professionali.

## Risposte rapide
- **Quale libreria è consigliata?** Aspose.Page per Java  
- **Quanto tempo richiede l'implementazione?** Circa 10 minuti per un rettangolo di base  
- **È necessaria una licenza?** Una prova gratuita funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione  
- **Quale versione di Java è supportata?** Java 8 e successive  
- **Posso aggiungere più forme?** Sì – ripeti i passaggi per ogni forma

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base del linguaggio di programmazione Java.  
- Libreria Aspose.Page installata. In caso contrario, puoi scaricarla dalla [documentazione Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Un ambiente di sviluppo Java funzionante (IDE, JDK e Maven/Gradle se preferisci).

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Assicurati che la libreria Aspose.Page sia correttamente aggiunta al classpath. Ecco un esempio di base:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Ora, analizziamo l'esempio fornito suddividendolo in più passaggi per aggiungere un rettangolo in Java XPS.

## Passo 1: Imposta la directory del documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso della cartella in cui desideri memorizzare i file XPS.

## Passo 2: Crea un nuovo documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Questa riga **crea** un nuovo documento XPS che potrai successivamente popolare con forme, testo o immagini.

## Passo 3: Aggiungi un rettangolo con contorno a colore solido CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Questo passaggio aggiunge un rettangolo con contorno a colore solido CMYK. Puoi modificare la stringa di geometria (`"M 20,10 L 220,10 220,100 20,100 Z"`) per cambiare dimensioni o posizione, e regolare i valori di colore in `createColor` per adattarli al tuo design.

## Passo 4: Salva il documento XPS risultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Infine, salva il documento XPS modificato con il rettangolo aggiunto nella directory specificata in precedenza.

## Casi d'uso comuni
- **Intestazioni di report** – Usa i rettangoli come blocchi di sfondo per i titoli.  
- **Tabelle di fattura** – Evidenzia celle o sezioni con bordi colorati.  
- **Grafica personalizzata** – Combina più rettangoli per creare forme complesse.

## Suggerimenti per la risoluzione dei problemi
- **Errore file non trovato:** Verifica che `dataDir` punti a una cartella esistente e che il profilo ICC (`uswebuncoated.icc`) sia presente.  
- **Colori errati:** Assicurati che il profilo ICC corrisponda allo spazio colore che intendi utilizzare (CMYK vs. RGB).  
- **Dimensioni inattese:** Regola la stringa di geometria per riflettere le coordinate corrette.

## Conclusione
Congratulazioni! Hai appreso con successo come **creare file XPS document Java** e aggiungere rettangoli usando Aspose.Page. Questa base ti permette di costruire documenti XPS più ricchi, personalizzare grafiche e integrare forme in flussi di lavoro più ampi.

## FAQ
### Posso aggiungere più rettangoli in un unico documento XPS?
Sì, puoi aggiungere quanti rettangoli desideri ripetendo i passaggi descritti nel tutorial.

### Come posso cambiare il colore del rettangolo?
Modifica i valori di colore nel metodo `createColor` per ottenere il colore desiderato.

### Aspose.Page è adatto per gestire manipolazioni complesse di documenti XPS?
Assolutamente! Aspose.Page offre un set robusto di funzionalità per gestire varie attività sui documenti XPS.

### Dove posso trovare esempi aggiuntivi e supporto?
Esplora il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per ulteriori esempi e chiedi assistenza alla community.

### Posso provare Aspose.Page prima di acquistarlo?
Sì, puoi esplorare una [prova gratuita](https://releases.aspose.com/) per sperimentare le capacità di Aspose.Page.

## Domande frequenti

**D: Questo approccio funziona con Java 11 o versioni successive?**  
R: Sì, la libreria Aspose.Page è compatibile con Java 8 e successive, incluse Java 11, 17 e oltre.

**D: Posso incorporare immagini all'interno dell'area del rettangolo?**  
R: Puoi aggiungere un elemento `XpsImage` e posizionarlo sopra o dentro il rettangolo usando le stesse coordinate di geometria.

**D: Come impostare un colore di riempimento anziché solo il contorno?**  
R: Chiama `path.setFill(...)` con un pennello a colore solido creato tramite `doc.createSolidColorBrush(...)`.

**D: È possibile ruotare il rettangolo?**  
R: Applica una matrice di trasformazione al percorso usando `path.setTransform(...)` per ottenere rotazione o scala.

**D: Quale licenza è necessaria per l'uso in produzione?**  
R: È richiesta una licenza commerciale Aspose.Page per il deployment; la prova gratuita è limitata a valutazione e sviluppo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2025-12-30  
**Testato con:** Aspose.Page per Java 24.12 (latest)  
**Autore:** Aspose  

---