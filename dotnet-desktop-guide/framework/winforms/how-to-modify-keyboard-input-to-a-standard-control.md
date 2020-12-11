---
title: "Procedura: Modificare l'input da tastiera in un controllo standard"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 1aa22501eb3d15b30be4ea4918473cf5a48cfe94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965425"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="386ea-102">Procedura: Modificare l'input da tastiera in un controllo standard</span><span class="sxs-lookup"><span data-stu-id="386ea-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="386ea-103">Windows Forms permette di usare e modificare l'input da tastiera.</span><span class="sxs-lookup"><span data-stu-id="386ea-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="386ea-104">L'utilizzo di una chiave fa riferimento alla gestione di una chiave entro un metodo o un gestore eventi, in modo che altri metodi ed eventi successivi nella coda di messaggi non ricevano il valore della chiave.</span><span class="sxs-lookup"><span data-stu-id="386ea-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="386ea-105">Per modifica di una chiave si intente la modifica del valore di una chiave, in modo che i metodi e i gestori eventi successivi nella coda di messaggi ricevano un valore di chiave diverso.</span><span class="sxs-lookup"><span data-stu-id="386ea-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="386ea-106">Questo argomento illustra come completare queste attività.</span><span class="sxs-lookup"><span data-stu-id="386ea-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="386ea-107">Per usare una chiave</span><span class="sxs-lookup"><span data-stu-id="386ea-107">To consume a key</span></span>  
  
- <span data-ttu-id="386ea-108">In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> su `true`.</span><span class="sxs-lookup"><span data-stu-id="386ea-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="386ea-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="386ea-109">-or-</span></span>  
  
     <span data-ttu-id="386ea-110">In un gestore eventi <xref:System.Windows.Forms.Control.KeyDown> impostare la proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> della classe <xref:System.Windows.Forms.KeyEventArgs> su `true`.</span><span class="sxs-lookup"><span data-stu-id="386ea-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="386ea-111">L'impostazione della proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> nel gestore eventi <xref:System.Windows.Forms.Control.KeyDown> non impedisce la generazione degli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti attuale.</span><span class="sxs-lookup"><span data-stu-id="386ea-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="386ea-112">Usare la proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="386ea-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="386ea-113">L'esempio seguente è tratto da un'istruzione `switch` che esamina la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> dell'oggetto <xref:System.Windows.Forms.KeyPressEventArgs> ricevuto da un gestore eventi <xref:System.Windows.Forms.Control.KeyPress>.</span><span class="sxs-lookup"><span data-stu-id="386ea-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="386ea-114">Questo codice usa i tasti corrispondenti ai caratteri 'A' e 'a'.</span><span class="sxs-lookup"><span data-stu-id="386ea-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="386ea-115">Per modificare un tasto carattere standard</span><span class="sxs-lookup"><span data-stu-id="386ea-115">To modify a standard character key</span></span>  
  
- <span data-ttu-id="386ea-116">In un gestore eventi <xref:System.Windows.Forms.Control.KeyPress> impostare la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> della classe <xref:System.Windows.Forms.KeyPressEventArgs> sul valore del nuovo tasto carattere.</span><span class="sxs-lookup"><span data-stu-id="386ea-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="386ea-117">L'esempio seguente è tratto da un'istruzione `switch` che modifica 'B' in 'A' e 'b' in 'a'.</span><span class="sxs-lookup"><span data-stu-id="386ea-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="386ea-118">Si noti che la proprietà <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> del parametro <xref:System.Windows.Forms.KeyPressEventArgs> è impostata su `false`, in modo che il nuovo valore del tasto venga propagato ad altri metodi ed eventi nella coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="386ea-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="386ea-119">Per modificare un tasto non corrispondente a un carattere</span><span class="sxs-lookup"><span data-stu-id="386ea-119">To modify a noncharacter key</span></span>  
  
- <span data-ttu-id="386ea-120">Eseguire l'override di un metodo <xref:System.Windows.Forms.Control> che elabora messaggi di Windows, individuare il messaggio WM_KEYDOWN o WM_SYSKEYDOWN e impostare la proprietà <xref:System.Windows.Forms.Message.WParam%2A> del parametro <xref:System.Windows.Forms.Message> sul valore <xref:System.Windows.Forms.Keys> che rappresenta il nuovo tasto non corrispondente a un carattere.</span><span class="sxs-lookup"><span data-stu-id="386ea-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="386ea-121">L'esempio di codice seguente illustra come eseguire l'override del metodo <xref:System.Windows.Forms.Control.PreProcessMessage%2A> di un controllo per individuare i tasti da F1 a F9 e modificare la funzione del tasto F3 in quella del tasto F1.</span><span class="sxs-lookup"><span data-stu-id="386ea-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="386ea-122">Per altre informazioni sui <xref:System.Windows.Forms.Control> metodi di cui è possibile eseguire l'override per intercettare i messaggi della tastiera, vedere [input dell'utente in un'applicazione Windows Forms](user-input-in-a-windows-forms-application.md) e funzionamento dell' [input da tastiera](how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="386ea-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="386ea-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="386ea-123">Example</span></span>  
 <span data-ttu-id="386ea-124">L'esempio di codice seguente è l'applicazione completa degli esempi di codice delle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="386ea-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="386ea-125">L'applicazione usa un controllo personalizzato derivato dalla classe <xref:System.Windows.Forms.TextBox> per usare e modificare gli input da tastiera.</span><span class="sxs-lookup"><span data-stu-id="386ea-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="386ea-126">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="386ea-126">Compiling the Code</span></span>  
 <span data-ttu-id="386ea-127">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="386ea-127">This example requires:</span></span>  
  
- <span data-ttu-id="386ea-128">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="386ea-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386ea-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="386ea-129">See also</span></span>

- [<span data-ttu-id="386ea-130">Input da tastiera in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="386ea-130">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="386ea-131">Input dell'utente in un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="386ea-131">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="386ea-132">Funzionamento dell'input da tastiera</span><span class="sxs-lookup"><span data-stu-id="386ea-132">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)
