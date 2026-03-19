---
date: 2026-03-19
description: Μάθετε πώς να προσθέσετε εισιτήριο δημιουργώντας προσαρμοσμένα εισιτήρια
  εκτύπωσης με το Aspose.Page για .NET. Προσαρμόστε την εμπειρία εκτύπωσής σας με
  λεπτομερή έλεγχο.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Πώς να προσθέσετε εισιτήριο: Δημιουργήστε προσαρμοσμένο εισιτήριο εκτύπωσης
  με το Aspose.Page για .NET'
url: /el/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Ticket: Create Custom Print Ticket with Aspose.Page for .NET

## Introduction

Αν χρειάζεστε λειτουργία **προσθήκης ticket** σε μια εφαρμογή .NET, το Aspose.Page σας δίνει τη δυνατότητα να δημιουργήσετε προσαρμοσμένα print tickets απευθείας από τον κώδικα. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα όλη τη διαδικασία — ρύθμιση του περιβάλλοντος, δημιουργία εγγράφου XPS, προσθήκη προσαρμοσμένου job print ticket και αποθήκευση του αποτελέσματος. Στο τέλος, θα μπορείτε να προσθέσετε υποστήριξη ticket σε οποιαδήποτε ροή εκτύπωσης με σιγουριά.

## Quick Answers
- **Τι σημαίνει “add ticket”;** Αναφέρεται στην ενσωμάτωση ενός προσαρμοσμένου print ticket (μεταδεδομένα XPS) που ελέγχει τις ρυθμίσεις του εκτυπωτή.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for .NET.  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.  
- **Μπορώ να το χρησιμοποιήσω με .NET Core;** Ναι, το Aspose.Page υποστηρίζει .NET Framework και .NET Core.  
- **Πόσο χρόνο παίρνει η υλοποίηση;** Συνήθως λιγότερο από 15 λεπτά για ένα βασικό ticket.

## What is a Custom Print Ticket?
Ένα προσαρμοσμένο print ticket είναι μια περιγραφή βασισμένη σε XML των προτιμήσεων του εκτυπωτή (όπως ταξινόμηση, αντίγραφα, διαχείριση χρώματος κ.λπ.) που ταξιδεύει μαζί με ένα έγγραφο XPS. Επιτρέπει στους προγραμματιστές να καθορίζουν προγραμματιστικά πώς πρέπει να εκτυπωθεί ένα έγγραφο, εξαλείφοντας τη χειροκίνητη διαμόρφωση από την πλευρά του πελάτη.

## Why add ticket support with Aspose.Page?
- **Λεπτομερής έλεγχος:** Ορίστε ταξινόμηση, αριθμό αντιγράφων, τύπο μέσου και άλλα από τον κώδικα.  
- **Συνεπής λειτουργία σε πολλαπλές πλατφόρμες:** Το ίδιο ticket λειτουργεί σε οποιονδήποτε εκτυπωτή που καταλαβαίνει τα μεταδεδομένα XPS.  
- **Απρόσκοπτη ενσωμάτωση:** Λειτουργεί απευθείας με τα υπάρχοντα .NET projects χωρίς πρόσθετες υπηρεσίες.

## Prerequisites

Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις C# και ανάπτυξης .NET.  
- Visual Studio (οποιαδήποτε πρόσφατη έκδοση) εγκατεστημένο.  
- Βιβλιοθήκη Aspose.Page for .NET προστιθέμενη στο project σας.  

Αν δεν έχετε προσθέσει ακόμη τη βιβλιοθήκη, μπορείτε να τη κατεβάσετε από την [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/). Για βοήθεια από την κοινότητα, επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Import Namespaces

Ξεκινήστε εισάγοντας τα namespaces που εκθέτουν τις κλάσεις XPS και metadata.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Τώρα ας αναλύσουμε την υλοποίηση βήμα‑βήμα.

## Step 1: Set up Document Directory

Ορίστε πού θα αποθηκευτεί το παραγόμενο αρχείο XPS.

```csharp
string dir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Δημιουργήστε ένα νέο έγγραφο XPS που θα περιέχει τις σελίδες και το ticket.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Step 3: Add Custom Job Print Ticket

Επισυνάψτε ένα προσαρμοσμένο job print ticket στο έγγραφο. Αυτό αποτελεί τον πυρήνα της λειτουργίας **προσθήκης ticket** — εδώ καθορίζετε ταξινόμηση, αντίγραφα, πρόθεση απόδοσης, διαχείριση χρώματος και οποιεσδήποτε άλλες ρυθμίσεις χρειάζεστε.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Συμβουλή:** Αντικαταστήστε τη συμβολοσειρά snapshot placeholder με μια κωδικοποιημένη Base64 δομή DEVMODE που ταιριάζει στις δυνατότητες του εκτυπωτή σας.

## Step 4: Save the Document

Αποθηκεύστε το έγγραφο XPS (με το ενσωματωμένο ticket) στο δίσκο.

```csharp
xDocs.Save(dir + "output1.xps");
```

Όταν ανοίξετε το *output1.xps* σε έναν προβολέα που σέβεται τα μεταδεδομένα XPS, ο εκτυπωτής θα εφαρμόσει αυτόματα τις ρυθμίσεις που ορίζονται στο ticket.

## Common Issues and Solutions

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Το ticket δεν εφαρμόζεται | Ο προβολέας αγνοεί τα μεταδεδομένα XPS | Χρησιμοποιήστε έναν οδηγό εκτυπωτή που υποστηρίζει XPS print tickets ή έναν προβολέα όπως το Microsoft XPS Viewer. |
| Μη έγκυρο Base64 snapshot | Κατεστραμμένα δεδομένα DEVMODE | Αναδημιουργήστε το snapshot από τον οδηγό εκτυπωτή χρησιμοποιώντας το API `GetPrinter`. |
| Έλλειψη δικαιωμάτων | Άρνηση πρόσβασης εγγραφής στο `dir` | Βεβαιωθείτε ότι η εφαρμογή εκτελείται με επαρκή δικαιώματα στο σύστημα αρχείων. |

## Frequently Asked Questions

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page for .NET με άλλα .NET frameworks;**  
Α: Ναι, το Aspose.Page λειτουργεί με .NET Framework, .NET Core, .NET 5/6 και νεότερες εκδόσεις.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page;**  
Α: Επισκεφθείτε [this link](https://purchase.aspose.com/temporary-license/) για να αποκτήσετε μια προσωρινή άδεια για το Aspose.Page.

**Ε: Υπάρχει φόρουμ κοινότητας για υποστήριξη του Aspose.Page;**  
Α: Φυσικά, μπορείτε να βρείτε χρήσιμες συζητήσεις και υποστήριξη στο [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Ε: Τι τύποι μέσων υποστηρίζονται σε προσαρμοσμένα print tickets;**  
Α: Το Aspose.Page υποστηρίζει μια σειρά τύπων μέσων, συμπεριλαμβανομένου απλού χαρτιού, γυαλιστερού και προσαρμοσμένων ορισμών μέσων.

**Ε: Υπάρχουν δείγματα έργων διαθέσιμα για το Aspose.Page for .NET;**  
Α: Εξερευνήστε την [documentation](https://reference.aspose.com/page/net/) για δείγματα έργων και αποσπάσματα κώδικα που θα σας βοηθήσουν να ξεκινήσετε την ανάπτυξη.

## Conclusion

Καλύψαμε πώς να προσθέσετε υποστήριξη **add ticket** σε ένα έγγραφο XPS χρησιμοποιώντας το Aspose.Page for .NET. Ακολουθώντας αυτά τα βήματα μπορείτε να ενσωματώσετε πλούσιες οδηγίες εκτύπωσης απευθείας στα αρχεία σας, αποκτώντας πλήρη έλεγχο της ροής εκτύπωσης από τις .NET εφαρμογές σας. Μη διστάσετε να πειραματιστείτε με επιπλέον ρυθμίσεις ticket για να ταιριάζουν στο συγκεκριμένο περιβάλλον εκτύπωσής σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Page for .NET (latest stable version)  
**Author:** Aspose  

---