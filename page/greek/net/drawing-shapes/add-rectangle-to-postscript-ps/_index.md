---
title: Προσθήκη Rectangle στο PostScript (PS) με το Aspose.Page για .NET
linktitle: Προσθήκη ορθογώνιου στο PostScript (PS)
second_title: Aspose.Page .NET API
description: Βελτιώστε τη δημιουργία εγγράφων στο .NET με το Aspose.Page. Μάθετε να προσθέτετε ορθογώνια σε αρχεία PostScript (PS) βήμα προς βήμα.
weight: 12
url: /el/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Rectangle στο PostScript (PS) με το Aspose.Page για .NET

## Εισαγωγή

Εάν θέλετε να βελτιώσετε τις δυνατότητες δημιουργίας εγγράφων σας στο .NET, το Aspose.Page παρέχει μια ισχυρή λύση για το χειρισμό εγγράφων PostScript. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης ορθογωνίων σε ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page για .NET.

## Προαπαιτούμενα

Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Page για .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Page για .NET από[εδώ](https://releases.aspose.com/page/net/).

- Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης .NET στον υπολογιστή σας.

## Εισαγωγή χώρων ονομάτων

Πριν ξεκινήσετε την κωδικοποίηση, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων για πρόσβαση στις απαιτούμενες κλάσεις και μεθόδους:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Τώρα, ας αναλύσουμε το παράδειγμα σε πολλά βήματα:

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων σας

```csharp
// ExStart: 1
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
```

Σε αυτό το βήμα, αντικαταστήστε το "Ο Κατάλογος Εγγράφων σας" με τη διαδρομή όπου θέλετε να αποθηκεύσετε το έγγραφο PostScript.

## Βήμα 2: Δημιουργία ροής εξόδου για έγγραφο PostScript

```csharp
//Δημιουργία ροής εξόδου για έγγραφο PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Εδώ, δημιουργούμε μια ροή εξόδου για το έγγραφο PostScript και καθορίζουμε το όνομα του αρχείου ("AddRectangle_outPS.ps"). Προσαρμόστε το όνομα και τη θέση του αρχείου σύμφωνα με τις προτιμήσεις σας.

## Βήμα 3: Ορίστε τις επιλογές αποθήκευσης και δημιουργήστε έγγραφο PS

```csharp
//Δημιουργήστε επιλογές αποθήκευσης με μέγεθος Α4
PsSaveOptions options = new PsSaveOptions();

// Δημιουργία νέου εγγράφου PS 1 σελίδας
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ορίστε τις επιλογές αποθήκευσης, καθορίζοντας το επιθυμητό μέγεθος σελίδας (Α4 σε αυτήν την περίπτωση). Στη συνέχεια, δημιουργήστε ένα νέο έγγραφο PostScript σε μία σελίδα.

## Βήμα 4: Προσθέστε ορθογώνιο και γεμίστε

```csharp
//Δημιουργήστε διαδρομή γραφικών από το πρώτο ορθογώνιο
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Σετ βαφής
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Συμπληρώστε το ορθογώνιο
document.Fill(path);
```

Εδώ, δημιουργούμε μια διαδρομή γραφικών που αντιπροσωπεύει το πρώτο ορθογώνιο, ορίζουμε το χρώμα βαφής (σε αυτήν την περίπτωση, πορτοκαλί) και γεμίζουμε το ορθογώνιο.

## Βήμα 5: Προσθέστε άλλο ένα ορθογώνιο και χτύπημα

```csharp
//Δημιουργήστε διαδρομή γραφικών από το δεύτερο ορθογώνιο
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Ορίστε εγκεφαλικό επεισόδιο
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Χαράξτε (περιγράψτε) το ορθογώνιο
document.Draw(path);
```

Παρόμοια με το προηγούμενο βήμα, δημιουργούμε μια διαδρομή γραφικών για το δεύτερο ορθογώνιο, ορίζουμε το χρώμα της διαδρομής (κόκκινο με πάχος 3) και σκιαγραφούμε το ορθογώνιο.

## Βήμα 6: Κλείστε τη σελίδα και αποθηκεύστε το έγγραφο

```csharp
//Κλείστε την τρέχουσα σελίδα
document.ClosePage();

//Αποθηκεύστε το έγγραφο
document.Save();
```

Τέλος, κλείστε την τρέχουσα σελίδα και αποθηκεύστε ολόκληρο το έγγραφο.

## συμπέρασμα

Συγχαρητήρια! Προσθέσατε με επιτυχία ορθογώνια σε ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page για .NET. Αυτό το σεμινάριο κάλυψε τα βασικά βήματα, από τη ρύθμιση του περιβάλλοντος ανάπτυξης έως την αποθήκευση του τελικού εγγράφου.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να προσαρμόσω τα χρώματα των ορθογωνίων;

A1: Ναι, μπορείτε να προσαρμόσετε τα χρώματα προσαρμόζοντας τις παραμέτρους στο`SolidBrush` και`Pen` τάξεις.

### Ε2: Είναι το Aspose.Page συμβατό με άλλες μορφές εγγράφων;

A2: Ναι, το Aspose.Page υποστηρίζει διάφορες μορφές εγγράφων, συμπεριλαμβανομένων των XPS και PostScript.

### Ε3: Πώς μπορώ να προσθέσω κείμενο στο έγγραφο;

 A3: Μπορείτε να χρησιμοποιήσετε το`TextFragment` κλάση στο Aspose.Page για να προσθέσετε κείμενο στο έγγραφό σας.

### Ε4: Πού μπορώ να βρω επιπλέον παραδείγματα και τεκμηρίωση;

 A4: Εξερευνήστε την τεκμηρίωση[εδώ](https://reference.aspose.com/page/net/) και επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτική υποστήριξη.

### Ε5: Μπορώ να δοκιμάσω το Aspose.Page πριν από την αγορά;

 A5: Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/) , και για εκτεταμένη χρήση, σκεφτείτε α[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
