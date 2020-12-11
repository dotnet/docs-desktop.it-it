---
title: "Procedura: Impostare il renderer ToolStrip per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965203"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="dffad-102">Procedura: Impostare il renderer ToolStrip per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="dffad-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="dffad-103">È possibile personalizzare l'aspetto dei singoli controlli <xref:System.Windows.Forms.ToolStrip> o di tutti i controlli <xref:System.Windows.Forms.ToolStrip> presenti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dffad-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffad-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dffad-104">Example</span></span>  
 <span data-ttu-id="dffad-105">Nell'esempio di codice riportato di seguito viene dimostrato come applicare selettivamente un renderer personalizzato a un controllo <xref:System.Windows.Forms.ToolStrip> e a un controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dffad-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="dffad-106">Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi selezionare l'ambito del rendering personalizzato dal controllo <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="dffad-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="dffad-107">Scegliere **Applica** per impostare il renderer.</span><span class="sxs-lookup"><span data-stu-id="dffad-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="dffad-108">Per visualizzare il rendering della voce di menu personalizzata, selezionare l' <xref:System.Windows.Forms.MenuStrip> opzione nel <xref:System.Windows.Forms.ComboBox> controllo, fare clic su **applica**, quindi aprire la voce di menu **file** .</span><span class="sxs-lookup"><span data-stu-id="dffad-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="dffad-109">Impostare la proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a tutti i controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dffad-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="dffad-110">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a un singolo controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="dffad-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dffad-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dffad-111">Compiling the Code</span></span>  
 <span data-ttu-id="dffad-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffad-112">This example requires:</span></span>  
  
- <span data-ttu-id="dffad-113">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="dffad-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffad-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffad-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="dffad-115">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="dffad-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
