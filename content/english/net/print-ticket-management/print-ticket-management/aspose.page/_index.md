---
title: Edit Existing Print Ticket with Aspose.Page for .NET
linktitle: Edit Existing Print Ticket with Aspose.Page for .NET
second_title: Aspose.Page .NET API
description: 
type: docs
weight: 11
url: /net/print-ticket-management/print-ticket-management/aspose.page/
---

## Complete Source Code
```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;

namespace CSharp.WorkingWithPrintTickets
{
    public class EditPrintTicket
    {
        public static void Run()
        {
            // ExStart:1
            // The path to the documents directory.
            string dir = "Your Document Directory";

            // Open XPS Document with print tickets
            XpsDocument xDocs = new XpsDocument(dir + "input3.xps");

            JobPrintTicket pt = xDocs.JobPrintTicket;

            // Remove some parameters from job print ticket
            pt.Remove(
                "ns0000:PageDevmodeSnapshot",
                "ns0000:JobInterleaving",
                "ns0000:JobImageType");

            // Add some parameters to job print ticket
            pt.Add(
                new JobCopiesAllDocuments(2),
                new PageMediaSize(PageMediaSize.PageMediaSizeOption.ISOA4));

            // Save the document with changed job print ticket.
            xDocs.Save(dir + "output3.xps");

            // ExEnd:1
        }
    }
}

```
