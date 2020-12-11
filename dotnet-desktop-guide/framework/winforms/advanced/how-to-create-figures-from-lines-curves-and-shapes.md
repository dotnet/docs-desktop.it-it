---
title: 'Procedura: Creare figure da linee, curve e forme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952133"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="46445-102">Procedura: Creare figure da linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="46445-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="46445-103">Per creare una figura, costruire un oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> , quindi chiamare i metodi, ad esempio <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> , per aggiungere primitive al percorso.</span><span class="sxs-lookup"><span data-stu-id="46445-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46445-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="46445-104">Example</span></span>  
 <span data-ttu-id="46445-105">Negli esempi di codice seguenti vengono creati percorsi con figure:</span><span class="sxs-lookup"><span data-stu-id="46445-105">The following code examples create paths that have figures:</span></span>  
  
- <span data-ttu-id="46445-106">Nel primo esempio viene creato un percorso con una sola figura.</span><span class="sxs-lookup"><span data-stu-id="46445-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="46445-107">La figura è costituita da un singolo arco. L'arco ha un angolo di sweep di – 180 gradi, che è in senso antiorario nel sistema di coordinate predefinito.</span><span class="sxs-lookup"><span data-stu-id="46445-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
- <span data-ttu-id="46445-108">Nel secondo esempio viene creato un percorso con due figure.</span><span class="sxs-lookup"><span data-stu-id="46445-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="46445-109">La prima figura è un arco seguito da una riga.</span><span class="sxs-lookup"><span data-stu-id="46445-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="46445-110">La seconda figura è una riga seguita da una curva seguita da una riga.</span><span class="sxs-lookup"><span data-stu-id="46445-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="46445-111">La prima figura viene lasciata aperta e la seconda figura viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="46445-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46445-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="46445-112">Compiling the Code</span></span>  
 <span data-ttu-id="46445-113">Gli esempi precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="46445-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46445-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46445-114">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="46445-115">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="46445-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="46445-116">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="46445-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
