---
date: 2026-01-07
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS .NET χρησιμοποιώντας το Aspose.Page.
  Αυτός ο οδηγός δείχνει πώς να προσθέτετε γλύφους γεμάτους εικόνες και ξένες εικόνες
  για πιο πλούσια οπτικά στοιχεία του εγγράφου.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Δημιουργία εγγράφου XPS .NET με Aspose.Page – Γλύφη γεμάτη εικόνα & Ξένη εικόνα
url: /el/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία XPS document .NET με Aspose.Page – Image Filled Glyph & Foreign Image

## Εισαγωγή

Αν χρειάζεστε **create XPS document .NET** εφαρμογές που φαίνονται επαγγελματικές και άψογες, το Aspose.Page σας παρέχει τα εργαλεία για να ενσωματώσετε εικόνες απευθείας σε γλύφη και να επαναχρησιμοποιήσετε γραφικούς πόρους σε πολλά έγγραφα. Σε αυτό το tutorial θα σας καθοδηγήσουμε στη δημιουργία δύο αρχείων XPS, στη γέμιση των γλύφων με ένα image brush, και στη συνέχεια στην επαναχρήση αυτού του brush σε δεύτερο έγγραφο. Στο τέλος θα καταλάβετε γιατί αυτή η προσέγγιση εξοικονομεί μνήμη, απλοποιεί το styling, και ανοίγει δημιουργικές δυνατότητες για αναφορές, τιμολόγια ή οποιοδήποτε εκτυπώσιμο περιεχόμενο.

## Γρήγορες Απαντήσεις
- **What does this tutorial cover?** Προσθήκη image‑filled glyphs και επαναχρησιμοποίηση τους σε XPS documents με Aspose.Page for .NET.  
- **Which primary keyword is targeted?** `create xps document .net`.  
- **Prerequisites?** .NET development environment, Aspose.Page for .NET, και ένας φάκελος για τα XPS αρχεία σας.  
- **How long does implementation take?** Περίπου 10‑15 λεπτά για ένα λειτουργικό prototype.  
- **Can I use other image formats?** Ναι – οποιαδήποτε μορφή υποστηρίζεται από το .NET `System.Drawing.Image`.

## Προαπαιτούμενα

Πριν βουτήξετε στον κώδικα, βεβαιωθείτε ότι έχετε τα παρακάτω έτοιμα:

- **Aspose.Page for .NET** – κατεβάστε τη νεότερη βιβλιοθήκη από [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET 6+).  
- **Document Directory** – δημιουργήστε έναν φάκελο στον υπολογιστή σας που θα περιέχει τις εικόνες εισόδου και τα παραγόμενα XPS αρχεία· θα τον αναφέρουμε ως **Your Document Directory** στα αποσπάσματα.

## Εισαγωγή Namespaces

Ξεκινήστε φορτώνοντας τα namespaces που απαιτούνται για εργασία με XPS objects και drawing utilities.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Δημιουργία του πρώτου XPS Document

Ξεκινάμε δημιουργώντας ένα κενό XPS document που θα φιλοξενήσει το image‑filled glyph.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Βήμα 2: Προσθήκη Glyphs στο πρώτο Document

Στη συνέχεια, προσθέστε ένα glyph (έναν χαρακτήρα κειμένου) που θα γεμίσουμε αργότερα με ένα image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Βήμα 3: Γέμισμα Glyphs με ένα Image Brush

Εδώ δημιουργούμε ένα `ImageBrush` από ένα αρχείο TIFF που βρίσκεται στον data directory μας και το εφαρμόζουμε στο glyph. Το brush ορίζεται σε tile mode ώστε η εικόνα να επαναλαμβάνεται αν η περιοχή του glyph υπερβαίνει το μέγεθος της εικόνας.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Βήμα 4: Δημιουργία του δεύτερου XPS Document

Τώρα δημιουργούμε ένα δεύτερο XPS document που θα επαναχρησιμοποιήσει το στυλ του glyph και το image brush από το πρώτο.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Βήμα 5: Προσθήκη Glyphs με τη γραμματοσειρά από το πρώτο Document

Προσθέτουμε ένα glyph στο δεύτερο document, επαναχρησιμοποιώντας το ακριβές αντικείμενο γραμματοσειράς από το πρώτο document. Αυτό εξασφαλίζει οπτική συνέπεια μεταξύ των δύο αρχείων.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Βήμα 6: Δημιουργία Image Brush από το Fill του πρώτου Document

Αντί να φορτώσουμε ξανά την εικόνα, κλωνοποιούμε το brush από το `glyphs1` και το αναθέτουμε στο `glyphs2`. Αυτό δείχνει πώς μπορείτε να **create XPS document .NET** workflows που μοιράζονται πόρους αποδοτικά.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Βήμα 7: Αποθήκευση των Documents

Τέλος, αποθηκεύστε και τα δύο XPS αρχεία στο δίσκο. Μπορείτε τώρα να τα ανοίξετε με οποιονδήποτε XPS viewer για να δείτε το εφέ του image‑filled glyph.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Γιατί να χρησιμοποιήσετε image‑filled glyphs όταν δημιουργείτε XPS document .NET;

- **Visual Impact** – Μετατρέψτε απλό κείμενο σε στοιχεία πλούσια σε γραφικά χωρίς rasterizing ολόκληρης της σελίδας.  
- **Resource Reuse** – Μοιραστείτε brushes και γραμματοσειρές σε πολλά έγγραφα, μειώνοντας το αποτύπωμα μνήμης.  
- **Flexibility** – Tile, stretch ή rotate το image brush για να δημιουργήσετε προσαρμοσμένα patterns ή branding.

## Κοινά Προβλήματα & Συμβουλές

- **File Path Errors** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό διαδρομής (`\` ή `/`) κατάλληλο για το OS σας.  
- **Unsupported Image Formats** – Το Aspose.Page λειτουργεί καλύτερα με TIFF, PNG και JPEG. Μετατρέψτε άλλες μορφές πριν τη χρήση.  
- **TileMode Not Applied** – Επαληθεύστε ότι κάνετε cast σε `XpsImageBrush` πριν ορίσετε το `TileMode`; διαφορετικά η ιδιότητα αγνοείται.

## Συχνές Ερωτήσεις

### Q1: Μπορώ να χρησιμοποιήσω διαφορετικές μορφές εικόνας για το γέμισμα των glyphs;

**A:** Ναι, το Aspose.Page υποστηρίζει TIFF, PNG, JPEG, BMP και GIF. Απλώς δώστε τη σωστή επέκταση αρχείου στην κλήση `CreateImageBrush`.

### Q2: Πώς μπορώ να προσαρμόσω περαιτέρω την εμφάνιση των glyphs;

**A:** Εξερευνήστε πρόσθετες ιδιότητες του `XpsGlyphs` όπως `Opacity`, `RenderTransform` και `Stroke` για λεπτομερή ρύθμιση του rendering.

### Q3: Είναι το Aspose.Page κατάλληλο για διαχείριση μεγάλων συνόλων εγγράφων;

**A:** Απόλυτα. Η βιβλιοθήκη είναι βελτιστοποιημένη για σενάρια υψηλής απόδοσης και μπορεί να επεξεργαστεί χιλιάδες XPS αρχεία σε batch jobs.

### Q4: Μπορώ να εφαρμόσω διαφορετικά στυλ σε μεμονωμένα glyphs;

**A:** Ναι. Κάθε αντικείμενο `XpsGlyphs` μπορεί να έχει το δικό του fill, stroke και transformation, παρέχοντάς σας λεπτομερή έλεγχο.

### Q5: Ποια είναι τα οφέλη της χρήσης του Aspose.Page σε σχέση με άλλα εργαλεία επεξεργασίας εγγράφων;

**A:** Το Aspose.Page προσφέρει ένα πλήρες, χωρίς άδεια API για δημιουργία, επεξεργασία και μετατροπή XPS, με εκτενή τεκμηρίωση και υποστήριξη 24/7.

---

**Τελευταία ενημέρωση:** 2026-01-07  
**Δοκιμή με:** Aspose.Page 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}