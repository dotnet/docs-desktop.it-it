---
title: 'Procedura: Creare un elenco di finestre di interfaccia a documenti multipli con MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961939"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="22b56-102">Procedura: creare un elenco di finestre MDI con MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="22b56-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="22b56-103">Usare l'interfaccia a documenti multipli (MDI) per creare applicazioni in grado di aprire diversi documenti contemporaneamente e copiare e incollare il contenuto da un documento all'altro.</span><span class="sxs-lookup"><span data-stu-id="22b56-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="22b56-104">Questa procedura illustra come creare un elenco di tutti i form figlio attivi nel menu della finestra del padre.</span><span class="sxs-lookup"><span data-stu-id="22b56-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="22b56-105">Per creare un elenco di finestre MDI in un MenuStrip</span><span class="sxs-lookup"><span data-stu-id="22b56-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="22b56-106">Creare un form e impostarne la proprietà <xref:System.Windows.Forms.Form.IsMdiContainer%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="22b56-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="22b56-107">Aggiungere un tipo <xref:System.Windows.Forms.MenuStrip> al form.</span><span class="sxs-lookup"><span data-stu-id="22b56-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="22b56-108">Aggiungere due voci di menu di primo livello a <xref:System.Windows.Forms.MenuStrip> e impostare le relative <xref:System.Windows.Forms.Control.Text%2A> proprietà su `&File` e `&Window` .</span><span class="sxs-lookup"><span data-stu-id="22b56-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="22b56-109">Aggiungere una voce del sottomenu alla voce di menu `&File` e impostare la relativa proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su `&Open`.</span><span class="sxs-lookup"><span data-stu-id="22b56-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="22b56-110">Impostare la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> proprietà di <xref:System.Windows.Forms.MenuStrip> su `&Window` <xref:System.Windows.Forms.ToolStripMenuItem> .</span><span class="sxs-lookup"><span data-stu-id="22b56-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="22b56-111">Aggiungere un modulo al progetto e aggiungere il controllo desiderato, ad esempio un altro <xref:System.Windows.Forms.MenuStrip> .</span><span class="sxs-lookup"><span data-stu-id="22b56-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="22b56-112">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="22b56-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="22b56-113">All'interno del gestore eventi, inserire codice simile al seguente per creare e visualizzare le nuove istanze di `Form2` come elementi figlio MDI di `Form1` .</span><span class="sxs-lookup"><span data-stu-id="22b56-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="22b56-114">Inserire il codice come il seguente in `&New` <xref:System.Windows.Forms.ToolStripMenuItem> per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="22b56-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22b56-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="22b56-115">Compiling the Code</span></span>  
 <span data-ttu-id="22b56-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22b56-116">This example requires:</span></span>  
  
- <span data-ttu-id="22b56-117">Due controlli <xref:System.Windows.Forms.Form> denominati `Form1` e `Form2`.</span><span class="sxs-lookup"><span data-stu-id="22b56-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="22b56-118">Un controllo <xref:System.Windows.Forms.MenuStrip> su `Form1` denominato `menuStrip1` e un controllo <xref:System.Windows.Forms.MenuStrip> su `Form2` denominato `menuStrip2`.</span><span class="sxs-lookup"><span data-stu-id="22b56-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="22b56-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22b56-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b56-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22b56-120">See also</span></span>

- [<span data-ttu-id="22b56-121">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="22b56-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="22b56-122">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="22b56-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="22b56-123">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="22b56-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
