---
date: 2026-07-10
description: 'Aspose Page .NET οδηγός: Μάθετε πώς να τροποποιείτε έγγραφα XPS χρησιμοποιώντας
  το Aspose.Page for .NET, συμπεριλαμβανομένης της προσθήκης κειμένου, υπογραφών και
  υδατογραφήματος με σαφή παραδείγματα κώδικα.'
keywords:
- aspose page .net tutorial
- modify xps document
- add text to xps
lastmod: 2026-07-10
linktitle: Τροποποίηση Εγγράφου XPS
og_description: Ο οδηγός Aspose Page .NET δείχνει πώς να τροποποιήσετε έγγραφα XPS,
  προσθέτοντας κείμενο και υπογραφές γρήγορα. Ακολουθήστε τον βήμα‑βήμα οδηγό για
  προγραμματιστές .NET.
og_image_alt: Guide to modify XPS document using Aspose.Page for .NET
og_title: 'Aspose.Page .NET Οδηγός: Τροποποίηση Εγγράφου XPS'
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: 'Aspose Page .NET tutorial: Learn how to modify XPS documents using
    Aspose.Page for .NET, including adding text, signatures, and watermarks with clear
    code examples.'
  headline: 'Aspose.Page .NET Tutorial: Modify XPS Document'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page is regularly updated to support .NET Framework 4.5+,
      .NET Core 3.1+, .NET 5, and .NET 6.
    question: Is Aspose.Page compatible with the latest .NET frameworks?
  - answer: Absolutely. Change the parameters of `AddGlyphs` (font name, size, `FontStyle`)
      to suit your design.
    question: Can I customize the font and style of the added text?
  - answer: Aspose.Page can handle documents larger than 200 MB and up to 500 pages
      without exhausting memory, thanks to its streaming architecture.
    question: Are there any size limits for XPS files?
  - answer: You can acquire a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How do I obtain a temporary license for Aspose.Page?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: Where can I seek help or connect with the Aspose community?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose page
- xps modification
- .net tutorial
title: 'Aspose.Page .NET Οδηγός: Τροποποίηση Εγγράφου XPS'
url: /el/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET Tutorial: Τροποποίηση εγγράφου XPS

## Εισαγωγή

Σε αυτό το **aspose page .net tutorial** θα ανακαλύψετε πώς να τροποποιήσετε ένα έγγραφο XPS προγραμματιστικά με το Aspose.Page for .NET. Είτε χρειάζεστε να εισάγετε μια υπογραφή, να προσθέσετε υδατογράφημα ή απλώς να τοποθετήσετε προσαρμοσμένο κείμενο σε μια σελίδα, θα περάσουμε από κάθε γραμμή κώδικα, θα εξηγήσουμε γιατί κάθε βήμα είναι σημαντικό και θα μοιραστούμε πρακτικές συμβουλές για να αποφύγετε κοινά προβλήματα. Στο τέλος θα μπορείτε να επεξεργάζεστε αρχεία XPS σε λίγα λεπτά, όχι ώρες.

### Γρήγορες Απαντήσεις
- **Τι καλύπτει αυτό το tutorial;** Προσθήκη κειμένου υπογραφής (“Confirmed”) σε επιλεγμένες σελίδες ενός αρχείου XPS.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for .NET (τελευταία έκδοση).  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10 λεπτά για μια βασική εισαγωγή υπογραφής.

## Τι είναι η τροποποίηση ενός εγγράφου XPS;

Η τροποποίηση ενός εγγράφου XPS περιλαμβάνει την προγραμματιστική αλλαγή του οπτικού του περιεχομένου—όπως η εισαγωγή κειμένου, εικόνων ή διανυσματικών σχημάτων—διατηρώντας τη φύση του σταθερού layout του αρχείου. Επειδή το XPS βασίζεται σε XML, οι αλλαγές εφαρμόζονται απευθείας στη δομή των σελίδων του εγγράφου χωρίς ανάγκη μετατροπής, επιτρέποντας ακριβή έλεγχο του layout, της τυπογραφίας και των γραφικών.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για την τροποποίηση εγγράφων XPS;

Το Aspose.Page προσφέρει ένα εγγενές .NET API που λειτουργεί σε πολλαπλές πλατφόρμες, εξαλείφει εξωτερικές εξαρτήσεις και προσφέρει υψηλή απόδοση για μεγάλα έγγραφα. Παρέχει στους προγραμματιστές πρόσβαση χαμηλού επιπέδου σε σελίδες, glyphs, brushes και transforms, καθιστώντας δυνατή την υλοποίηση προσαρμοσμένων υπογραφών, υδατογραφημάτων και σύνθετων γραφικών με λεπτομερή έλεγχο.

## Προαπαιτούμενα

- **Aspose.Page for .NET** – Εγκαταστήστε το πακέτο NuGet ή κατεβάστε τη βιβλιοθήκη από την επίσημη τεκμηρίωση **[here](https://reference.aspose.com/page/net/)**.  
- **Input XPS file** – Αποκτήστε ένα δείγμα εγγράφου XPS (π.χ., `input1.xps`) από τη **[Aspose releases page](https://releases.aspose.com/page/net/)**.  
- **Working directory** – Δημιουργήστε έναν φάκελο στον υπολογιστή σας για να αποθηκεύσετε τα αρχεία εισόδου και εξόδου και σημειώστε τη πλήρη διαδρομή του· θα αντιστοιχίσετε αυτή τη διαδρομή στη μεταβλητή `dir` στον κώδικα.  
- **Development environment** – Visual Studio 2019/2022, .NET Framework 4.7.2 ή νεότερη, ή οποιοδήποτε .NET Core/5/6 project.

Τώρα που όλα είναι έτοιμα, ας βουτήξουμε στον κώδικα.

## Πώς να εισάγετε ονομαστικούς χώρους (namespaces) για το Aspose.Page;

Για να εργαστείτε με το Aspose.Page πρέπει να εισάγετε τους ονομαστικούς του χώρους στην κορυφή του αρχείου C# σας. Αυτό δίνει στον μεταγλωττιστή πρόσβαση σε τύπους όπως `XpsDocument`, `Glyphs` και `SolidColorBrush`. Η κλάση `XpsDocument` αντιπροσωπεύει ένα αρχείο XPS και παρέχει πρόσβαση στις σελίδες και τους πόρους του.

```csharp
using Aspose.Page;
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using System.IO;
using System.Drawing;
```

Οι δηλώσεις `using` σας δίνουν άμεση πρόσβαση στο `XpsDocument`, `Glyphs` και άλλες βασικές κλάσεις.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Πώς να ανοίξετε ροή εγγράφου XPS;

Ανοίξτε το πηγαίο αρχείο XPS χρησιμοποιώντας ένα `FileStream` μόνο για ανάγνωση και περάστε το στον κατασκευαστή `XpsDocument`. Αυτό φορτώνει το αρχείο σε ένα αντικείμενο `XpsDocument`, το οποίο λειτουργεί ως σημείο εισόδου για όλες τις επόμενες τροποποιήσεις. Βεβαιωθείτε ότι η ροή είναι τυλιγμένη σε ένα μπλοκ `using` ώστε ο χειριστής του αρχείου να απελευθερώνεται αυτόματα.

```csharp
string inputPath = Path.Combine(dir, "input1.xps");
using (FileStream fs = new FileStream(inputPath, FileMode.Open, FileAccess.Read))
{
    XpsDocument document = new XpsDocument(fs);
    // All further operations use the 'document' variable.
}
```

**Definition anchor:** Η κλάση `XpsDocument` είναι το αντικείμενο κορυφαίου επιπέδου του Aspose.Page που ενσωματώνει ένα μόνο αρχείο XPS, εκθέτοντας σελίδες, πόρους και μεταδεδομένα για επεξεργασία.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Pro tip:* Τυλίξτε τη ροή σε ένα μπλοκ `using` για να διασφαλίσετε ότι ο χειριστής του αρχείου απελευθερώνεται αυτόματα.

## Πώς να δημιουργήσετε κείμενο υπογραφής σε XPS;

Δημιουργήστε ένα `SolidColorBrush` για να ορίσετε το χρώμα που θα γεμίζει το κείμενο της υπογραφής, στη συνέχεια προετοιμάστε τη συμβολοσειρά που θέλετε να αποδώσετε. Η κλάση `SolidColorBrush` παρέχει ομοιόμορφη γεμιστική χρωματική ενέργεια για λειτουργίες σχεδίασης όπως κείμενο ή σχήματα. Προσαρμόστε το χρώμα του πινέλου ώστε να ταιριάζει με το branding σας πριν προσθέσετε τα glyphs.

```csharp
SolidColorBrush brush = new SolidColorBrush(document, Color.BlueViolet);
string signature = "Confirmed";
```

**Definition anchor:** Το `SolidColorBrush` είναι ένα αντικείμενο σχεδίασης που γεμίζει σχήματα ή κείμενο με ένα ενιαίο, ομοιόμορφο χρώμα.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

## Πώς να ορίσετε σελίδες και να προσθέσετε τα glyphs της υπογραφής;

Επιλέξτε κάθε στόχο σελίδα με `SelectActivePage` και στη συνέχεια καλέστε `AddGlyphs` για να τοποθετήσετε το κείμενο υπογραφής στις επιθυμητές συντεταγμένες. Η μέθοδος `AddGlyphs` εισάγει μια ακολουθία χαρακτήρων στην ενεργή σελίδα χρησιμοποιώντας τη συγκεκριμένη γραμματοσειρά, μέγεθος, στυλ και πινέλο. Ρυθμίστε τις τιμές X και Y ώστε να τοποθετήσετε το κείμενο ακριβώς όπου χρειάζεται στο layout της σελίδας.

```csharp
int[] pages = { 1, 2, 3 };
foreach (int pageNumber in pages)
{
    XpsPage page = document.Pages[pageNumber - 1];
    page.SelectActivePage();
    page.AddGlyphs(100, 200, signature, "Arial", 24, FontStyle.Regular, brush);
}
```

**Definition anchor:** Η `AddGlyphs` εισάγει μια ακολουθία χαρακτήρων (glyphs) στην ενεργή σελίδα χρησιμοποιώντας τη δοθείσα γραμματοσειρά, μέγεθος, στυλ και πινέλο.

*Why these coordinates?* Οι τιμές X και Y μετρώνται σε points (1/72 inch). Προσαρμόστε τις ώστε να τοποθετήσετε το κείμενο ακριβώς εκεί που το χρειάζεστε στο layout της σελίδας.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

## Πώς να αποθηκεύσετε τις αλλαγές στο έγγραφο XPS;

Αφού προσθέσετε όλα τα επιθυμητά glyphs, καλέστε τη μέθοδο `Save` στο αντικείμενο `XpsDocument` για να γράψετε το τροποποιημένο περιεχόμενο σε νέο αρχείο. Η λειτουργία `Save` σειριοποιεί την εν-μνήμη αναπαράσταση του εγγράφου πίσω σε μορφή XPS, διατηρώντας όλες τις αλλαγές όπως το προστεθέν κείμενο ή γραφικά. Δώστε ένα διαφορετικό όνομα εξόδου ώστε να μην αντικαταστήσετε το αρχικό αρχείο.

```csharp
string outputPath = Path.Combine(dir, "input1_out.xps");
using (FileStream outFs = new FileStream(outputPath, FileMode.Create, FileAccess.Write))
{
    document.Save(outFs);
}
```

Το νέο αρχείο `input1_out.xps` περιέχει τώρα την υπογραφή “Confirmed” στις σελίδες 1‑3.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Signature not visible** | Λάθος συντεταγμένες ή η σελίδα δεν έχει επιλεγεί | Επαληθεύστε ότι καλείται το `SelectActivePage` για κάθε σελίδα και προσαρμόστε τις τιμές X/Y. |
| **Exception on `AddGlyphs`** | Η γραμματοσειρά δεν είναι εγκατεστημένη στον διακομιστή | Βεβαιωθείτε ότι η καθορισμένη γραμματοσειρά (π.χ., Arial) είναι διαθέσιμη, ή ενσωματώστε μια προσαρμοσμένη γραμματοσειρά χρησιμοποιώντας `document.AddFont`. |
| **Output file is corrupted** | Η ροή δεν κλείνει σωστά | Χρησιμοποιήστε δηλώσεις `using` για όλες τις ροές και καλέστε `document.Dispose()` εάν χρειάζεται. |
| **Performance slowdown on large files** | Φόρτωση ολόκληρου του εγγράφου στη μνήμη | Επεξεργαστείτε τις σελίδες σε παρτίδες ή χρησιμοποιήστε `XpsLoadOptions` με επιλογές streaming (αν είναι διαθέσιμες σε νεότερες εκδόσεις). |

## Συχνές Ερωτήσεις

**Q: Is Aspose.Page compatible with the latest .NET frameworks?**  
A: Ναι, το Aspose.Page ενημερώνεται τακτικά για να υποστηρίζει .NET Framework 4.5+, .NET Core 3.1+, .NET 5 και .NET 6.

**Q: Can I customize the font and style of the added text?**  
A: Απόλυτα. Αλλάξτε τις παραμέτρους του `AddGlyphs` (όνομα γραμματοσειράς, μέγεθος, `FontStyle`) ώστε να ταιριάζουν στο σχέδιό σας.

**Q: Are there any size limits for XPS files?**  
A: Το Aspose.Page μπορεί να διαχειριστεί έγγραφα μεγαλύτερα από 200 MB και έως 500 σελίδες χωρίς εξάντληση μνήμης, χάρη στην αρχιτεκτονική streaming.

**Q: How do I obtain a temporary license for Aspose.Page?**  
A: Μπορείτε να αποκτήσετε μια προσωρινή άδεια **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I seek help or connect with the Aspose community?**  
A: Επισκεφθείτε το **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** για να θέσετε ερωτήσεις και να μοιραστείτε εμπειρίες.

## Συμπέρασμα

Σε αυτό το **aspose page .net tutorial** δείξαμε πώς να **τροποποιήσετε έγγραφα XPS** προσθέτοντας προσαρμοσμένο κείμενο υπογραφής χρησιμοποιώντας το Aspose.Page for .NET. Τώρα έχετε μια σταθερή βάση για να εισάγετε οποιοδήποτε κείμενο, υδατογράφημα ή σημείωση σε συγκεκριμένες σελίδες ενός αρχείου XPS. Πειραματιστείτε με διαφορετικές γραμματοσειρές, χρώματα και θέσεις ώστε να ανταποκριθείτε στις απαιτήσεις branding της εφαρμογής σας, και εξερευνήστε το ευρύτερο API του Aspose.Page για προχωρημένες δυνατότητες γραφικών και layout.

---

**Τελευταία ενημέρωση:** 2026-07-10  
**Δοκιμή με:** Aspose.Page 24.11 for .NET (τελευταία έκδοση τη στιγμή της συγγραφής)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Προσθήκη κειμένου σε έγγραφο XPS με Aspose.Page for .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Προσθήκη εικόνας σε έγγραφο XPS με Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Δημιουργία εγγράφου XPS – Aspose.Page for .NET](/page/net/document-creation/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}