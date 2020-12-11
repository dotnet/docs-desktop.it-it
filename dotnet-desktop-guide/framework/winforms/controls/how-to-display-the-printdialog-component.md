---
title: Come visualizzare il componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961843"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="4abb7-102">Come visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="4abb7-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="4abb7-103">Il <xref:System.Windows.Forms.PrintDialog> componente è la finestra di dialogo di stampa standard di Windows a cui molti utenti hanno familiarità.</span><span class="sxs-lookup"><span data-stu-id="4abb7-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="4abb7-104">Poiché gli utenti saranno immediatamente confortevoli, potrebbe essere utile utilizzare il <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="4abb7-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="4abb7-105">Per visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="4abb7-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="4abb7-106">Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo dall'interno del codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4abb7-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="4abb7-107">Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="4abb7-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="4abb7-108">Questi vengono salvati nella  <xref:System.Drawing.Printing.PrinterSettings> classe (e la <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede al [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) tramite il <xref:System.Windows.Forms.PrintDialog> componente) associato al processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="4abb7-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="4abb7-109">Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="4abb7-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="4abb7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4abb7-110">See also</span></span>

- [<span data-ttu-id="4abb7-111">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="4abb7-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="4abb7-112">Procedura: Acquisire l'input dell'utente da un componente PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4abb7-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="4abb7-113">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4abb7-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="4abb7-114">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="4abb7-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="4abb7-115">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4abb7-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="4abb7-116">Controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4abb7-116">Windows Forms Controls</span></span>](index.md)
