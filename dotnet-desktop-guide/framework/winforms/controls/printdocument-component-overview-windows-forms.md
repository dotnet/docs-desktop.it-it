---
title: Panoramica del componente PrintDocument
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96b18a44853d836cb0f16ba0e8372a825e998b74
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961456"
---
# <a name="printdocument-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDocument (Windows Form)

Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows. Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.

## <a name="working-with-the-printdocument-component"></a>Utilizzo del componente PrintDocument

Due degli scenari principali che coinvolgono il <xref:System.Drawing.Printing.PrintDocument> componente sono:

- Processi di stampa semplici, come la stampa di un singolo file di testo. In tal caso, è necessario aggiungere il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi. La logica di programmazione deve culminare con il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento. Questo metodo invia <xref:System.Drawing.Graphics> alla stampante un oggetto, contenuto nella <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe. Per un esempio in cui viene illustrato come stampare un documento di testo usando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare un file di testo con più pagine in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata. In tal caso, è necessario derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [override](/dotnet/visual-basic/language-reference/modifiers/overrides) per Visual Basic o [override](/dotnet/csharp/language-reference/keywords/override) per C# <xref:System.Drawing.Printing.PrintDocument.PrintPage> ) evento.

Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Form](../advanced/windows-forms-print-support.md)
- [Componente PrintDocument](printdocument-component-windows-forms.md)
