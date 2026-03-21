---
date: 2026-03-21
description: Μάθετε πώς να προσθέτετε κείμενο Unicode σε ένα έγγραφο XPS χρησιμοποιώντας
  το Aspose.Page για .NET. Αυτός ο οδηγός σας δείχνει πώς να δημιουργήσετε έγγραφο
  XPS με C# και να προσθέσετε κείμενο με συμβολοσειρές Unicode χρησιμοποιώντας το
  Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Πώς να προσθέσετε κείμενο Unicode σε έγγραφο XPS με το Aspose.Page
url: /el/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Unicode Κείμενο σε Έγγραφο XPS με το Aspose.Page

## Εισαγωγή

Αν χρειάζεστε **how to add unicode** χαρακτήρες σε ένα αρχείο XPS, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα προς βήμα τις ακριβείς ενέργειες που απαιτούνται για **create XPS document C#**‑style χρησιμοποιώντας το Aspose.Page για .NET και θα δείξουμε τη δυνατότητα **aspose page add text** με μια Unicode συμβολοσειρά. Στο τέλος θα έχετε ένα πλήρως λειτουργικό έγγραφο XPS που εμφανίζει σωστά κείμενο Unicode από δεξιά προς αριστερά (RTL).

## Γρήγορες Απαντήσεις
- **Τι καλύπτει το tutorial;** Προσθήκη Unicode κειμένου σε έγγραφο XPS με το Aspose.Page για .NET.  
- **Ποια γλώσσα χρησιμοποιείται;** C# (συμβατή με .NET Framework και .NET Core).  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να αλλάξω τη γραμματοσειρά ή το μέγεθος;** Ναι – το παράδειγμα χρησιμοποιεί Arial 20 pt, αλλά λειτουργεί οποιαδήποτε εγκατεστημένη γραμματοσειρά.  
- **Περιλαμβάνεται υποστήριξη RTL;** Ορίζοντας `BidiLevel = 1` ενεργοποιεί την απόδοση από δεξιά προς αριστερά για Unicode συμβολοσειρές.

## Τι είναι το “how to add unicode” στο XPS;

Η προσθήκη Unicode κειμένου σημαίνει εισαγωγή χαρακτήρων από οποιαδήποτε γλώσσα—Αραβικά, Εβραϊκά, Κινέζικα κ.λπ.—σε ένα έγγραφο XPS. Η κλάση `XpsGlyphs` του Aspose.Page διαχειρίζεται τη χαμηλού επιπέδου τοποθέτηση γλύφων, ενώ η ιδιότητα `BidiLevel` ελέγχει την κατεύθυνση του κειμένου για σενάρια RTL.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για προσθήκη κειμένου;

- **Πλήρης ενσωμάτωση .NET** – λειτουργεί με .NET Framework, .NET Core, .NET 5/6+.  
- **Χωρίς εξωτερικές εξαρτήσεις** – καθαρός διαχειριζόμενος κώδικας, χωρίς COM interop.  
- **Πλούσια υποστήριξη τυπογραφίας** – γραμματοσειρές, στυλ, χρώματα και διπλής κατεύθυνσης κείμενο.  
- **Υψηλή απόδοση** – δημιουργεί και αποθηκεύει αρχεία XPS γρήγορα, ιδανικό για δημιουργία στο διακομιστή.

## Προαπαιτούμενα

- Βασικές γνώσεις C# και ανάπτυξης .NET.  
- Visual Studio (οποιαδήποτε πρόσφατη έκδοση).  
- Βιβλιοθήκη Aspose.Page για .NET – κατεβάστε την από [here](https://releases.aspose.com/page/net/).

## Εισαγωγή Namespaces

Πρώτα, εισάγετε τα namespaces που σας δίνουν πρόσβαση στο μοντέλο XPS και στα βοηθητικά εργαλεία σχεδίασης.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Βήμα 1: Ρύθμιση του Εγγράφου – create XPS document C#

Δημιουργήστε ένα νέο έγγραφο XPS που θα φιλοξενήσει το Unicode κείμενο.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Βήμα 2: Προσθήκη Unicode Κειμένου – aspose page add text

Τώρα προσθέτουμε την πραγματική Unicode συμβολοσειρά. Σε αυτό το παράδειγμα χρησιμοποιούμε τη γραμματοσειρά Arial, μέγεθος 20, και τοποθετούμε το κείμενο στο (400 f, 200 f). Η `BidiLevel` ίση με 1 λέει στον renderer να αντιμετωπίσει τη συμβολοσειρά ως δεξιά‑προς‑αριστερά.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Βήμα 3: Αποθήκευση του Εγγράφου

Τέλος, αποθηκεύστε το αρχείο XPS στο δίσκο.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Συγχαρητήρια! Έχετε προσθέσει με επιτυχία **how to add unicode** κείμενο σε έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Το κείμενο εμφανίζεται παραμορφωμένο | Η γραμματοσειρά δεν υποστηρίζει το εύρος Unicode | Χρησιμοποιήστε μια γραμματοσειρά που περιέχει τα απαιτούμενα γλύφα (π.χ., Arial Unicode MS). |
| Το RTL κείμενο παραμένει αριστερό‑προς‑δεξί | Η `BidiLevel` δεν έχει οριστεί ή είναι 0 | Βεβαιωθείτε ότι `glyphs.BidiLevel = 1;` για σενάρια RTL. |
| Το αρχείο δεν αποθηκεύεται | Μη έγκυρη διαδρομή `dataDir` | Επαληθεύστε ότι ο φάκελος υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής. |

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.Page συμβατό με τα πιο πρόσφατα .NET frameworks;**  
A: Ναι, το Aspose.Page ενημερώνεται τακτικά για να υποστηρίζει .NET Framework, .NET Core και .NET 5/6+.

**Q: Μπορώ να προσαρμόσω το στυλ και το μέγεθος της γραμματοσειράς κατά την προσθήκη κειμένου;**  
A: Απολύτως! Η μέθοδος `AddGlyphs` σας επιτρέπει να καθορίσετε οποιαδήποτε οικογένεια γραμματοσειράς, μέγεθος και `FontStyle` χρειάζεστε.

**Q: Πού μπορώ να βρω επιπλέον τεκμηρίωση για το Aspose.Page;**  
A: Μπορείτε να ανατρέξετε στην τεκμηρίωση [here](https://reference.aspose.com/page/net/) για λεπτομερείς πληροφορίες API.

**Q: Υπάρχουν δωρεάν πόροι για να ξεκινήσω με το Aspose.Page;**  
A: Ναι, εξερευνήστε το φόρουμ κοινότητας στο [Aspose.Page forum](https://forum.aspose.com/c/page/39) για συμβουλές, παραδείγματα και υποστήριξη από άλλους χρήστες.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση πριν από την αγορά;**  
A: Φυσικά! Κατεβάστε τη δωρεάν δοκιμή από [here](https://releases.aspose.com/) για να αξιολογήσετε τη βιβλιοθήκη.

---

**Τελευταία Ενημέρωση:** 2026-03-21  
**Δοκιμάστηκε Με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}