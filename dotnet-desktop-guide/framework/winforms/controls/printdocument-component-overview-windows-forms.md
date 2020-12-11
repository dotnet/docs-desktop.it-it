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
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="b331b-102">Cenni preliminari sul componente PrintDocument (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="b331b-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="b331b-103">Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="b331b-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="b331b-104">Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.</span><span class="sxs-lookup"><span data-stu-id="b331b-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="b331b-105">Utilizzo del componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="b331b-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="b331b-106">Due degli scenari principali che coinvolgono il <xref:System.Drawing.Printing.PrintDocument> componente sono:</span><span class="sxs-lookup"><span data-stu-id="b331b-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="b331b-107">Processi di stampa semplici, come la stampa di un singolo file di testo.</span><span class="sxs-lookup"><span data-stu-id="b331b-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="b331b-108">In tal caso, è necessario aggiungere il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="b331b-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="b331b-109">La logica di programmazione deve culminare con il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento.</span><span class="sxs-lookup"><span data-stu-id="b331b-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="b331b-110">Questo metodo invia <xref:System.Drawing.Graphics> alla stampante un oggetto, contenuto nella <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe.</span><span class="sxs-lookup"><span data-stu-id="b331b-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="b331b-111">Per un esempio in cui viene illustrato come stampare un documento di testo usando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare un file di testo con più pagine in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b331b-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="b331b-112">Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata.</span><span class="sxs-lookup"><span data-stu-id="b331b-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="b331b-113">In tal caso, è necessario derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [override](/dotnet/visual-basic/language-reference/modifiers/overrides) per Visual Basic o [override](/dotnet/csharp/language-reference/keywords/override) per C# <xref:System.Drawing.Printing.PrintDocument.PrintPage> ) evento.</span><span class="sxs-lookup"><span data-stu-id="b331b-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides) for Visual Basic or [override](/dotnet/csharp/language-reference/keywords/override) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="b331b-114">Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b331b-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="b331b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b331b-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="b331b-116">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b331b-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="b331b-117">Componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="b331b-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
