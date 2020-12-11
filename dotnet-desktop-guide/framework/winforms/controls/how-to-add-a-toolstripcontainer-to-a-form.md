---
title: 'Procedura: Aggiungere un oggetto ToolStripContainer a un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96950923"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="ff69d-102">Procedura: Aggiungere un oggetto ToolStripContainer a un modulo</span><span class="sxs-lookup"><span data-stu-id="ff69d-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="ff69d-103">È possibile aggiungere un oggetto <xref:System.Windows.Forms.ToolStripContainer> a un Windows Form a livello di codice e quindi popolarlo con controlli.</span><span class="sxs-lookup"><span data-stu-id="ff69d-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff69d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff69d-104">Example</span></span>  
 <span data-ttu-id="ff69d-105">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un controllo <xref:System.Windows.Forms.ToolStripContainer> e un controllo <xref:System.Windows.Forms.ToolStrip> a un Windows Form, come aggiungere elementi al controllo <xref:System.Windows.Forms.ToolStrip> e come aggiungere il controllo <xref:System.Windows.Forms.ToolStrip> alla proprietà <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del controllo <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="ff69d-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff69d-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ff69d-106">Compiling the Code</span></span>  
 <span data-ttu-id="ff69d-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff69d-107">This code example requires:</span></span>  
  
- <span data-ttu-id="ff69d-108">Riferimenti agli assembly System.Drawing, System.Text e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ff69d-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff69d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff69d-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="ff69d-110">Controllo ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="ff69d-110">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="ff69d-111">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ff69d-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
