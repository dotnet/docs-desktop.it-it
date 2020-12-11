---
title: 'Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: a6655652a7c5dedb8e183356688972c07a705cbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962587"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="f7b85-102">Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="f7b85-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="f7b85-103">Se si sta gestendo direttamente grafica memorizzata nel buffer, sarà necessario essere in grado di creare ed eseguire il rendering dei buffer grafici.</span><span class="sxs-lookup"><span data-stu-id="f7b85-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="f7b85-104">È possibile creare istanze della classe <xref:System.Drawing.BufferedGraphics> associata alle aree di disegno sullo schermo chiamando il metodo <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7b85-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="f7b85-105">Il metodo crea un'istanza di <xref:System.Drawing.BufferedGraphics> associata a una particolare area di rendering, ad esempio un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="f7b85-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="f7b85-106">Una volta creata un'istanza di <xref:System.Drawing.BufferedGraphics>, è possibile disegnare la grafica nel buffer da essa rappresentato tramite la proprietà <xref:System.Drawing.BufferedGraphics.Graphics%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7b85-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="f7b85-107">Una volta eseguite tutte le operazioni grafiche, è possibile copiare il contenuto del buffer sullo schermo chiamando il metodo <xref:System.Drawing.BufferedGraphics.Render%2A>. </span><span class="sxs-lookup"><span data-stu-id="f7b85-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7b85-108">Se si esegue direttamente il rendering, l'uso di memoria aumenterà, anche se solo leggermente.</span><span class="sxs-lookup"><span data-stu-id="f7b85-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="f7b85-109">Per visualizzare manualmente la grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="f7b85-109">To manually display buffered graphics</span></span>  
  
1. <span data-ttu-id="f7b85-110">Ottenere un riferimento a un'istanza della classe <xref:System.Drawing.BufferedGraphicsContext>.</span><span class="sxs-lookup"><span data-stu-id="f7b85-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="f7b85-111">Per altre informazioni, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="f7b85-111">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2. <span data-ttu-id="f7b85-112">Creare un'istanza della classe <xref:System.Drawing.BufferedGraphics> chiamando il metodo <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>e, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f7b85-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="f7b85-113">Disegnare la grafica nel buffer relativo impostando la proprietà <xref:System.Drawing.BufferedGraphics.Graphics%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7b85-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="f7b85-114">Esempio:</span><span class="sxs-lookup"><span data-stu-id="f7b85-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4. <span data-ttu-id="f7b85-115">Una volta completate tutte le operazioni di disegno nel buffer grafico, chiamare il metodo <xref:System.Drawing.BufferedGraphics.Render%2A> per eseguire il rendering del buffer, nell'area di disegno associata al buffer, oppure in un'area specificata, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f7b85-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5. <span data-ttu-id="f7b85-116">Una volta terminato il rendering della grafica, chiamare il metodo `Dispose` sull'istanza di <xref:System.Drawing.BufferedGraphics> per liberare risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="f7b85-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="f7b85-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b85-117">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [<span data-ttu-id="f7b85-118">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="f7b85-118">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="f7b85-119">Procedura: Gestire manualmente la grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="f7b85-119">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)
