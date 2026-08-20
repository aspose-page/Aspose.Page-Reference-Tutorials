---
date: 2026-03-21
description: Μάθετε πώς να συμπληρώνετε κείμενο και να προσθέτετε κείμενο σε έγγραφα
  PS χρησιμοποιώντας το Aspose.Page για .NET. Οδηγός βήμα‑βήμα με παραδείγματα κώδικα.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Πώς να γεμίσετε κείμενο σε έγγραφα PostScript (PS) με το Aspose.Page
url: /el/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Συμπληρώσετε Κείμενο σε Έγγραφα PostScript (PS) με το Aspose.Page

## Εισαγωγή

Αν χρειάζεστε **how to fill text** μέσα σε ένα αρχείο PostScript (PS), το Aspose.Page για .NET το καθιστά απλό. Είτε δημιουργείτε αναφορές, τιμολόγια ή προσαρμοσμένα γραφικά, η προσθήκη και η μορφοποίηση κειμένου είναι μια βασική απαίτηση. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — από τη ρύθμιση του περιβάλλοντος μέχρι την αποθήκευση του τελικού εγγράφου PS — ώστε να μπορείτε με σιγουριά να προσθέτετε κείμενο σε αρχεία PS στις .NET εφαρμογές σας.

## Γρήγορες Απαντήσεις
- **What does “fill text” mean?** Απεικονίζει χαρακτήρες χρησιμοποιώντας ένα συμπαγές πινέλο, ζωγραφίζοντας τα γλυφικά απευθείας στη σελίδα.  
- **Can I use custom fonts?** Ναι — το Aspose.Page υποστηρίζει προσαρμοσμένες γραμματοσειρές μέσω της δυνατότητας `add custom font ps`.  
- **How do I save the PS document?** Καλείτε `document.Save()` μετά το κλείσιμο της σελίδας· αυτό γράφει το αρχείο στο δίσκο (`save ps document`).  
- **Is “fill and stroke text” supported?** Απολύτως· χρησιμοποιήστε το `FillAndStrokeText` για να εφαρμόσετε τόσο το γέμισμα όσο και το περίγραμμα.  
- **What .NET versions are required?** Οποιαδήποτε έκδοση .NET Framework 4.5+ ή .NET Core/5/6+ runtime.

## Τι είναι το “how to fill text” σε ένα έγγραφο PS;

Το γέμισμα κειμένου σημαίνει τη βαφή των χαρακτήρων με ένα συμπαγές χρώμα (ή πινέλο) χωρίς περίγραμμα. Στο PostScript, αυτό είναι ανάλογο του τελεστή `fill`. Το Aspose.Page το αφαιρεί σε εύχρηστες μεθόδους όπως `FillText` και `FillAndStrokeText`.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για την προσθήκη custom font ps;

- **Full font support** – οι γραμματοσειρές του συστήματος και εξωτερικές TrueType/OpenType λειτουργούν αμέσως.  
- **Precise positioning** – ελέγχετε τις συντεταγμένες X/Y, το μέγεθος και το στυλ.  
- **Rich styling** – συνδυάστε γέμισμα, περίγραμμα και πένες για εφέ όπως “fill and stroke text”.  
- **Cross‑platform** – λειτουργεί σε Windows, Linux και macOS με το ίδιο API.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- **Aspose.Page for .NET** – κατεβάστε τη βιβλιοθήκη από την [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/).  
- **Document Directory** – ένας φάκελος στον υπολογιστή σας όπου θα βρίσκονται τα πηγαία και τα παραγόμενα αρχεία PS (αναφέρεται ως *Your Document Directory* στον κώδικα).  
- **Fonts Folder** – ένας υποφάκελος που περιέχει τυχόν προσαρμοσμένες γραμματοσειρές που σκοπεύετε να χρησιμοποιήσετε.

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τα απαιτούμενα namespaces ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις που θα χρησιμοποιήσουμε:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Δημιουργία Ροής Εξόδου για Έγγραφο PS  

Ανοίγουμε ένα `FileStream` που θα κρατήσει το παραγόμενο αρχείο PS, ρυθμίζουμε το `PsSaveOptions` ώστε να δείχνει στον φάκελο προσαρμοσμένων γραμματοσειρών, και δημιουργούμε ένα `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tip:** Διατηρήστε το μπλοκ `using` για να εξασφαλίσετε ότι η ροή κλείνει αυτόματα, κάτι που επίσης ολοκληρώνει το αρχείο PS (`save ps document`).

### Βήμα 2: Γέμισμα Κειμένου με Συστημική Γραμματοσειρά  

Εδώ δείχνουμε τη βασική λειτουργία **how to fill text** χρησιμοποιώντας την ενσωματωμένη γραμματοσειρά *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Βήμα 3: Γέμισμα Κειμένου με Προσαρμοσμένη Γραμματοσειρά  

Αν χρειάζεστε συγκεκριμένη εμφάνιση, φορτώστε μια προσαρμοσμένη γραμματοσειρά από το φάκελο γραμματοσειρών χρησιμοποιώντας το `ExternalFontCache.FetchDrFont`. Αυτό ικανοποιεί την απαίτηση **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Βήμα 4: Περίγραμμα (Stroke) Κειμένου με Συστημική Γραμματοσειρά  

Το περίγραμμα σχεδιάζει το περίγραμμα του γλύφου. Συνδυάστε το με γέμισμα για ένα εφέ “fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Why this matters:** Η κλήση `FillAndStrokeText` δείχνει πώς να **fill and stroke text** σε ένα μόνο βήμα, παρέχοντάς σας πιο πλούσιο τυπογραφικό έλεγχο.

### Βήμα 5: Περίγραμμα Κειμένου με Προσαρμοσμένη Γραμματοσειρά  

Η ίδια τεχνική περιγράμματος λειτουργεί με οποιαδήποτε προσαρμοσμένη γραμματοσειρά έχετε φορτώσει.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Βήμα 6: Κλείσιμο Σελίδας και Αποθήκευση Εγγράφου  

Η ολοκλήρωση είναι απλή: κλείστε την τρέχουσα σελίδα και καλέστε το `Save()` για να γράψετε το αρχείο PS στο δίσκο.

```csharp
document.ClosePage();
document.Save();
}
```

> **Result:** Θα βρείτε το `AddText_outPS.ps` στο *Your Document Directory*, περιέχοντας τόσο γεμιστό όσο και περιγραμμισμένο κείμενο που αποδίδεται με συστημικές και προσαρμοσμένες γραμματοσειρές.

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Λύση |
|-------|----------|
| **Custom font not found** | Βεβαιωθείτε ότι το αρχείο γραμματοσειράς (.ttf/.otf) υπάρχει στον φάκελο που αναφέρεται από το `AdditionalFontsFolders`. |
| **Text appears at wrong position** | Ρυθμίστε τις συντεταγμένες X/Y που περνιούνται στο `FillText`/`OutlineText`. Θυμηθείτε ότι το PostScript χρησιμοποιεί μονάδες σημείου (1/72 ίντσα). |
| **Colors look different** | Βεβαιωθείτε ότι χρησιμοποιείτε `SolidBrush` ή `Pen` με τις σωστές τιμές `Color`. |
| **Document not saving** | Επιβεβαιώστε ότι το μπλοκ `using` ολοκληρώνεται χωρίς εξαιρέσεις και ότι η εφαρμογή έχει δικαιώματα εγγραφής στον προορισμό. |

## Συχνές Ερωτήσεις

**Q: Can I use Aspose.Page with other .NET libraries?**  
A: Ναι, το Aspose.Page ενσωματώνεται ομαλά με άλλα .NET components, επιτρέποντάς σας να συνδυάσετε βιβλιοθήκες PDF, εικόνας ή γραφημάτων στην ίδια λύση.

**Q: Are custom fonts essential for this process?**  
A: Ενώ οι συστημικές γραμματοσειρές λειτουργούν καλά, οι προσαρμοσμένες γραμματοσειρές σας δίνουν πλήρη ελευθερία σχεδίασης και είναι χρήσιμες όταν απαιτείται τυπογραφία ειδική για το brand.

**Q: Is Aspose.Page suitable for large‑scale document processing?**  
A: Απολύτως. Η βιβλιοθήκη είναι βελτιστοποιημένη για σενάρια υψηλής απόδοσης και μπορεί να διαχειριστεί χιλιάδες αρχεία PS αποδοτικά.

**Q: Can I modify the position of the text in the PS document?**  
A: Φυσικά — απλώς αλλάξτε τις αριθμητικές τιμές X/Y στις κλήσεις `FillText` ή `OutlineText`.

**Q: Where can I seek assistance for Aspose.Page‑related queries?**  
A: Επισκεφθείτε το [Aspose.Page Forum](https://forum.aspose.com/c/page/39) για να συνδεθείτε με την κοινότητα και να λάβετε εξειδικευμένη βοήθεια.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-03-21  
**Δοκιμάστηκε Με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose