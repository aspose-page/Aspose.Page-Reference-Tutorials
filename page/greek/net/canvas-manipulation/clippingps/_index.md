---
date: 2026-06-25
description: Μάθετε πώς να προσθέσετε clipping path στο PostScript χρησιμοποιώντας
  Aspose.Page για .NET – οδηγός βήμα‑βήμα με τεχνικές πινέλου και διακεκομμένου ορθογωνίου.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Clipping PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Πώς να προσθέσετε Clipping Path στο PostScript με Aspose.Page για .NET
url: /el/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Διαδρομή Κοπής σε PostScript με Aspose.Page για .NET

## Εισαγωγή

Σε αυτό το ολοκληρωμένο tutorial θα μάθετε **πώς να προσθέσετε διαδρομή κοπής** σε ένα έγγραφο PostScript (PS) χρησιμοποιώντας το Aspose.Page για .NET. Θα περάσουμε από κάθε βήμα, θα σας δείξουμε πώς να **ορίσετε πινέλο χρώματος**, και θα επιδείξουμε πώς να **σχεδιάσετε ένα διακεκομμένο ορθογώνιο** γύρω από το κομμένο περιεχόμενο. Στο τέλος θα έχετε ένα πλήρως λειτουργικό αρχείο PS που απεικονίζει την κοπή με σχήμα, δίνοντας στα γραφικά σας μια πιο δυναμική και επαγγελματική εμφάνιση.

## Γρήγορες Απαντήσεις
- **Τι κάνει η “προσθήκη διαδρομής κοπής”;** Περιορίζει τις λειτουργίες σχεδίασης σε ένα καθορισμένο σχήμα, κρύβοντας ό,τι βρίσκεται εκτός αυτού του σχήματος.  
- **Ποια βιβλιοθήκη διαχειρίζεται την κοπή στο .NET;** Το Aspose.Page για .NET παρέχει ένα πλούσιο API για τη διαχείριση PS/EPS.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να αλλάξω το χρώμα του πινέλου;** Ναι, χρησιμοποιήστε `SetPaint` με οποιοδήποτε `SolidBrush` ή διαβάθμιση προτιμάτε.  
- **Είναι δυνατόν να σχεδιάσω ένα διακεκομμένο ορθογώνιο;** Απόλυτα – δημιουργήστε ένα `Pen` με `DashStyle.Dash` και χρησιμοποιήστε `Draw`.  

## Τι είναι η διαδρομή κοπής σε PostScript;

Μια διαδρομή κοπής ορίζει την ορατή περιοχή των επόμενων εντολών σχεδίασης, απορρίπτοντας οτιδήποτε αποτυπώνεται εκτός των ορίων της. Σε πρακτικούς όρους, σας επιτρέπει να μάσκαρετε γραφικά ώστε να εμφανίζεται μόνο το τμήμα εντός της διαδρομής, κάτι που είναι απαραίτητο για τη δημιουργία σύνθετων συνθέσεων χωρίς να τροποποιείται μόνιμα το αρχικό αντικείμενο.

## Πώς να προσθέσετε διαδρομή κοπής σε έγγραφο PostScript με το Aspose.Page;

Φορτώστε ένα `PsDocument`, ορίστε μια διαδρομή γραφικών (π.χ., έναν κύκλο), εφαρμόστε `Clip()` για να περιορίσετε την περιοχή σχεδίασης, στη συνέχεια χρησιμοποιήστε `SetPaint` και `Fill` για να αποδώσετε το περιεχόμενο εντός της κομμένης περιοχής. Μετά την αποκατάσταση της κατάστασης γραφικών μπορείτε να σχεδιάσετε πρόσθετα σχήματα—όπως ένα διακεκομμένο ορθογώνιο—χωρίς να επηρεάσετε την κομμένη περιοχή. Αυτή η ακολουθία εκτελεί την κοπή με λίγες συνοπτικές κλήσεις API.

`PsDocument` αντιπροσωπεύει ένα αντικείμενο εγγράφου PostScript.  
`GraphicsPath` είναι ένας διανυσματικός κοντέινερ για γεωμετρικά σχήματα.  
`Clip()` ορίζει την περιοχή κοπής για τις επόμενες σχεδίες.  
`SetPaint` εκχωρεί ένα πινέλο που χρησιμοποιείται για το γέμισμα σχημάτων.  
`Fill` αποδίδει την τρέχουσα διαδρομή χρησιμοποιώντας το τρέχον χρώμα.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για κοπή;

Το Aspose.Page υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**, συμπεριλαμβανομένων των PS, EPS, PDF, SVG και τύπων εικόνας, και μπορεί να επεξεργαστεί έγγραφα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη δεν έχει **εξωτερικές εξαρτήσεις**, λειτουργεί σε **.NET Framework 4.5+**, **.NET Core 3.1+** και **.NET 6+**, και προσφέρει πλήρη έλεγχο της κατάστασης γραφικών (αποθήκευση/επαναφορά, μετατόπιση, περιστροφή). Αυτά τα ποσοτικοποιημένα οφέλη την καθιστούν αξιόπιστη επιλογή για δημιουργία γραφικών από τον διακομιστή.

## Προαπαιτούμενα

- Βασικές γνώσεις προγραμματισμού C#.  
- Η βιβλιοθήκη Aspose.Page για .NET εγκατεστημένη – μπορείτε να την κατεβάσετε [εδώ](https://releases.aspose.com/page/net/).  
- Visual Studio ή οποιοδήποτε προτιμώμενο .NET IDE.  

## Εισαγωγή Χώρων Ονομάτων

Οι παρακάτω χώροι ονομάτων σας δίνουν πρόσβαση στα βασικά αντικείμενα γραφικών και στις ειδικές επιλογές αποθήκευσης PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Τώρα ας αναλύσουμε το παράδειγμα σε σαφή, αριθμημένα βήματα.

### Βήμα 1: Ορισμός Καταλόγου Εγγράφου

Ορίστε το φάκελο όπου θα βρίσκονται τα αρχεία πηγής και εξόδου. Αυτό διευκολύνει την εύρεση του παραγόμενου αρχείου PS αργότερα.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Βήμα 2: Δημιουργία Ροής Εξόδου για Έγγραφο PostScript

Δημιουργήστε μια ροή εγγραφής που θα περιέχει το παραγόμενο αρχείο PS. Η χρήση ενός `FileStream` εξασφαλίζει ότι το αρχείο γράφεται απευθείας στο δίσκο.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Βήμα 3: Δημιουργία Επιλογών Αποθήκευσης

`PsSaveOptions` είναι το αντικείμενο διαμόρφωσης του Aspose.Page για έξοδο PS. Σας επιτρέπει να ελέγχετε τη συμπίεση, την έκδοση και άλλες λεπτομέρειες απόδοσης.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Βήμα 4: Δημιουργία Νέου 1‑Σελίδας PS Εγγράφου

`PsDocument` αντιπροσωπεύει ένα αντικείμενο εγγράφου PostScript. Το δημιουργείτε με τη ροή εξόδου και τις επιλογές αποθήκευσης που μόλις διαμορφώσατε.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Βήμα 5: Δημιουργία Διαδρομής Γραφικών από το Ορθογώνιο

`GraphicsPath` είναι ένας διανυσματικός κοντέινερ για γεωμετρικά σχήματα. Εδώ ξεκινάμε με ένα απλό ορθογώνιο που θα κοπεί αργότερα.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Βήμα 6: Κοπή με Σχήμα

Προσθέτουμε μια διαδρομή κοπής χρησιμοποιώντας έναν κύκλο, ορίζουμε το πινέλο χρώματος σε μπλε και γεμίζουμε το ορθογώνιο εντός της κομμένης περιοχής. Αυτό δείχνει πώς η κοπή περιορίζει τη σχεδίαση στο εσωτερικό του κύκλου.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Βήμα 7: Μετατόπιση Κατάστασης Γραφικών Άνω Επιπέδου & Σχεδίαση Διακεκομμένου Ορθογωνίου

Μετά την αποκατάσταση της προηγούμενης κατάστασης γραφικών, μετατοπίζουμε τον κέρσορα, δημιουργούμε ένα `Pen` με `DashStyle.Dash` και σχεδιάζουμε ένα διακεκομμένο ορθογώνιο γύρω από το κομμένο περιεχόμενο. Η μπλε γραμμή τονίζει το όριο της κοπής.

`Pen` ορίζει χαρακτηριστικά γραμμής όπως χρώμα και τύπο διακεκομμένης γραμμής.  
`DashStyle.Dash` καθορίζει ένα μοτίβο διακεκομμένης γραμμής.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Βήμα 8: Κλείσιμο και Αποθήκευση Εγγράφου

Ολοκληρώστε τη σελίδα, αδειάστε τη ροή και απελευθερώστε τους πόρους. Το αρχείο PS είναι τώρα γραμμένο στο δίσκο και έτοιμο για προβολή σε οποιονδήποτε προβολέα PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Τώρα έχετε προσθέσει με επιτυχία **διαδρομή κοπής**, ορίσει ένα προσαρμοσμένο πινέλο χρώματος και σχεδιάσει ένα διακεκομμένο ορθογώνιο γύρω από τα γραφικά σας χρησιμοποιώντας το Aspose.Page για .NET.

## Συχνά Προβλήματα και Λύσεις

- **Η κοπή δεν είναι ορατή:** Βεβαιωθείτε ότι καλείτε το `WriteGraphicsSave()` πριν τη μετατόπιση και το `WriteGraphicsRestore()` μετά το γέμισμα.  
- **Λάθος χρώματα:** Επαληθεύστε ότι το `SetPaint` καλείται μετά το `Clip` και πριν το `Fill`.  
- **Οι διακεκομμένες γραμμές εμφανίζονται στερεές:** Βεβαιωθείτε ότι το `DashStyle` του `Pen` είναι ορισμένο σε `DashStyle.Dash` πριν το `SetStroke`.  

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες γλώσσες προγραμματισμού;
Α: Το Aspose.Page σχεδιάστηκε κυρίως για εφαρμογές .NET, αλλά η Aspose προσφέρει ισοδύναμες βιβλιοθήκες για Java, C++ και άλλες πλατφόρμες.

### Ε2: Πού μπορώ να βρω επιπλέον παραδείγματα και τεκμηρίωση για το Aspose.Page για .NET;
Α: Μπορείτε να εξερευνήσετε περισσότερα παραδείγματα και λεπτομερή τεκμηρίωση στην [Aspose.Page documentation](https://reference.aspose.com/page/net/).

### Ε3: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Page για .NET;
Α: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page για .NET [εδώ](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page για .NET;
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Ε5: Πού μπορώ να λάβω υποστήριξη ή να συζητήσω ερωτήματα σχετικά με το Aspose.Page;
Α: Επισκεφθείτε τα [Aspose.Page forums](https://forum.aspose.com/c/page/39) για υποστήριξη κοινότητας και συζητήσεις.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Έγγραφο PostScript με Aspose.Page για .NET](/page/net/document-creation/create-postscript-document/)
- [Αποθήκευση αρχείου PostScript με Μετασχηματισμούς Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Δημιουργία εγγράφου postscript .net – Προσθήκη Ορθογωνίου με Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}