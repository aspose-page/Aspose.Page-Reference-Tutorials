---
date: 2026-03-29
description: Scopri come aggiungere oggetti trasparenti ai documenti XPS e poi esportare
  XPS in PDF usando Aspose.Page per .NET. Guida passo‑passo con consigli pratici.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Esporta XPS in PDF – Aggiungi oggetto trasparente con Aspose.Page
url: /it/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta XPS in PDF – Aggiungi oggetto trasparente con Aspose.Page

## Introduzione

In questo tutorial imparerai come aggiungere oggetti trasparenti a un documento XPS e poi **esportare XPS in PDF** con Aspose.Page per .NET. La trasparenza può rendere i tuoi documenti più moderni e aiutarti a evidenziare informazioni importanti. Ti guideremo passo passo, spiegheremo le ragioni del codice e ti mostreremo come completare il flusso di lavoro convertendo il file XPS in un PDF per una facile condivisione.

## Risposte rapide
- **Cosa significa “esportare XPS in PDF”?** Conversione di un file XPS in un file PDF mantenendo layout, colori e trasparenza.  
- **Perché aggiungere prima la trasparenza?** Gli oggetti trasparenti ti consentono di creare grafiche a strati che appaiono ottime nel PDF finale.  
- **È necessaria una licenza?** Sì, è richiesta una licenza valida di Aspose.Page per l'uso in produzione.  
- **Questo funziona su .NET Core?** Assolutamente – Aspose.Page supporta .NET Core, .NET 5/6 e il framework .NET completo.  
- **Dove posso trovare altri esempi?** Consulta la documentazione di Aspose.Page e il forum della community collegati qui sotto.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

- Aspose.Page per .NET: Verifica di avere la libreria Aspose.Page per .NET installata. Puoi scaricarla da [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Importare gli spazi dei nomi

Per iniziare, includi gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ora, procediamo con la guida passo‑passo.

## Passo 1: Creare un nuovo documento XPS

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Questo codice inizializza un nuovo documento XPS usando Aspose.Page per .NET.

## Passo 2: Dimostrare la trasparenza

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Queste righe creano due percorsi grigi che serviranno da sfondo per le forme trasparenti che aggiungeremo più tardi.

## Passo 3: Creare un percorso con una geometria di rettangolo chiuso

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Qui creiamo un rettangolo blu. Poiché in seguito ne modificheremo l'opacità, il rettangolo apparirà semi‑trasparente nel PDF finale.

## Passo 4: Manipolare percorsi e colori

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Cloniamo il primo rettangolo, lo aggiungiamo alla pagina e cambiamo il suo colore di riempimento in verde. Questo dimostra quanto sia semplice riutilizzare geometrie esistenti.

## Passo 5: Clonare e trasformare i percorsi

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Il percorso clonato viene spostato verso il basso di 300 unità e dipinto di rosso, creando un effetto a strati sovrapposti.

## Passo 6: Ripetere e modificare i percorsi

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Riutilizziamo i dati di geometria da `path2`, li spostiamo a destra e applichiamo nuovamente un riempimento blu.

## Passo 7: Gestire l'opacità

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Impostare la proprietà `Opacity` a 0.8 rende questo rettangolo opaco all'80 %, illustrando come è possibile regolare finemente la trasparenza per ciascun elemento.

## Passo 8: Salvare il documento XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Il file XPS è ora salvato con tutti gli oggetti trasparenti applicati.  

**Esporta in PDF:** Per **esportare XPS in PDF**, basta chiamare nuovamente `doc.Save` con estensione `.pdf`, ad esempio `doc.Save(dataDir + "TransparentDocument.pdf");`. La stessa fedeltà visiva, comprese le impostazioni di opacità, viene preservata nel PDF risultante.

## Perché esportare XPS in PDF dopo aver aggiunto la trasparenza?

- **Compatibilità universale:** Il PDF è ampiamente supportato su tutte le piattaforme, mentre XPS è più di nicchia.  
- **Effetti visivi preservati:** Aspose.Page mantiene trasparenza, gradienti e trasformazioni di matrice intatti durante la conversione.  
- **Condivisione semplificata:** I PDF possono essere aperti nei browser, dispositivi mobili e molti lettori di terze parti senza plugin aggiuntivi.

## Casi d'uso comuni

- **Brochure di marketing** dove grafiche a strati conferiscono un aspetto premium.  
- **Diagrammi tecnici** che richiedono sezioni evidenziate senza ingombrare il layout.  
- **Generazione di report** dove si desidera sovrapporre filigrane o loghi con opacità parziale.

## Suggerimenti e avvertenze

- **Consiglio professionale:** Imposta sempre il valore di `Opacity` tra 0 e 1. Valori al di fuori di questo intervallo vengono limitati e potrebbero produrre risultati inattesi.  
- **Consiglio sulle prestazioni:** Riutilizzare la geometria (`path2.Data`) riduce l'uso di memoria quando hai bisogno di molte forme simili.  
- **Trappola:** Salvare direttamente in PDF dopo aver aggiunto la trasparenza funziona subito, ma se in seguito modifichi il PDF con altri strumenti, alcuni visualizzatori più vecchi potrebbero non renderizzare correttamente l'opacità.

## Conclusione

Aggiungere oggetti trasparenti ai documenti XPS usando Aspose.Page per .NET offre un modo versatile per migliorare le presentazioni visive. Una volta che il tuo file XPS ha l'aspetto desiderato, puoi **esportare XPS in PDF** con una singola riga di codice, preservando tutti gli effetti di trasparenza per una ampia distribuzione.

## FAQ

### Q1: Posso applicare la trasparenza a qualsiasi oggetto in un documento XPS?

A1: Sì, la trasparenza può essere applicata a vari oggetti come percorsi, forme e immagini in un documento XPS.

### Q2: Come posso regolare l'opacità di un elemento specifico?

A2: Puoi impostare la proprietà di opacità del Fill o dello Stroke per regolare la trasparenza di un elemento specifico.

### Q3: Aspose.Page è compatibile con .NET Core?

A3: Sì, Aspose.Page supporta .NET Core, consentendo lo sviluppo cross‑platform.

### Q4: Posso esportare documenti XPS in altri formati usando Aspose.Page?

A4: Aspose.Page fornisce funzionalità per esportare documenti XPS in vari formati, inclusi PDF e immagini.

### Q5: Dove posso trovare supporto aggiuntivo e discussioni della community?

A5: Per supporto aggiuntivo e discussioni della community, visita il [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: La conversione PDF mantiene le impostazioni di trasparenza?

A6: Assolutamente. Quando esporti XPS in PDF con Aspose.Page, tutte le impostazioni di opacità e fusione vengono conservate.

### Q7: Posso elaborare in batch più file XPS in PDF?

A7: Sì, puoi iterare su una collezione di file XPS e chiamare `doc.Save(...".pdf")` per ciascuno, automatizzando conversioni di massa.

---

**Ultimo aggiornamento:** 2026-03-29  
**Testato con:** Aspose.Page 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}