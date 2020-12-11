---
title: 'Procedura: Eseguire operazioni di trascinamento della selezione tra applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: 9aac3a0efd6359c25a6972f0e0b52dd489ec31db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962569"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="b6387-102">Procedura: Eseguire operazioni di trascinamento della selezione tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="b6387-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="b6387-103">Eseguire operazioni di trascinamento e rilascio tra applicazioni non è diverso dal consentire quest'azione nell'ambito di un'applicazione, purché entrambe le applicazioni implicate si comportino in base al "contratto" stabilito tra le proprietà <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> e <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6387-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="b6387-104">Nella procedura seguente si userà un'applicazione basata su Windows creata dall'utente e l'elaboratore di testi WordPad incluso con il sistema operativo Windows per eseguire operazioni di trascinamento della selezione tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b6387-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="b6387-105">WordPad offre un determinato set di effetti consentiti per il trascinamento del testo selezionato; l'applicazione basata su Windows per cui si scriverà il codice interagirà con tali effetti, in modo che le operazioni di trascinamento della selezione possano essere completate correttamente.</span><span class="sxs-lookup"><span data-stu-id="b6387-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="b6387-106">Per eseguire una procedura di trascinamento e rilascio tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="b6387-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1. <span data-ttu-id="b6387-107">Creare una nuova applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b6387-107">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="b6387-108">Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="b6387-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3. <span data-ttu-id="b6387-109">Configurare il controllo <xref:System.Windows.Forms.TextBox> per ricevere dati rilasciati.</span><span class="sxs-lookup"><span data-stu-id="b6387-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="b6387-110">Per altre informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento della selezione in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b6387-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4. <span data-ttu-id="b6387-111">Eseguire l'applicazione basata su Windows e, mentre l'applicazione è in esecuzione, eseguire WordPad.</span><span class="sxs-lookup"><span data-stu-id="b6387-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="b6387-112">WordPad è un editor di testo installato da Windows che consente operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="b6387-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="b6387-113">È accessibile premendo il pulsante **Start** , selezionando **Esegui** e digitando `WordPad` nella casella di testo della finestra di dialogo **Esegui** e facendo clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6387-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5. <span data-ttu-id="b6387-114">Una volta aperto WordPad, digitare una stringa di testo al suo interno.</span><span class="sxs-lookup"><span data-stu-id="b6387-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6. <span data-ttu-id="b6387-115">Usando il mouse, selezionare il testo e quindi trascinarlo sul controllo <xref:System.Windows.Forms.TextBox> nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="b6387-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="b6387-116">Notare che quando si passa il mouse sul controllo <xref:System.Windows.Forms.TextBox> (e, di conseguenza, si genera l'evento <xref:System.Windows.Forms.Control.DragEnter>), il cursore cambia ed è possibile rilasciare il testo selezionato sul controllo <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="b6387-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="b6387-117">È anche possibile configurare il controllo <xref:System.Windows.Forms.TextBox> per consentire il trascinamento delle stringhe di testo in WordPad.</span><span class="sxs-lookup"><span data-stu-id="b6387-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="b6387-118">Per altre informazioni, vedere [procedura dettagliata: esecuzione di un'operazione di trascinamento della selezione in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b6387-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6387-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6387-119">See also</span></span>

- [<span data-ttu-id="b6387-120">Procedura: Aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="b6387-120">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="b6387-121">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="b6387-121">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="b6387-122">Supporto delle operazioni di trascinamento della selezione e degli Appunti</span><span class="sxs-lookup"><span data-stu-id="b6387-122">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
