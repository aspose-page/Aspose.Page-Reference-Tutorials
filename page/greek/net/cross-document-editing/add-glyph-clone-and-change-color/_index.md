---
date: 2026-01-07
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS, να προσθέσετε κλώνα γλυφών,
  να χρησιμοποιήσετε πινέλο στερεού χρώματος και να αποθηκεύσετε το αρχείο XPS με
  το Aspose.Page για .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Δημιουργία εγγράφου XPS – Προσθήκη κλωνοποιημένου γλύφου & αλλαγή χρώματος
  με το Aspose.Page για .NET
url: /el/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εγγράφου XPS – Προσθήκη κλώνου Glyph & Αλλαγή χρώματος με Aspose.Page για .NET

## Introduction

Καλώς ήρθατε σε αυτόν τον οδηγό βήμα‑βήμα που σας δείχνει **πώς να δημιουργήσετε αρχεία XPS**, να κλωνοποιήσετε glyphs και να αλλάξετε τα χρώματά τους χρησιμοποιώντας το Aspose.Page για .NET. Είτε δημιουργείτε δυναμικές αναφορές, τιμολόγια ή προσαρμοσμένα γραφικά, η εξοικείωση με αυτές τις τεχνικές σας επιτρέπει να παράγετε οπτικά πλούσια έξοδο XPS χωρίς να αφήσετε το οικοσύστημα .NET.

## Quick Answers
- **Ποιος είναι ο κύριος στόχος;** Δημιουργία εγγράφου XPS, προσθήκη κλώνων glyph και αλλαγή των χρωμάτων τους.  
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.Page για .NET.  
- **Χρειάζεται άδεια;** Διατίθεται προσωρινή άδεια για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Πώς αποθηκεύεται το αποτέλεσμα;** Χρησιμοποιήστε τη μέθοδο `Save` για να γράψετε το αρχείο XPS στο δίσκο.

## Prerequisites

- Βασική κατανόηση της γλώσσας προγραμματισμού C#.  
- Εγκατεστημένο Visual Studio ή οποιοδήποτε άλλο προτιμώμενο περιβάλλον ανάπτυξης C#.  
- Βιβλιοθήκη Aspose.Page για .NET. Μπορείτε να την κατεβάσετε [εδώ](https://releases.aspose.com/page/net/).  
- Εξοικείωση με τη μορφή εγγράφου XPS.

## Import Namespaces

Για να ξεκινήσετε, συμπεριλάβετε τους απαραίτητους χώρους ονομάτων στο έργο C# σας:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

Ξεκινήστε δημιουργώντας τον κατάλογο όπου θα αποθηκευτούν τα έγγραφά σας:

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

Τώρα, ας δημιουργήσουμε το πρώτο έγγραφο XPS:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

Προσθέστε glyphs στο πρώτο έγγραφο χρησιμοποιώντας τις καθορισμένες παραμέτρους:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

Γεμίστε τα glyphs στο πρώτο έγγραφο με **πινέλο στερεού χρώματος**, για παράδειγμα, πράσινο:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

Τώρα, δημιουργήστε το δεύτερο έγγραφο XPS:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

Κλωνοποιήστε glyphs από το πρώτο έγγραφο και προσθέστε τα στο δεύτερο έγγραφο:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

Αλλάξτε το χρώμα των κλωνοποιημένων glyphs στο δεύτερο έγγραφο, για παράδειγμα, σε κόκκινο. Αυτό δείχνει **πώς να αλλάξετε το χρώμα** ενός glyph μετά την κλωνοποίηση:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

Αποθηκεύστε το πρώτο έγγραφο XPS στον φάκελο που ορίσατε νωρίτερα:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

Αποθηκεύστε το δεύτερο έγγραφο XPS:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Συγχαρητήρια! Έχετε δημιουργήσει επιτυχώς **αρχεία XPS**, προσθέσει κλώνους glyph και αλλάξει τα χρώματά τους χρησιμοποιώντας το Aspose.Page για .NET.

## Why Use Glyph Cloning and Color Changes?

- **Επαναχρησιμοποίηση:** Κλωνοποιήστε υπάρχοντα glyphs για να επαναχρησιμοποιήσετε σύνθετα διανυσματικά σχήματα χωρίς να τα ορίσετε ξανά.  
- **Απόδοση:** Μειώνει το χρόνο επεξεργασίας σε σύγκριση με τη δημιουργία glyphs από το μηδέν.  
- **Ευελιξία Σχεδίου:** Εφαρμόστε διαφορετικά στιγμιότυπα `SolidColorBrush` στο ίδιο glyph για να πετύχετε διαφορετικά οπτικά θέματα.  
- **Επεξεργασία μεταξύ εγγράφων:** Κλωνοποιήστε glyphs σε πολλαπλά αρχεία XPS, επιτρέποντας συνεπή επωνυμία σε αναφορές.

## Common Issues & Troubleshooting

| Πρόβλημα | Λύση |
|----------|------|
| **Clone returns null** | Βεβαιωθείτε ότι το glyph πηγής (`glyphs`) έχει προστεθεί στο πρώτο έγγραφο πριν την κλωνοποίηση. |
| **Color does not change** | Κάντε cast το `glyphs.Fill` σε `XpsSolidColorBrush` πριν ορίσετε την ιδιότητα `Color` (όπως φαίνεται στο Βήμα 7). |
| **File not saved** | Επαληθεύστε ότι το `dataDir` δείχνει σε έναν έγκυρο, εγγράψιμο φάκελο και ότι έχετε τις κατάλληλες άδειες συστήματος αρχείων. |
| **Unexpected glyph size** | Ρυθμίστε την παράμετρο μεγέθους γραμματοσειράς (δεύτερο όρισμα στο `AddGlyphs`) για να κλιμακώσετε το glyph αναλόγως. |

## Frequently Asked Questions

**Q1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές εγγράφων;**  
A1: Το Aspose.Page για .NET έχει σχεδιαστεί ειδικά για εργασία με έγγραφα XPS. Εάν χρειάζεστε επεξεργασία άλλων μορφών, μπορείτε να εξερευνήσετε άλλες βιβλιοθήκες Aspose προσαρμοσμένες για αυτές τις μορφές.

**Q2: Διατίθεται προσωρινή άδεια για το Aspose.Page για .NET;**  
A2: Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια για σκοπούς δοκιμής. Επισκεφθείτε [εδώ](https://purchase.aspose.com/temporary-license/) για περισσότερες πληροφορίες.

**Q3: Πώς μπορώ να λάβω υποστήριξη ή βοήθεια για τυχόν προβλήματα;**  
A3: Μπορείτε να επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να συνδεθείτε με την κοινότητα και να ζητήσετε βοήθεια.

**Q4: Υπάρχουν περιορισμοί στην δωρεάν έκδοση δοκιμής;**  
A4: Η δωρεάν έκδοση δοκιμής έχει ορισμένους περιορισμούς· συνιστάται να ελέγξετε την τεκμηρίωση για λεπτομέρειες πριν τη χρήση.

**Q5: Πού μπορώ να βρω πλήρη τεκμηρίωση για το Aspose.Page για .NET;**  
A5: Μπορείτε να ανατρέξετε στην τεκμηρίωση [εδώ](https://reference.aspose.com/page/net/) για λεπτομερείς πληροφορίες και παραδείγματα.

**Q6: Πώς αλλάζω το χρώμα περιγράμματος (stroke) ενός glyph αντί για το γέμισμα;**  
A6: Χρησιμοποιήστε `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` για να ορίσετε πινέλο περιγράμματος.

**Q7: Μπορώ να προσθέσω πολλαπλούς κλώνους glyph στο ίδιο έγγραφο;**  
A7: Ναι, καλέστε `doc2.Add(glyphs.Clone());` επανειλημμένα, προσαρμόζοντας τις θέσεις όπως χρειάζεται.

---

**Τελευταία ενημέρωση:** 2026-01-07  
**Δοκιμή με:** Aspose.Page 24.11 για .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}