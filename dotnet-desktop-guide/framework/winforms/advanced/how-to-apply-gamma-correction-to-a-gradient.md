---
title: 'Procedura: Applicare la correzione gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960976"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="3fb6a-102">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="3fb6a-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="3fb6a-103">È possibile abilitare la correzione gamma per un pennello sfumatura lineare impostando la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà del pennello su `true` .</span><span class="sxs-lookup"><span data-stu-id="3fb6a-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="3fb6a-104">È possibile disabilitare la correzione gamma impostando la <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà su `false` .</span><span class="sxs-lookup"><span data-stu-id="3fb6a-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="3fb6a-105">Per impostazione predefinita, la correzione gamma è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb6a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fb6a-106">Example</span></span>  

<span data-ttu-id="3fb6a-107">L'esempio seguente è un metodo chiamato dal gestore eventi di un controllo <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="3fb6a-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="3fb6a-108">Nell'esempio viene creato un pennello sfumato lineare e tale pennello viene utilizzato per riempire due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="3fb6a-109">Il primo rettangolo viene riempito senza correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="3fb6a-110">Nella figura seguente sono illustrati i due rettangoli riempiti.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="3fb6a-111">Il rettangolo superiore, che non ha la correzione gamma, appare scuro al centro.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="3fb6a-112">Il rettangolo inferiore, con correzione gamma, sembra avere un'intensità più uniforme.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![Due rettangoli riempiti da gradienti, con e senza correzione gamma.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fb6a-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3fb6a-114">Compiling the Code</span></span>  
 <span data-ttu-id="3fb6a-115">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb6a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fb6a-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="3fb6a-117">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="3fb6a-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
