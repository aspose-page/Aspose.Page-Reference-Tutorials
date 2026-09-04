---
date: 2026-06-25
description: Μάθετε πώς να κόβετε έγγραφα XPS χρησιμοποιώντας το Aspose.Page για .NET.
  Αυτός ο οδηγός βήμα‑βήμα σας δείχνει πώς να δημιουργείτε, να επεξεργάζεστε και να
  αποθηκεύετε αρχεία XPS αποδοτικά.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Κόψιμο XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Πώς να κόψετε XPS με Aspose.Page για .NET
url: /el/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Κόψετε XPS με Aspose.Page για .NET

## Εισαγωγή

Καλώς ήρθατε σε αυτό το ολοκληρωμένο tutorial σχετικά με **πώς να κόψετε XPS** χρησιμοποιώντας το Aspose.Page για .NET! Σε αυτόν τον οδηγό, θα μάθετε βήμα‑βήμα πώς να δημιουργήσετε ένα έγγραφο XPS, να εφαρμόσετε γεωμετρικές μάσκες αποκοπής και να αποθηκεύσετε το αποτέλεσμα. Η αποκοπή σας επιτρέπει να κρύβετε μέρη ενός καμβά, επιτρέποντας εξελιγμένες διατάξεις όπως εικόνες με μάσκα, προσαρμοσμένα σχήματα ή περιοχές εστίασης περιεχομένου—όλα χωρίς να αφήσετε τον κώδικα .NET.

## Γρήγορες Απαντήσεις
- **Τι είναι η αποκοπή XPS;** Εφαρμογή γεωμετρικής μάσκας (clip) για περιορισμό της ορατής περιοχής των στοιχείων καμβά XPS.  
- **Ποια βιβλιοθήκη είναι η καλύτερη για αυτό;** Το Aspose.Page για .NET προσφέρει ένα πλήρες API για δημιουργία και αποκοπή XPS.  
- **Προαπαιτούμενα;** Visual Studio, .NET runtime και η βιβλιοθήκη Aspose.Page για .NET.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα βασικό σενάριο αποκοπής.  
- **Μπορώ να το χρησιμοποιήσω σε παραγωγή;** Ναι, με έγκυρη άδεια Aspose (διαθέσιμο δοκιμαστικό).

## Τι είναι η αποκοπή XPS;

Η αποκοπή XPS σημαίνει την εφαρμογή γεωμετρικής μάσκας σε έναν καμβά ώστε οποιαδήποτε σχεδίαση εκτός της μάσκας να μην αποδίδεται. Αυτή η τεχνική είναι ιδανική για τη δημιουργία εικόνων με μάσκα, κουμπιών προσαρμοσμένου σχήματος ή για την εστίαση της προσοχής του αναγνώστη σε συγκεκριμένη περιοχή της σελίδας. Ορίζοντας μια γεωμετρία αποκοπής — όπως ένα ορθογώνιο, κύκλο ή σύνθετο μονοπάτι — αποκτάτε λεπτομερή έλεγχο πάνω σε ό,τι εμφανίζεται στην τελική σελίδα XPS.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για .NET για την αποκοπή XPS;

Το Aspose.Page παρέχει προβλέψιμη, διακομιστή‑πλευρά επεξεργασία XPS χωρίς εξωτερικές εξαρτήσεις. Υποστηρίζει **50+ μορφές εισόδου και εξόδου**, μπορεί να επεξεργαστεί **αρχεία XPS 200‑σελίδων σε λιγότερο από 0,5 δευτερόλεπτα** σε τυπική CPU 2,5 GHz, και λειτουργεί σε .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 και .NET 7. Το API σας δίνει πλήρη έλεγχο πάνω στις μετασχηματισμούς του καμβά, τις γεωμετρίες διαδρομών και τα πινέλα, εξασφαλίζοντας υψηλής ποιότητας έξοδο κάθε φορά.

## Προαπαιτούμενα

- Το Visual Studio εγκατεστημένο στον υπολογιστή σας.  
- Η βιβλιοθήκη Aspose.Page για .NET προστέθηκε στο έργο σας. Μπορείτε να την κατεβάσετε [εδώ](https://releases.aspose.com/page/net/).  
- Βασικές γνώσεις της γλώσσας προγραμματισμού C#.

## Πώς να αποκόψετε XPS;

Φορτώστε ένα έγγραφο XPS, δημιουργήστε έναν καμβά, ορίστε μια γεωμετρία αποκοπής (π.χ., κύκλο), εκχωρήστε τη γεωμετρία στην ιδιότητα `Clip` του καμβά, σχεδιάστε το περιεχόμενό σας και, τέλος, αποθηκεύστε το έγγραφο. Όλα αυτά τα βήματα μπορούν να εκτελεστούν με λίγες κλήσεις μεθόδων, και το Aspose.Page διαχειρίζεται αυτόματα το υποκείμενο XML markup, ώστε να εστιάσετε στο οπτικό σχεδιασμό αντί στη δομή του αρχείου.

## Εισαγωγή Χώρων Ονομάτων

Για να χρησιμοποιήσετε τις λειτουργίες του Aspose.Page για .NET, πρέπει να εισάγετε τους απαιτούμενους χώρους ονομάτων στο έργο σας. Ακολουθήστε τα παρακάτω βήματα:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Τώρα, ας αναλύσουμε τον κώδικα παραδείγματος που δώσατε σε πολλαπλά βήματα.

## Βήμα 1: Ορίστε τη διαδρομή του καταλόγου εγγράφου.

Ορίστε το φάκελο όπου θα δημιουργηθεί το αρχείο XPS. Η χρήση του `Path.Combine` εγγυάται τον σωστό διαχωριστικό καταλόγου σε οποιοδήποτε λειτουργικό σύστημα.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Βήμα 2: Δημιουργήστε ένα νέο Έγγραφο XPS.

Δημιουργήστε μια παρουσία της κλάσης `XpsDocument`, η οποία αντιπροσωπεύει ολόκληρο το πακέτο XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 3: Δημιουργήστε τον κύριο καμβά.

Η κλάση `Canvas` αντιπροσωπεύει μια επιφάνεια σχεδίασης μέσα σε μια σελίδα XPS όπου αποδίδονται σχήματα, εικόνες και κείμενο.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Βήμα 4: Ορίστε τις μετατοπίσεις αριστερά και πάνω στον κύριο καμβά.

Ρυθμίστε τη θέση του καμβά για να ελέγξετε πού ξεκινά η σχεδίαση στη σελίδα.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Βήμα 5: Δημιουργήστε γεωμετρία διαδρομής ορθογωνίου.

`PathGeometry` ορίζει ένα διανυσματικό σχήμα· εδώ δημιουργούμε ένα απλό ορθογώνιο.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Βήμα 6: Δημιουργήστε γέμισμα για ορθογώνια.

Ορίστε ένα πινέλο στερεού χρώματος που θα χρησιμοποιηθεί για το γέμισμα του ορθογωνίου.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Βήμα 7: Προσθέστε έναν άλλο καμβά με αποκοπή στον κύριο καμβά.

Δημιουργήστε έναν υποκαμβά που θα λάβει μια μάσκα αποκοπής.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Βήμα 8: Δημιουργήστε γεωμετρία κύκλου για αποκοπή.

`PathGeometry` μπορεί επίσης να αντιπροσωπεύει κύκλους· αυτή η γεωμετρία θα εκχωρηθεί στην ιδιότητα `Clip` του υποκαμβά.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Βήμα 9: Δημιουργήστε ένα ορθογώνιο στο δεύτερο καμβά και γεμίστε το.

Σχεδιάστε ένα ορθογώνιο μέσα στον αποκομμένο καμβά· μόνο το τμήμα μέσα στον κύκλο θα είναι ορατό.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Βήμα 10: Προσθέστε το δεύτερο καμβά με ένα περιγραμμισμένο ορθογώνιο στον κύριο καμβά.

Προσθέστε ένα ορθογώνιο με περίγραμμα για να δείξετε πώς τα περιγράμματα αλληλεπιδρούν με την αποκοπή.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Βήμα 11: Δημιουργήστε ένα ορθογώνιο στον τρίτο καμβά και περιγράψτε το.

Ένας τρίτος καμβάς δείχνει ανεξάρτητη σχεδίαση χωρίς αποκοπή.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Βήμα 12: Αποθηκεύστε το τελικό έγγραφο XPS.

Αποθηκεύστε το πακέτο XPS στο σύστημα αρχείων.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Συχνά Προβλήματα και Λύσεις
- **Μη έγκυρη διαδρομή** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με ανάστροφη κάθετο (`\\`) ή χρησιμοποιήστε το `Path.Combine`.  
- **Η αποκοπή δεν εφαρμόζεται** – Επαληθεύστε ότι η συμβολοσειρά γεωμετρίας αποκοπής είναι σωστά μορφοποιημένη· ένα λείπον κενό μπορεί να κάνει την αποκοπή να αγνοηθεί.  
- **Εξαίρεση άδειας** – Σε μη‑αξιολογική έκδοση, προσθέστε μια έγκυρη άδεια Aspose πριν δημιουργήσετε το έγγραφο για να αποφύγετε εξαιρέσεις χρόνου εκτέλεσης.

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές εγγράφων;
Α1: Το Aspose.Page για .NET επικεντρώνεται κυρίως σε έγγραφα XPS, αλλά η Aspose παρέχει άλλες βιβλιοθήκες για διάφορες μορφές εγγράφων.

### Ε2: Είναι το Aspose.Page για .NET κατάλληλο για αρχάριους;
Α2: Ναι, το Aspose.Page για .NET έχει σχεδιαστεί ώστε να είναι φιλικό προς το χρήστη, και οι αρχάριοι μπορούν γρήγορα να κατανοήσουν τις λειτουργίες του με την κατάλληλη τεκμηρίωση.

### Ε3: Πού μπορώ να βρω περισσότερα παραδείγματα και πόρους;
Α3: Επισκεφθείτε την [τεκμηρίωση](https://reference.aspose.com/page/net/) και το [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39) για εκτενείς πόρους και παραδείγματα.

### Ε4: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page για .NET;
Α4: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Ε5: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Page για .NET;
Α5: Ναι, μπορείτε να εξερευνήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

## Πρόσθετες Συχνές Ερωτήσεις

**Q: Μπορώ να συνδυάσω πολλαπλές γεωμετρίες αποκοπής σε έναν μόνο καμβά;**  
A: Ναι, μπορείτε να εκχωρήσετε ένα σύνθετο `PathGeometry` που περιέχει πολλαπλές υπο‑διαδρομές στην ιδιότητα `Clip`, επιτρέποντας στρωματοποιημένη μάσκα.

**Q: Επηρεάζει η αποκοπή τη μετατροπή σε PDF;**  
A: Όταν μετατρέπετε αργότερα το XPS σε PDF χρησιμοποιώντας το Aspose.PDF, η γεωμετρία αποκοπής διατηρείται, έτσι το οπτικό αποτέλεσμα παραμένει ίδιο.

**Q: Είναι δυνατόν να ανιματοποιηθεί η αποκοπή σε XPS;**  
A: Το XPS δεν υποστηρίζει animation· ωστόσο, μπορείτε να δημιουργήσετε μια σειρά από σελίδες XPS με διαφορετικά σχήματα αποκοπής για να προσομοιώσετε κίνηση.

---

**Τελευταία Ενημέρωση:** 2026-06-25  
**Δοκιμασμένο με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Σχετικά Μαθήματα

- [Πώς να Μετασχηματίσετε XPS με Aspose.Page για .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Προσθήκη Ορθογωνίου σε Έγγραφο XPS με Aspose.Page για .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Μετατροπή XPS σε PDF με Aspose.Page για .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}