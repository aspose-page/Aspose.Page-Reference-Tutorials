---
date: 2026-01-20
description: Scopri come creare un documento XPS, aggiungere un rettangolo e salvare
  il file XPS usando Aspose.Page per .NET in questa guida passo‑passo.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Crea documento XPS: aggiungi rettangolo con Aspose.Page per .NET'
url: /it/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea documento XPS: aggiungi rettangolo con Aspose.Page per .NET

## Introduzione

In questo tutorial **creerai file documento XPS** e disegnerai un rettangolo al loro interno utilizzando la libreria Aspose.Page per .NET. Aggiungere forme come i rettangoli è una necessità comune quando devi generare fatture, report o grafiche personalizzate in modo programmatico. Segui i passaggi qui sotto e avrai un file XPS pronto all'uso in pochi minuti.

## Risposte rapide
- **Cosa posso generare?** Documenti XPS con grafica vettoriale e testo.  
- **Quale libreria?** Aspose.Page per .NET (disponibile versione di prova gratuita).  
- **Quanto tempo ci vuole?** Circa 5‑10 minuti per implementare ed eseguire.  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea per l'uso in produzione.  
- **Posso salvare il risultato come file XPS?** Sì – il metodo `Save` scrive un **file XPS** su disco.

## Che cosa significa “creare documento XPS”?

Creare un documento XPS significa costruire programmaticamente una descrizione di pagina nel formato XML Paper Specification. Il file risultante è indipendente dalla risoluzione, ideale per la stampa e la visualizzazione di alta qualità su più piattaforme.

## Perché usare Aspose.Page per creare documento XPS?

- **Supporto completo .NET** – funziona con .NET Framework, .NET Core e .NET 5/6+.  
- **API di disegno ricca** – include geometria dei percorsi, pennelli, penne e gestione del testo.  
- **Nessuna dipendenza esterna** – tutto gira in‑processo senza necessità di Office o Acrobat.  

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. **Aspose.Page per .NET** – scaricalo [qui](https://releases.aspose.com/page/net/).  
2. **Una cartella scrivibile** dove verranno memorizzati i file XPS generati.

## Importa spazi dei nomi

Nel tuo progetto .NET, importa gli spazi dei nomi richiesti:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passo 1: Imposta la directory del documento

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Suggerimento:** Usa un percorso assoluto o `Path.Combine` per evitare problemi di separatore di percorso su sistemi operativi diversi.

## Passo 2: Crea un nuovo documento XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

A questo punto hai **creato un oggetto documento XPS** che conterrà tutti gli elementi di disegno.

## Passo 3: Aggiungi un rettangolo (usando create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

La chiamata `CreatePathGeometry` **crea la geometria del percorso** che definisce il contorno del rettangolo. Puoi modificare la stringa di comando in stile SVG per disegnare altre forme.

## Passo 4: Salva il documento (salva file XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

La chiamata a `Save` scrive il **file XPS** nella posizione specificata.

Congratulazioni! Hai **creato con successo un documento XPS**, aggiunto un rettangolo e salvato il file.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `FileNotFoundException` su `doc.Save` | `dataDir` punta a una cartella inesistente | Assicurati che la directory esista o creala con `Directory.CreateDirectory(dataDir)`. |
| Rettangolo non visibile | Profilo colore del tratto mancante o geometria del percorso malformata | Verifica il percorso del file ICC e la stringa di geometria (`M … Z`). |
| Rallentamento delle prestazioni su documenti grandi | Troppi chiamate individuali a `AddPath` | Raggruppa le operazioni di disegno o riutilizza oggetti pennello/penna. |

## Domande frequenti

**D: Aspose.Page è compatibile con tutte le applicazioni .NET?**  
R: Sì, Aspose.Page è progettato per funzionare senza problemi con tutte le applicazioni .NET.

**D: Dove posso trovare la documentazione per Aspose.Page per .NET?**  
R: La documentazione è disponibile [qui](https://reference.aspose.com/page/net/).

**D: Posso provare Aspose.Page per .NET gratuitamente prima di acquistare?**  
R: Sì, puoi ottenere una versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Page per .NET?**  
R: Visita [questo link](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea.

**D: Dove posso trovare supporto della community o fare domande su Aspose.Page per .NET?**  
R: Visita il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per il supporto della community.

---

**Ultimo aggiornamento:** 2026-01-20  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}