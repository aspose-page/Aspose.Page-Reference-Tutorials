---
date: 2026-06-30
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS .NET και να προσθέσετε image‑filled
  glyphs ή foreign images χρησιμοποιώντας το Aspose.Page για .NET σε λίγα εύκολα βήματα.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Προσθήκη Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Δημιουργία εγγράφου XPS .NET – Προσθήκη Image Filled Glyph & Foreign Image
  με Aspose.Page
url: /el/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εγγράφου XPS .NET – Προσθήκη γλύφου γεμάτου με εικόνα & ξένης εικόνας με Aspose.Page

## Εισαγωγή

Στην ανάπτυξη .NET, οι εργασίες **create XPS document .NET** είναι συχνές όταν χρειάζεστε γραφικά υψηλής ποιότητας, ανεξάρτητα από την ανάλυση. Το Aspose.Page για .NET το καθιστά απλό και σας επιτρέπει να εμπλουτίσετε τα αρχεία XPS με γλύφους γεμάτους εικόνες ή να εισάγετε εικόνες από άλλο έγγραφο XPS. Στο τέλος αυτού του σεμιναρίου θα γνωρίζετε πώς να δημιουργήσετε δύο έγγραφα XPS, να γεμίσετε γλύφους με εικόνες και να επαναχρησιμοποιήσετε αυτές τις εικόνες σε πολλά έγγραφα — ιδανικό για τη δημιουργία τιμολογίων, πιστοποιητικών ή οποιασδήποτε οπτικά πλούσιας εξόδου.

## Γρήγορες Απαντήσεις
- **Τι υποστηρίζει το Aspose.Page;** Πάνω από 25 μορφές εικόνας και η δυνατότητα επεξεργασίας αρχείων XPS έως 500 MB χωρίς πλήρη φόρτωση στη μνήμη.  
- **Πόσες γραμμές κώδικα χρειάζονται για να προσθέσετε έναν γλύφο γεμάτο εικόνα;** Μόνο δύο γραμμές: δημιουργήστε ένα `ImageBrush` και το αναθέστε σε ένα `Glyph`.  
- **Χρειάζεται άδεια για παραγωγή;** Ναι, μια εμπορική άδεια αφαιρεί τα υδατογραφήματα αξιολόγησης.  
- **Ποιες εκδόσεις .NET είναι συμβατές;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Μπορώ να επαναχρησιμοποιήσω γραμματοσειρές από άλλο XPS;** Απόλυτα – μπορείτε να εισάγετε τη συλλογή γραμματοσειρών από το πρώτο έγγραφο στο δεύτερο.

## Πώς δημιουργείτε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page .NET;

Φορτώστε τη βιβλιοθήκη Aspose.Page, δημιουργήστε ένα `XpsDocument`, προσθέστε μια σελίδα και καλέστε `Save` – αυτή είναι η πλήρης ροή εργασίας σε τρεις σύντομες δηλώσεις. Το API διαχειρίζεται αυτόματα το μέγεθος της σελίδας, το DPI και τη διαχείριση πόρων, ώστε να μην χρειάζεται να διαχειρίζεστε δομές XPS χαμηλού επιπέδου μόνοι σας. Αυτή η προσέγγιση κλιμακώνεται από ένα φυλλάδιο μιας σελίδας έως καταλόγους εκατοντάδων σελίδων.

## Προαπαιτούμενα

- **Aspose.Page for .NET** – κατεβάστε το από [here](https://releases.aspose.com/page/net/).  
- **Ένα .NET IDE** – Visual Studio, Rider ή VS Code με την επέκταση C#.  
- **Ένας φάκελος για τα έγγραφά σας** – θα τον αναφέρουμε ως **Your Document Directory** στα αποσπάσματα κώδικα.

## Εισαγωγή ονοματοχώρων

Ο χώρος ονομάτων `Aspose.Page.XPS` παρέχει τις βασικές κλάσεις εγγράφου XPS, ενώ το `Aspose.Page.XPS.XpsModel` περιέχει στοιχεία μοντέλου όπως γλύφους και πινέλα. Εισάγετέ τα στην αρχή του αρχείου σας:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Τι είναι ένας γλύφος γεμάτος με εικόνα;

Ένας γλύφος είναι ένα διανυσματικό σχήμα που μπορεί να αποδοθεί με στερεό χρώμα, διαβάθμιση ή πινέλο εικόνας. Όταν εφαρμόζετε ένα `ImageBrush`, το εσωτερικό του γλύφου βαφτίζεται με την παρεχόμενη εικόνα, επιτρέποντας σύνθετα οπτικά εφέ χωρίς να ραστεροποιείται ολόκληρη η σελίδα.

## Βήμα 1: Δημιουργία του πρώτου εγγράφου XPS

`XpsDocument` αντιπροσωπεύει ένα πακέτο XPS και είναι το σημείο εισόδου για τη δημιουργία και αποθήκευση αρχείων XPS. Ξεκινήστε δημιουργώντας το πρώτο έγγραφο XPS που θα φιλοξενήσει τους γλύφους γεμάτους εικόνα.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Βήμα 2: Προσθήκη γλύφων στο πρώτο έγγραφο

`XpsGlyphs` ορίζει μια συλλογή γλύφων (χαρακτήρες κειμένου) που μπορούν να τοποθετηθούν σε μια σελίδα. Προσθέστε γλύφους στο πρώτο έγγραφο, καθορίζοντας τη γραμματοσειρά, το μέγεθος, το στυλ και τη θέση.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Βήμα 3: Γέμισμα γλύφων με πινέλο εικόνας

`ImageBrush` βαφτίζει μια περιοχή με εικόνα, επιτρέποντας μοτίβα ή φωτογραφίες να γεμίζουν σχήματα. Γεμίστε τους γλύφους με ένα πινέλο εικόνας, χρησιμοποιώντας μια εικόνα από τον φάκελο δεδομένων σας.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Βήμα 4: Δημιουργία του δεύτερου εγγράφου XPS

`XpsDocument` χρησιμοποιείται για τη δημιουργία ενός νέου αρχείου XPS που μπορεί να περιέχει σελίδες, πόρους και περιεχόμενο. Τώρα, δημιουργήστε το δεύτερο έγγραφο XPS που θα ενσωματώσει γλύφους από το πρώτο έγγραφο.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Βήμα 5: Προσθήκη γλύφων με τη γραμματοσειρά από το πρώτο έγγραφο

`Font` αντιπροσωπεύει μια γραμματοσειρά που χρησιμοποιείται για την απόδοση κειμένου σε ένα έγγραφο XPS. Προσθέστε γλύφους στο δεύτερο έγγραφο, χρησιμοποιώντας τη γραμματοσειρά που εξήχθη από το πρώτο έγγραφο. Με το μοίρασμα της συλλογής γραμματοσειρών, διατηρείτε το μέγεθος του αρχείου μικρό και εξασφαλίζετε οπτική συνέπεια.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Βήμα 6: Δημιουργία πινέλου εικόνας από το γέμισμα του πρώτου εγγράφου

`ImageBrush` μπορεί να δημιουργηθεί από ένα υπάρχον γέμισμα για να επαναχρησιμοποιηθεί η ίδια εικόνα σε πολλά έγγραφα. Δημιουργήστε ένα πινέλο εικόνας από το γέμισμα του πρώτου εγγράφου και χρησιμοποιήστε το για να γεμίσετε τους γλύφους στο δεύτερο έγγραφο. Αυτή η τεχνική «ξένης εικόνας» σας επιτρέπει να επαναχρησιμοποιήσετε γραφικά χωρίς να διπλασιάζετε το αρχείο προέλευσης.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Βήμα 7: Αποθήκευση των εγγράφων

`Save` γράφει το πακέτο XPS σε ένα αρχείο, ενσωματώνοντας όλους τους πόρους. Αποθηκεύστε τόσο το πρώτο όσο και το δεύτερο έγγραφο XPS στον φάκελο εξόδου. Η μέθοδος `Save` γράφει το πακέτο XPS, ενσωματώνοντας όλους τους πόρους και διατηρώντας τους γλύφους γεμάτους εικόνα.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| **Η εικόνα δεν εμφανίζεται μέσα στον γλύφο** | Το `ImageBrush` δημιουργήθηκε με λανθασμένο URI ή το μέγεθος της εικόνας υπερβαίνει τα όρια του γλύφου. | Επαληθεύστε τη διαδρομή της εικόνας και, προαιρετικά, ορίστε `ImageBrush.Stretch = Stretch.Uniform`. |
| **Οι γραμματοσειρές λείπουν στο δεύτερο έγγραφο** | Οι πόροι γραμματοσειρών δεν εξήχθησαν από το πρώτο XPS. | Χρησιμοποιήστε `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` πριν προσθέσετε γλύφους. |
| **Μείωση απόδοσης σε μεγάλα αρχεία** | Φόρτωση μεγάλων εικόνων στη μνήμη για κάθε γλύφο. | Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `ImageBrush` για όλους τους γλύφους ή μειώστε το μέγεθος της εικόνας πριν τη χρήση. |

## Συχνές Ερωτήσεις

### Q1: Μπορώ να χρησιμοποιήσω διαφορετικές μορφές εικόνας για το γέμισμα των γλύφων;

A1: Ναι, το Aspose.Page υποστηρίζει PNG, JPEG, BMP, GIF, TIFF, και άλλα—πάνω από 25 μορφές συνολικά.

### Q2: Πώς μπορώ να προσαρμόσω περαιτέρω την εμφάνιση των γλύφων;

A2: Εξερευνήστε ιδιότητες όπως `Glyph.Stroke`, `Glyph.FillOpacity`, και `Glyph.Transform` για να προσαρμόσετε τα περιγράμματα, τη διαφάνεια και την περιστροφή.

### Q3: Είναι το Aspose.Page κατάλληλο για τη διαχείριση μεγάλων συνόλων εγγράφων;

A3: Απόλυτα. Η βιβλιοθήκη επεξεργάζεται αρχεία XPS εκατοντάδων σελίδων χρησιμοποιώντας streaming, διατηρώντας τη χρήση μνήμης κάτω από 100 MB ακόμη και για έγγραφα 500 σελίδων.

### Q4: Μπορώ να εφαρμόσω διαφορετικά στυλ σε μεμονωμένους γλύφους;

A4: Ναι, κάθε αντικείμενο `Glyph` έχει τις δικές του ιδιότητες `Fill`, `Stroke` και `Transform`, επιτρέποντας στυλ ανά γλύφο.

### Q5: Ποια είναι τα οφέλη της χρήσης του Aspose.Page σε σχέση με άλλα εργαλεία XPS;

A5: Το Aspose.Page υποστηρίζει 25+ μορφές εικόνας, επεξεργάζεται αρχεία έως 500 MB χωρίς πλήρη φόρτωση μνήμης και παρέχει 100 % .NET‑native API—αφαιρώντας την ανάγκη για COM interop ή εξωτερικά εργαλεία.

**Τελευταία ενημέρωση:** 2026-06-30  
**Δοκιμάστηκε με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Σεμινάρια

- [Δημιουργία εγγράφου XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [Προσθήκη εικόνας σε έγγραφο XPS με Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Προσθήκη κλώνου γλύφου και αλλαγή χρώματος με Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}