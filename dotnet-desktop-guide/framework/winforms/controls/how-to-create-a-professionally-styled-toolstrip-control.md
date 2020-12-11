---
title: 'Procedura: Creare un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963913"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="4feb6-102">Procedura: Creare un controllo ToolStrip professionale</span><span class="sxs-lookup"><span data-stu-id="4feb6-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="4feb6-103">Per assegnare un aspetto professionale ai controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione è possibile scrivere una classe personalizzata derivata dal tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="4feb6-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="4feb6-104">In Visual Studio è disponibile un supporto completo per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4feb6-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="4feb6-105">Vedere [Procedura dettagliata: creazione di un controllo ToolStrip professionale](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="4feb6-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4feb6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4feb6-106">Example</span></span>  
 <span data-ttu-id="4feb6-107">Nell'esempio di codice riportato di seguito viene illustrato come utilizzare i <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che simula il **riquadro di spostamento** fornito da Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="4feb6-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4feb6-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4feb6-108">Compiling the Code</span></span>  
 <span data-ttu-id="4feb6-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4feb6-109">This example requires:</span></span>  
  
- <span data-ttu-id="4feb6-110">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4feb6-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4feb6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4feb6-111">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="4feb6-112">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4feb6-112">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="4feb6-113">Procedura: Specificare voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="4feb6-113">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
