---
title: Αλλαγή μεγέθους εικόνων EPS με το Aspose.Page για .NET
linktitle: Αλλαγή μεγέθους εικόνων EPS
second_title: Aspose.Page .NET API
description: Εξερευνήστε την απρόσκοπτη διαδικασία αλλαγής μεγέθους εικόνων EPS στο .NET χρησιμοποιώντας το Aspose.Page. Αποκτήστε ακρίβεια σε σημεία, ίντσες, χιλιοστά και ποσοστά χωρίς κόπο.
type: docs
weight: 11
url: /el/net/image-manipulation/resize-eps-images/
---
## Εισαγωγή

Θέλετε να αλλάξετε το μέγεθος των εικόνων EPS χωρίς προβλήματα χρησιμοποιώντας το Aspose.Page για .NET; Αυτό το σεμινάριο είναι ο περιεκτικός οδηγός σας για να χειριστείτε εύκολα το μέγεθος των εικόνων EPS σε διάφορες μονάδες, όπως σημεία, ίντσες, χιλιοστά και ποσοστά. Το Aspose.Page για .NET παρέχει ένα ισχυρό σύνολο εργαλείων και σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία βήμα προς βήμα.

## Προαπαιτούμενα

Πριν βουτήξετε στη μαγεία της αλλαγής μεγέθους, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Aspose.Page για .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/page/net/).

- Κατάλογος εγγράφων: Δημιουργήστε έναν κατάλογο όπου θα αποθηκεύετε το αρχείο εισόδου EPS και θα εξάγετε αρχεία με αλλαγή μεγέθους.

Τώρα που έχετε ρυθμίσει τα πάντα, ας προχωρήσουμε στην εισαγωγή των απαραίτητων χώρων ονομάτων και ας εμβαθύνουμε στον οδηγό βήμα προς βήμα.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας .NET, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων για να εργαστείτε με το Aspose.Page. Προσθέστε τον ακόλουθο κώδικα στην αρχή του αρχείου σας:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Βήμα 1: Αλλαγή μεγέθους σε πόντους

Ας ξεκινήσουμε αλλάζοντας το μέγεθος μιας εικόνας EPS σε σημεία. Οι πόντοι είναι μια τυπική μονάδα μέτρησης στη βιομηχανία εκτύπωσης.

```csharp
public static void ResizeInPoints()
{
    // Ο Κατάλογος Εγγράφων σας
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Βήμα 2: Αλλαγή μεγέθους σε ίντσες

Τώρα, ας αλλάξουμε το μέγεθος μιας εικόνας EPS σε ίντσες, μια κοινή μονάδα που χρησιμοποιείται στη γραφιστική.

```csharp
public static void ResizeInInches()
{
    // Ο Κατάλογος Εγγράφων σας
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Βήμα 3: Αλλαγή μεγέθους σε χιλιοστά

Τώρα, ας αλλάξουμε το μέγεθος μιας εικόνας EPS σε χιλιοστά, μια άλλη ευρέως χρησιμοποιούμενη μονάδα στο σχεδιασμό και την εκτύπωση.

```csharp
public static void ResizeInMillimeters()
{
    // Ο Κατάλογος Εγγράφων σας
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Βήμα 4: Αλλαγή μεγέθους σε ποσοστά

Τέλος, ας αλλάξουμε το μέγεθος μιας εικόνας EPS χρησιμοποιώντας ποσοστά, παρέχοντας μια ευέλικτη προσέγγιση για την προσαρμογή του μεγέθους της εικόνας.

```csharp
public static void ResizeInPercents()
{
    // Ο Κατάλογος Εγγράφων σας
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Μη διστάσετε να ενσωματώσετε αυτές τις μεθόδους στο έργο σας και θα αλλάξετε το μέγεθος των εικόνων EPS χωρίς κόπο. Πειραματιστείτε με διαφορετικές μονάδες για να επιτύχετε τις επιθυμητές διαστάσεις.

## συμπέρασμα

Συγχαρητήρια! Έχετε κατακτήσει την τέχνη της αλλαγής μεγέθους εικόνων EPS με το Aspose.Page για .NET. Αυτή η ισχυρή βιβλιοθήκη ανοίγει έναν κόσμο δυνατοτήτων για χειρισμό διανυσματικών γραφικών. Είτε σχεδιάζετε για έντυπα είτε για ψηφιακά μέσα, το Aspose.Page σάς δίνει τη δυνατότητα να επιτύχετε ακριβή και προσαρμοσμένα αποτελέσματα.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να αλλάξω το μέγεθος πολλών εικόνων EPS ταυτόχρονα;

A1: Ναι, μπορείτε να κάνετε κύκλο σε μια συλλογή αρχείων EPS, εφαρμόζοντας τις μεθόδους αλλαγής μεγέθους ανάλογα.

### Ε2: Είναι το Aspose.Page συμβατό με άλλες μορφές εικόνας;

A2: Το Aspose.Page εστιάζει κυρίως σε μορφές PostScript και EPS. Για άλλες μορφές εικόνας, εξετάστε το ενδεχόμενο να χρησιμοποιήσετε το Aspose.Imaging.

### Ε3: Υπάρχουν ζητήματα αδειοδότησης για εμπορικά έργα;

 A3: Ναι, βεβαιωθείτε ότι έχετε έγκυρη άδεια. Επίσκεψη[εδώ](https://purchase.aspose.com/buy) για λεπτομέρειες αδειοδότησης.

### Ε4: Μπορώ να δοκιμάσω το Aspose.Page πριν από την αγορά;

 Α4: Απολύτως! Μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).

### Ε5: Πού μπορώ να αναζητήσω πρόσθετη βοήθεια ή να συζητήσω θέματα;

 A5: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για να συνδεθείτε με την κοινότητα και να λάβετε βοήθεια.