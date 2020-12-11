---
title: 'Procedura: Usare una classe di rendering del controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964840"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="28f38-102">Procedura: Usare una classe di rendering del controllo</span><span class="sxs-lookup"><span data-stu-id="28f38-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="28f38-103">In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Forms.ComboBoxRenderer> classe per eseguire il rendering della freccia a discesa di un controllo casella combinata.</span><span class="sxs-lookup"><span data-stu-id="28f38-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="28f38-104">L'esempio è costituito dal <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di un semplice controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28f38-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="28f38-105">La <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> proprietà viene utilizzata per determinare se gli stili di visualizzazione sono abilitati nell'area client delle finestre dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="28f38-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="28f38-106">Se gli stili di visualizzazione sono attivi, il <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> metodo eseguirà il rendering della freccia a discesa con gli stili di visualizzazione; in caso contrario, il <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> metodo eseguirà il rendering della freccia a discesa nello stile di Windows classico.</span><span class="sxs-lookup"><span data-stu-id="28f38-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28f38-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="28f38-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28f38-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="28f38-108">Compiling the Code</span></span>  
 <span data-ttu-id="28f38-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="28f38-109">This example requires:</span></span>  
  
- <span data-ttu-id="28f38-110">Controllo personalizzato derivato dalla <xref:System.Windows.Forms.Control> classe.</span><span class="sxs-lookup"><span data-stu-id="28f38-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="28f38-111">Oggetto <xref:System.Windows.Forms.Form> che ospita il controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="28f38-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="28f38-112">Riferimenti agli <xref:System?displayProperty=nameWithType> <xref:System.Drawing?displayProperty=nameWithType> <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> spazi dei nomi,, e.</span><span class="sxs-lookup"><span data-stu-id="28f38-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f38-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28f38-113">See also</span></span>

- [<span data-ttu-id="28f38-114">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="28f38-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
