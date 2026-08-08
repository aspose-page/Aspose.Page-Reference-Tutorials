---
date: 2026-04-24
description: Impara come impostare il colore del rettangolo e aggiungere un rettangolo
  in Java XPS usando Aspose.Page. Questa guida copre l'aggiunta di un rettangolo in
  Java e la modifica del tratto del rettangolo.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Aggiungi rettangolo in Java XPS
second_title: Aspose.Page Java API
title: Imposta il colore del rettangolo e aggiungi il rettangolo in Java XPS
url: /it/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il colore del rettangolo e aggiungi un rettangolo in Java XPS

## Introduzione
In questa guida imparerai a **impostare il colore del rettangolo** e **aggiungere un rettangolo** in Java XPS usando la libreria Aspose.Page. Che tu debba disegnare forme semplici per un report o creare grafiche vettoriali complesse, padroneggiare lo stile dei rettangoli ti dà un controllo preciso sui tuoi documenti XPS.  

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Page for Java  
- **Posso modificare il contorno del rettangolo?** Sì, usando `setStroke` e `setStrokeThickness`  
- **È supportato un profilo colore CMYK?** Assolutamente – puoi caricare profili ICC come mostrato  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale per l'uso non‑valutativo  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti per un rettangolo di base

## Cos'è **set rectangle color**?
Impostare il colore di un rettangolo significa definire il colore di riempimento o di contorno con cui la forma verrà renderizzata nel documento XPS finale. Con Aspose.Page puoi usare RGB, CMYK o anche profili colore ICC personalizzati per ottenere una corrispondenza cromatica esatta.

## Perché usare Aspose.Page per **add rectangle java** e **change rectangle stroke**?
- **Full‑featured API** – supporta sia colori solidi che gradienti.  
- **Cross‑platform** – funziona su qualsiasi runtime Java senza dipendenze native.  
- **Rich geometry support** – crea percorsi complessi, applica trasformazioni e gestisci facilmente lo spessore del contorno.  

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Page installata. Se non lo è, scaricala dalla [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Un ambiente di sviluppo Java funzionante (IDE, JDK, ecc.).  

## Importa i pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Assicurati che la libreria Aspose.Page sia correttamente aggiunta al classpath. Ecco un esempio di base:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Ora, analizziamo l'esempio fornito in più passaggi per **aggiungere un rettangolo** e **impostarne il colore** in Java XPS.

## Passo 1: Imposta la directory del documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Sostituisci `"Your Document Directory"` con il percorso assoluto dove desideri leggere/scrivere i file XPS.

## Passo 2: Crea un nuovo documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Questa riga inizializza un nuovo documento XPS che conterrà le nostre forme.

## Passo 3: Aggiungi un rettangolo con contorno a colore solido CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Questo passaggio aggiunge un **rettangolo con contorno** di colore solido CMYK. Il metodo `setStroke` definisce il colore del contorno del rettangolo, mentre `setStrokeThickness` controlla lo spessore della linea—perfetto per **cambiare il contorno del rettangolo**.

### Suggerimento professionale:
Se preferisci un colore RGB, sostituisci la chiamata `createColor` con `doc.createColor(0, 0, 255)` per un riempimento blu solido.

## Passo 4: Salva il documento XPS risultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Infine, persisti il documento XPS su disco. Il file `AddRectangle_out.xps` ora contiene un rettangolo il cui colore e contorno hai definito.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Rettangolo non visibile** | Geometria del percorso errata o spessore del contorno impostato a 0 | Verifica la stringa del percorso (`"M 20,10 L 220,10 220,100 20,100 Z"`) e assicurati che `setStrokeThickness` sia maggiore di 0. |
| **Colore errato** | Utilizzo di un profilo ICC che non corrisponde allo spazio colore desiderato | Usa `doc.createColor(r, g, b)` per RGB o ricontrolla il percorso del file ICC. |
| **File non salvato** | `dataDir` punta a una cartella inesistente o non ha i permessi di scrittura | Crea la cartella in anticipo o scegli una posizione scrivibile. |

## Domande frequenti

**Q:** *Posso aggiungere più rettangoli in un unico documento XPS?*  
**A:** Sì. Basta ripetere i passaggi di creazione della geometria e di styling per ogni rettangolo di cui hai bisogno.

**Q:** *Come posso cambiare il colore di riempimento del rettangolo invece del contorno?*  
**A:** Usa `path.setFill(...)` con un pennello a colore solido, in modo simile a come viene usato `setStroke`.

**Q:** *Aspose.Page è adatto per manipolazioni complesse di documenti XPS?*  
**A:** Assolutamente. La libreria supporta funzionalità avanzate come gradienti, trasformazioni e font incorporati.

**Q:** *Dove posso trovare esempi aggiuntivi e supporto della community?*  
**A:** Esplora il [Aspose.Page forum](https://forum.aspose.com/c/page/39) per ulteriori esempi di codice e assistenza da parte di altri utenti.

**Q:** *Posso provare Aspose.Page prima di acquistarlo?*  
**A:** Sì, puoi esplorare una [free trial](https://releases.aspose.com/) per valutare le capacità dell'API.

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.Page for Java 24.12  
**Autore:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}