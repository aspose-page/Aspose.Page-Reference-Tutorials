---
title: Προσθέστε το Circle Ellipse στο PostScript (PS) με το Aspose.Page
linktitle: Προσθήκη Circle Ellipse στο PostScript (PS)
second_title: Aspose.Page .NET API
description: Μάθετε πώς να προσθέτετε αβίαστα κυκλικές ελλείψεις σε έγγραφα PostScript (PS) χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτη ενσωμάτωση.
weight: 10
url: /el/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθέστε το Circle Ellipse στο PostScript (PS) με το Aspose.Page

## Εισαγωγή

Καλώς ήρθατε σε αυτό το ολοκληρωμένο σεμινάριο για την προσθήκη ελλείψεων κύκλων σε έγγραφα PostScript (PS) χρησιμοποιώντας το Aspose.Page για .NET. Το Aspose.Page είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με το PostScript και άλλες μορφές εγγράφων απρόσκοπτα. Σε αυτόν τον οδηγό, θα σας καθοδηγήσουμε στη διαδικασία ενσωμάτωσης κυκλικών ελλείψεων στα έγγραφά σας PS με ευκολία.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Page για .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Page για .NET από[εδώ](https://releases.aspose.com/page/net/).

2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα λειτουργικό περιβάλλον ανάπτυξης .NET στον υπολογιστή σας.

Τώρα, ας ξεκινήσουμε με τον οδηγό βήμα προς βήμα.

## Εισαγωγή χώρων ονομάτων

Στο πρώτο βήμα, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για να κάνετε τη λειτουργία Aspose.Page διαθέσιμη στον κώδικά σας.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Τώρα, ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα για να σας καθοδηγήσουμε στη διαδικασία προσθήκης ελλείψεων κύκλων σε ένα έγγραφο PostScript.

## Βήμα 1: Ορίστε τον Κατάλογο εγγράφων

```csharp
// ExStart: 1
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
```

Βεβαιωθείτε ότι έχετε αντικαταστήσει το "Ο Κατάλογος Εγγράφων σας" με την πραγματική διαδρομή προς τον κατάλογο των εγγράφων σας.

## Βήμα 2: Δημιουργία ροής εξόδου για έγγραφο PostScript

```csharp
//Δημιουργία ροής εξόδου για έγγραφο PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Εδώ, δημιουργείται ένα FileStream για τη σύνταξη του εγγράφου PostScript και η λειτουργία αρχείου έχει ρυθμιστεί για τη δημιουργία ενός νέου αρχείου.

## Βήμα 3: Δημιουργήστε Save Options και PS Document

```csharp
//Δημιουργήστε επιλογές αποθήκευσης με μέγεθος Α4
PsSaveOptions options = new PsSaveOptions();

// Δημιουργία νέου εγγράφου PS 1 σελίδας
PsDocument document = new PsDocument(outPsStream, options, false);
```

Αυτό το βήμα περιλαμβάνει τη δημιουργία επιλογών αποθήκευσης με μέγεθος A4 και την προετοιμασία ενός νέου εγγράφου PS 1 σελίδας.

## Βήμα 4: Δημιουργήστε διαδρομή γραφικών για την πρώτη έλλειψη

```csharp
//Δημιουργήστε διαδρομή γραφικών από την πρώτη έλλειψη
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Δημιουργείται μια διαδρομή γραφικών για την πρώτη έλλειψη, προσδιορίζοντας τη θέση και τις διαστάσεις της.

## Βήμα 5: Ρυθμίστε το Paint και γεμίστε το Ellipse

```csharp
//Σετ βαφής
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Γεμίστε την έλλειψη
document.Fill(path);
```

Εδώ, η βαφή έχει σταθεροποιηθεί και η πρώτη έλλειψη γεμίζει με το καθορισμένο χρώμα.

## Βήμα 6: Δημιουργήστε διαδρομή γραφικών για τη δεύτερη έλλειψη

```csharp
//Δημιουργήστε διαδρομή γραφικών από τη δεύτερη έλλειψη
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Ομοίως, δημιουργείται μια διαδρομή γραφικών για τη δεύτερη έλλειψη, που ορίζει τη θέση και τις διαστάσεις της.

## Βήμα 7: Ρυθμίστε το Stroke και σχεδιάστε την έλλειψη

```csharp
//Ορίστε εγκεφαλικό επεισόδιο
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Χτύπημα (περιγράμματα) της έλλειψης
document.Draw(path);
```

Σε αυτό το βήμα, ορίζεται η διαδρομή και η δεύτερη έλλειψη περιγράφεται με το καθορισμένο χρώμα και πάχος γραμμής.

## Βήμα 8: Κλείστε την τρέχουσα σελίδα και αποθηκεύστε το έγγραφο

```csharp
//Κλείστε την τρέχουσα σελίδα
document.ClosePage();

//Αποθηκεύστε το έγγραφο
document.Save();
```

Τέλος, η τρέχουσα σελίδα κλείνει και ολόκληρο το έγγραφο αποθηκεύεται, ολοκληρώνοντας τη διαδικασία.

## συμπέρασμα

Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να προσθέτετε ελλείψεις κύκλων σε έγγραφα PostScript χρησιμοποιώντας το Aspose.Page για .NET. Αυτό το σεμινάριο παρείχε έναν λεπτομερή, βήμα προς βήμα οδηγό για να σας βοηθήσει να ενσωματώσετε απρόσκοπτα αυτήν τη λειτουργία στα έργα σας.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές εγγράφων;

 A1: Το Aspose.Page εστιάζει κυρίως στο PostScript, αλλά το Aspose παρέχει άλλες βιβλιοθήκες για διάφορες μορφές εγγράφων. Ελεγξε το[Κατάθεση τεκμηρίωσης](https://reference.aspose.com/page/net/) Για περισσότερες πληροφορίες.

### Ε2: Πού μπορώ να βρω πρόσθετη υποστήριξη και συζητήσεις στην κοινότητα;

 A2: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για κοινοτικές συζητήσεις και υποστήριξη.

### Ε3: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page για .NET;

 A3: Ναι, μπορείτε να έχετε πρόσβαση στο[δωρεάν δοκιμή](https://releases.aspose.com/)για να εξερευνήσετε τις δυνατότητες του Aspose.Page για .NET.

### Ε4: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Page;

 A4: Λάβετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/) για σκοπούς δοκιμών και αξιολόγησης.

### Ε5: Πού μπορώ να αγοράσω το Aspose.Page για .NET;

 A5: Αγορά Aspose.Page για .NET από το[σελίδα αγοράς](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
