---
date: 2026-01-07
description: Impara come creare un documento XPS, aggiungere cloni di glifi, utilizzare
  un pennello a colore solido e salvare il file XPS con Aspose.Page per .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Crea documento XPS – Aggiungi clone di glifo e cambia colore con Aspose.Page
  per .NET
url: /it/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare un documento XPS – Aggiungere un clone di glifo e cambiare colore con Aspose.Page per .NET

## Introduzione

Benvenuti in questa guida passo‑passo che mostra **come creare file di documento XPS**, clonare glifi e cambiare i loro colori usando Aspose.Page per .NET. Che stiate creando report dinamici, fatture o grafiche personalizzate, padroneggiare queste tecniche vi permette di produrre output XPS visivamente ricchi senza uscire dall'ecosistema .NET.

## Risposte rapide
- **Qual è l'obiettivo principale?** Creare un documento XPS, aggiungere cloni di glifi e cambiare i loro colori.  
- **Quale libreria viene utilizzata?** Aspose.Page per .NET.  
- **Ho bisogno di una licenza?** È disponibile una licenza temporanea per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Come salvo il risultato?** Utilizzare il metodo `Save` per scrivere il file XPS su disco.

## Prerequisiti

Prima di immergervi nel tutorial, assicuratevi di avere i seguenti prerequisiti:

- Una conoscenza di base del linguaggio di programmazione C#.  
- Visual Studio o qualsiasi altro ambiente di sviluppo C# preferito installato.  
- Aspose.Page per .NET. È possibile scaricarla [qui](https://releases.aspose.com/page/net/).  
- Familiarità con il formato di documento XPS.

## Importare gli spazi dei nomi

Per iniziare, includete gli spazi dei nomi necessari nel vostro progetto C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Come creare un documento XPS e aggiungere cloni di glifi

### Passo 1: Configurare la directory dei documenti

Iniziate configurando la directory in cui verranno archiviati i vostri documenti:

```csharp
string dataDir = "Your Document Directory";
```

### Passo 2: Creare il primo documento XPS

Ora, creiamo il primo documento XPS:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Passo 3: Aggiungere glifi al primo documento

Aggiungete glifi al primo documento usando i parametri specificati:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Passo 4: Riempire i glifi con un pennello a colore solido

Riempite i glifi nel primo documento con un **pennello a colore solido**, ad esempio verde:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Passo 5: Creare il secondo documento XPS

Ora, create il secondo documento XPS:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Passo 6: Come aggiungere un clone di glifo a un altro documento

Clonate i glifi dal primo documento e aggiungeteli al secondo documento:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Passo 7: Come cambiare il colore del glifo clonato

Cambiate il colore dei glifi clonati nel secondo documento, ad esempio, in rosso. Questo dimostra **come cambiare colore** di un glifo dopo il clonaggio:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Passo 8: Salvare il file XPS – Primo documento

Salvate il primo documento XPS nella cartella definita in precedenza:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Passo 9: Salvare il file XPS – Secondo documento

Salvate il secondo documento XPS:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Congratulazioni! Avete creato con successo file **documento XPS**, aggiunto cloni di glifi e cambiato i loro colori usando Aspose.Page per .NET.

## Perché utilizzare il clonaggio di glifi e il cambiamento di colore?

- **Riutilizzabilità:** Clonare glifi esistenti per riutilizzare forme vettoriali complesse senza ridefinirle.  
- **Prestazioni:** Riduce il tempo di elaborazione rispetto alla ricreazione dei glifi da zero.  
- **Flessibilità di design:** Applicare diverse istanze di `SolidColorBrush` allo stesso glifo per ottenere temi visivi vari.  
- **Modifica cross‑documento:** Clonare glifi tra più file XPS, consentendo un branding coerente nei report.

## Problemi comuni e risoluzione

| Problema | Soluzione |
|----------|-----------|
| **Il clone restituisce null** | Assicurarsi che il glifo di origine (`glyphs`) sia aggiunto al primo documento prima del clonaggio. |
| **Il colore non cambia** | Convertire (`cast`) `glyphs.Fill` a `XpsSolidColorBrush` prima di impostare la proprietà `Color` (come mostrato nel Passo 7). |
| **File non salvato** | Verificare che `dataDir` punti a una cartella valida e scrivibile e che si disponga delle autorizzazioni di file‑system appropriate. |
| **Dimensione del glifo inaspettata** | Regolare il parametro della dimensione del carattere (secondo argomento in `AddGlyphs`) per scalare il glifo in modo appropriato. |

## Domande frequenti

**Q1: Posso usare Aspose.Page per .NET con altri formati di documento?**  
A1: Aspose.Page per .NET è specificamente progettato per lavorare con documenti XPS. Se avete bisogno di manipolare altri formati, potete esplorare altre librerie Aspose specifiche per tali formati.

**Q2: È disponibile una licenza temporanea per Aspose.Page per .NET?**  
A2: Sì, è possibile ottenere una licenza temporanea per scopi di test. Visitate [qui](https://purchase.aspose.com/temporary-license/) per maggiori informazioni.

**Q3: Come posso ottenere supporto o assistenza per eventuali problemi?**  
A3: Sentitevi liberi di visitare il [forum Aspose.Page](https://forum.aspose.com/c/page/39) per entrare in contatto con la community e richiedere assistenza.

**Q4: Ci sono limitazioni nella versione di prova gratuita?**  
A4: La versione di prova gratuita presenta alcune limitazioni; è consigliabile consultare la documentazione per i dettagli prima dell'uso.

**Q5: Dove posso trovare una documentazione completa per Aspose.Page per .NET?**  
A5: Potete consultare la documentazione [qui](https://reference.aspose.com/page/net/) per informazioni dettagliate ed esempi.

**Q6: Come cambio il colore del tratto di un glifo invece del riempimento?**  
A6: Usate `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` per impostare un pennello di tratto.

**Q7: Posso aggiungere più cloni di glifi allo stesso documento?**  
A7: Sì, chiamate ripetutamente `doc2.Add(glyphs.Clone());`, regolando le posizioni secondo necessità.

---

**Ultimo aggiornamento:** 2026-01-07  
**Testato con:** Aspose.Page 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}