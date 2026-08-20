---
date: 2026-03-21
description: Scopri come aggiungere testo Unicode a un documento XPS utilizzando Aspose.Page
  per .NET. Questa guida ti mostra come creare un documento XPS in C# e aggiungere
  testo con stringhe Unicode usando Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Come aggiungere testo Unicode a un documento XPS con Aspose.Page
url: /it/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere testo Unicode a un documento XPS con Aspose.Page

## Introduzione

Se hai bisogno di **how to add unicode** caratteri in un file XPS, sei nel posto giusto. In questo tutorial percorreremo i passaggi esatti necessari per **create XPS document C#**‑style usando Aspose.Page per .NET e dimostreremo la capacità **aspose page add text** con una stringa Unicode. Alla fine avrai un documento XPS completamente funzionale che visualizza correttamente il testo Unicode da destra a sinistra (RTL).

## Risposte rapide
- **Che cosa copre il tutorial?** Aggiungere testo Unicode a un documento XPS con Aspose.Page per .NET.  
- **Quale linguaggio è usato?** C# (compatibile con .NET Framework e .NET Core).  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso cambiare il font o la dimensione?** Sì – l'esempio utilizza Arial 20 pt, ma qualsiasi font installato funziona.  
- **Il supporto RTL è incluso?** Impostare `BidiLevel = 1` abilita il rendering da destra a sinistra per le stringhe Unicode.

## Che cosa significa “how to add unicode” in XPS?

Aggiungere testo Unicode significa inserire caratteri di qualsiasi lingua—arabo, ebraico, cinese, ecc.—in un documento XPS. La classe `XpsGlyphs` di Aspose.Page gestisce il posizionamento a basso livello dei glifi, mentre la proprietà `BidiLevel` controlla la direzione del testo per gli script RTL.

## Perché usare Aspose.Page per aggiungere testo?

- **Integrazione completa con .NET** – funziona con .NET Framework, .NET Core, .NET 5/6+.  
- **Nessuna dipendenza esterna** – codice gestito puro, senza interop COM.  
- **Supporto tipografico avanzato** – font, stili, colori e testo bidirezionale.  
- **Alte prestazioni** – crea e salva file XPS rapidamente, ideale per la generazione lato server.

## Prerequisiti

- Conoscenza di base di C# e sviluppo .NET.  
- Visual Studio (qualsiasi versione recente).  
- Libreria Aspose.Page per .NET – scaricala da [here](https://releases.aspose.com/page/net/).

## Importare gli spazi dei nomi

Prima, importa gli spazi dei nomi che ti danno accesso al modello XPS e alle utility di disegno.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Passo 1: Configurare il documento – create XPS document C#

Crea un nuovo documento XPS che ospiterà il testo Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Passo 2: Aggiungere testo Unicode – aspose page add text

Ora aggiungiamo la stringa Unicode effettiva. In questo esempio usiamo il font Arial, dimensione 20, e posizioniamo il testo a (400 f, 200 f). Il `BidiLevel` di 1 indica al renderer di trattare la stringa come da destra a sinistra.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Passo 3: Salvare il documento

Infine, persisti il file XPS su disco.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Congratulazioni! Hai aggiunto con successo **how to add unicode** testo a un documento XPS usando Aspose.Page per .NET.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il testo appare distorto | Il font non supporta l'intervallo Unicode | Usa un font che contiene i glifi richiesti (ad es., Arial Unicode MS). |
| Il testo RTL è ancora da sinistra a destra | `BidiLevel` non impostato o impostato a 0 | Assicurati che `glyphs.BidiLevel = 1;` per gli script RTL. |
| Il file non viene salvato | Percorso `dataDir` non valido | Verifica che la directory esista e che l'app abbia i permessi di scrittura. |

## Domande frequenti

**Q: Aspose.Page è compatibile con gli ultimi framework .NET?**  
A: Sì, Aspose.Page è regolarmente aggiornato per supportare .NET Framework, .NET Core e .NET 5/6+.

**Q: Posso personalizzare lo stile e la dimensione del font quando aggiungo testo?**  
A: Assolutamente! Il metodo `AddGlyphs` ti consente di specificare qualsiasi famiglia di font, dimensione e `FontStyle` necessario.

**Q: Dove posso trovare documentazione aggiuntiva per Aspose.Page?**  
A: Puoi consultare la documentazione [here](https://reference.aspose.com/page/net/) per dettagli completi sull'API.

**Q: Esistono risorse gratuite per iniziare con Aspose.Page?**  
A: Sì, esplora il forum della community su [Aspose.Page forum](https://forum.aspose.com/c/page/39) per suggerimenti, esempi e supporto da parte della community.

**Q: È disponibile una versione di prova prima di effettuare l'acquisto?**  
A: Certamente! Scarica la versione di prova gratuita da [here](https://releases.aspose.com/) per valutare la libreria.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}