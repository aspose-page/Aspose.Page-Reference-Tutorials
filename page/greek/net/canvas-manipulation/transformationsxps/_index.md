---
date: 2026-06-25
description: Μάθετε πώς να μετατρέπετε έγγραφα XPS χωρίς κόπο – ο ολοκληρωμένος οδηγός
  για το πώς να μετατρέψετε XPS χρησιμοποιώντας το Aspose.Page for .NET, με βήματα
  code‑free και real‑world tips.
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: Μετασχηματισμοί XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Πώς να μετατρέψετε XPS με το Aspose.Page for .NET
url: /el/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να μετασχηματίσετε XPS με το Aspose.Page για .NET

## Εισαγωγή

Σε αυτόν τον ολοκληρωμένο οδηγό θα μάθετε **πώς να μετασχηματίζετε XPS** έγγραφα χρησιμοποιώντας το Aspose.Page για .NET. Είτε χρειάζεστε μετατόπιση, κλιμάκωση, περιστροφή ή συνδυασμό πολλαπλών γραφικών σε μία σελίδα, η βιβλιοθήκη σας παρέχει έλεγχο βασισμένο σε πίνακες μετασχηματισμού χωρίς να χρειάζεται να εμβαθύνετε σε ακατέργαστο XML. Θα περάσουμε βήμα‑βήμα, θα εξηγήσουμε γιατί κάθε μετασχηματισμός είναι σημαντικός και θα μοιραστούμε πρακτικές συμβουλές που μπορείτε να αντιγράψετε απευθείας στον κώδικα παραγωγής.

## Γρήγορες Απαντήσεις
- **Τι μπορείτε να πετύχετε;** Δημιουργήστε, μετατοπίστε, κλιμακώστε και περιστρέψτε στοιχεία καμβά XPS προγραμματιστικά.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page για .NET (τελευταία έκδοση).  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Υποστηριζόμενες πλατφόρμες;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Χρόνος υλοποίησης;** Περίπου 10‑15 λεπτά για τις βασικές μετασχηματισμούς που παρουσιάζονται παρακάτω.

## Τι είναι το «πώς να μετασχηματίσετε xps»;
Η φράση *how to transform xps* περιγράφει την προγραμματιστική αλλαγή της διάταξης, του μεγέθους και του προσανατολισμού των στοιχείων μέσα σε ένα έγγραφο XPS (XML Paper Specification). Χρησιμοποιώντας το Aspose.Page, εφαρμόζετε μετασχηματισμούς βασισμένους σε πίνακες σε καμβάδες, παρέχοντάς σας ακριβή έλεγχο της τοποθέτησης, της κλιμάκωσης και της περιστροφής χωρίς να επεξεργάζεστε χειροκίνητα το markup του XPS.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για μετασχηματισμούς XPS;
Φορτώστε το αρχείο XPS, εφαρμόστε μια σειρά μετασχηματισμών και αποθηκεύστε – όλα σε δύο γραμμές κώδικα. Το Aspose.Page υποστηρίζει **50+ μορφές εισόδου και εξόδου**, μπορεί να επεξεργαστεί **αρχεία XPS 200‑σελίδων σε λιγότερο από 2 δευτερόλεπτα**, και δεν απαιτεί **εξωτερικές εξαρτήσεις**. Αυτό το καθιστά ιδανικό για τη δημιουργία τιμολογίων, αναφορών ή οποιωνδήποτε εκτυπώσιμων γραφικών επί τόπου.

## Προαπαιτούμενα

- **Βιβλιοθήκη Aspose.Page για .NET** – κατεβάστε την από την επίσημη τεκμηρίωση: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Περιβάλλον Ανάπτυξης** – Visual Studio, Visual Studio Code, Rider ή οποιοδήποτε IDE που στοχεύει στο .NET.  
- **Κατάλογος Εγγράφων** – ένας φάκελος στον υπολογιστή σας όπου θα διαβάζετε/γράφετε αρχεία XPS. Αντικαταστήστε το placeholder στον κώδικα με την πραγματική διαδρομή.

Τώρα που έχουμε όλα έτοιμα, ας βουτήξουμε στον κώδικα.

## Εισαγωγή Namespaces

Οι παρακάτω ονοματοχώροι εκθέτουν τους βασικούς τύπους Aspose.Page με τους οποίους θα εργαστείτε:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Πώς να Μετασχηματίσετε XPS Χρησιμοποιώντας το Aspose.Page;

Φορτώστε το πηγαίο XPS (ή ξεκινήστε με ένα νέο έγγραφο), στη συνέχεια εφαρμόστε μια ακολουθία μετασχηματισμών πίνακα—μετατόπιση, κλιμάκωση και περιστροφή—απευθείας σε αντικείμενα καμβά. Κάθε μετασχηματισμός εφαρμόζεται με τη σειρά που τον καλείτε, επιτρέποντάς σας να δημιουργήσετε σύνθετες διατάξεις με λίγες κλήσεις μεθόδων.

## Πώς να Μετασχηματίσετε XPS – Οδηγός Βήμα‑Βήμα

Σε αυτήν την ενότητα περπατάμε μέσα από ένα πλήρες παράδειγμα που δημιουργεί ένα αρχείο XPS, προσθέτει πολλούς καμβάδες και εφαρμόζει μια σειρά μετασχηματισμών όπως μετατόπιση, κλιμάκωση και περιστροφή. Κάθε βήμα περιλαμβάνει ένα σύντομο απόσπασμα κώδικα (αντιπροσωπευόμενο από placeholders) και εξηγεί γιατί εκτελείται η ενέργεια, ώστε να το αναπαράγετε εύκολα.

### Βήμα 1: Δημιουργία Νέου Εγγράφου XPS

`XpsDocument` είναι το αντικείμενο Aspose.Page που αντιπροσωπεύει ένα αρχείο XPS στη μνήμη.  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Επεξήγηση*: Ξεκινάμε ορίζοντας το φάκελο που περιέχει τα αρχεία πηγής και εξόδου, στη συνέχεια δημιουργούμε ένα κενό `XpsDocument`. Αυτό το αντικείμενο θα είναι ο καμβάς για όλους τους επόμενους μετασχηματισμούς.

### Βήμα 2: Δημιουργία Κύριου Καμβά

`Canvas` είναι η επιφάνεια σχεδίασης που ομαδοποιεί σχήματα, κείμενο και άλλα γραφικά στοιχεία.  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Γιατί είναι σημαντικό*: Ο κύριος καμβάς λειτουργεί ως κοντέινερ για όλους τους άλλους καμβάδες. Εφαρμόζοντας μια μικρή μετατόπιση εξασφαλίζουμε ότι το περιεχόμενο δεν θα κοπεί στην άκρη της σελίδας.

### Βήμα 3: Δημιουργία Γεωμετρίας Διαδρομής Ορθογωνίου

`PathGeometry` ορίζει διανυσματικά σχήματα χρησιμοποιώντας τη σύνταξη διαδρομής XPS (M = move, L = line, Z = close).  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Συμβουλή*: Η συμβολοσειρά διαδρομής ακολουθεί την τυπική σύνταξη διαδρομής XPS. Προσαρμόστε τις συντεταγμένες για να αλλάξετε το μέγεθος του ορθογωνίου.

### Βήμα 4: Προσθήκη Γέμισης για Ορθογώνια

`SolidColorBrush` δημιουργεί μια γεμιστική απόχρωση στερεού χρώματος που μπορεί να επαναχρησιμοποιηθεί σε πολλαπλά σχήματα.  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Επαγγελματική συμβουλή*: Χρησιμοποιήστε `CreateColor` με τιμές RGB για να ταιριάξετε την παλέτα της μάρκας σας.

### Βήμα 5: Προσθήκη Νέου Καμβά Χωρίς Μετασχηματισμούς

`Canvas` χωρίς μετασχηματισμό λειτουργεί ως στοιχείο βάσης για σύγκριση.  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Εδώ τοποθετούμε απλώς ένα ορθογώνιο στη σελίδα χωρίς επιπλέον μετασχηματισμό — χρήσιμο ως στοιχείο βάσης.

### Βήμα 6: Προσθήκη Νέου Καμβά με Μετατόπιση

`TranslateTransform` μετακινεί αντικείμενα κατά τους άξονες X και Y.  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Τι συμβαίνει;* Η πρώτη μήτρα μετακινεί το ορθογώνιο προς τα κάτω κατά 200 μονάδες. Η επόμενη κλήση `Translate` το μετακινεί 500 μονάδες προς τα δεξιά, δείχνοντας πώς μπορούν να αλυσιδωθούν πολλαπλές μετατοπίσεις.

### Βήμα 7: Προσθήκη Νέου Καμβά με Διπλή Κλιμάκωση

`ScaleTransform` πολλαπλασιάζει το πλάτος και το ύψος του καμβά με τους δοθέντες παράγοντες.  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Γιατί κλιμάκωση;* Η κλιμάκωση κατά 2 διπλασιάζει το πλάτος και το ύψος του ορθογωνίου, επιτρέποντάς σας να δημιουργήσετε μεγαλύτερα γραφικά χωρίς να επανακαθορίσετε τη γεωμετρία.

### Βήμα 8: Προσθήκη Νέου Καμβά με Περιστροφή γύρω από Σημείο

`RotateAroundTransform` περιστρέφει τον καμβά γύρω από ένα προσαρμοσμένο σημείο (εδώ (100, 50)).  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Κύρια παρατήρηση*: `RotateAround` περιστρέφει τον καμβά γύρω από ένα προσαρμοσμένο σημείο, δίνοντάς σας ακριβή έλεγχο των άξονων περιστροφής.

### Βήμα 9: Αποθήκευση Τελικού Εγγράφου XPS

`Save` αποθηκεύει το έγγραφο στη μνήμη στο δίσκο σε μορφή XPS.  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Μετά την εφαρμογή όλων των μετασχηματισμών, το έγγραφο αποθηκεύεται στο `output1.xps`. Ανοίξτε το αρχείο σε οποιονδήποτε προβολέα XPS για να δείτε τα στοίβαγμα ορθογωνίων με τις αντίστοιχες μετατοπίσεις, κλιμακώσεις και περιστροφές.

## Συχνά Προβλήματα & Επίλυση

| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|----------|--------------|----------|
| Κενό αρχείο εξόδου | `dataDir` δείχνει σε φάκελο που δεν υπάρχει | Βεβαιωθείτε ότι ο φάκελος υπάρχει ή χρησιμοποιήστε απόλυτη διαδρομή |
| Τα ορθογώνια δεν τοποθετούνται όπως αναμένεται | Λανθασμένες τιμές πίνακα | Ελέγξτε ξανά τη σειρά των κλήσεων `Translate`, `Scale` και `RotateAround` |
| Τα χρώματα εμφανίζονται λανθασμένα | Τιμές RGB εκτός εύρους 0‑255 | Χρησιμοποιήστε έγκυρες τιμές byte για κάθε κανάλι |

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.Page για .NET συμβατό με όλα τα περιβάλλοντα ανάπτυξης .NET;**  
Α: Ναι, λειτουργεί άψογα με Visual Studio, Visual Studio Code, Rider και οποιοδήποτε IDE που υποστηρίζει .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

**Ε: Πού μπορώ να βρω επιπλέον παραδείγματα και λεπτομερή τεκμηρίωση API;**  
Α: Επισκεφθείτε την επίσημη τεκμηρίωση στο [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Ε: Μπορώ να δοκιμάσω το Aspose.Page πριν αγοράσω άδεια;**  
Α: Απόλυτα. Μια δωρεάν δοκιμή είναι διαθέσιμη εδώ: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Ζητήστε την μέσω της σελίδας προσωρινής άδειας: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να αγοράσω πλήρη άδεια;**  
Α: Αγοράστε απευθείας από το κατάστημα Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

**Τελευταία Ενημέρωση:** 2026-06-25  
**Δοκιμή Με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Δημιουργία Εγγράφου XPS με Aspose.Page για .NET](/page/net/document-creation/create-xps-document/)
- [Πώς να Κόψετε XPS με Aspose.Page για .NET](/page/net/canvas-manipulation/clippingxps/)
- [Μετατροπή XPS σε PDF με Aspose.Page για .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}