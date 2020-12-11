---
title: 'Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961624"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="3deda-102">Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3deda-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="3deda-103">È possibile usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3deda-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="3deda-104">La proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina se il controllo <xref:System.Windows.Forms.ToolStripStatusLabel> riempie automaticamente lo spazio disponibile nel controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3deda-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3deda-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3deda-105">Example</span></span>  
 <span data-ttu-id="3deda-106">Il seguente esempio di codice dimostra come usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3deda-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="3deda-107">Il gestore dell'evento <xref:System.Windows.Forms.ToolStripItem.Click> esegue un'operazione di OR esclusivo (XOR) per cambiare il valore della proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.</span><span class="sxs-lookup"><span data-stu-id="3deda-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="3deda-108">Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi fare clic su **Middle (Spring)** sul <xref:System.Windows.Forms.StatusStrip> controllo per cambiare il valore della <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="3deda-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3deda-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3deda-109">Compiling the Code</span></span>  
 <span data-ttu-id="3deda-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3deda-110">This example requires:</span></span>  
  
- <span data-ttu-id="3deda-111">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3deda-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3deda-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3deda-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3deda-113">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3deda-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
