---
title: Anti-aliasing con linee e curve
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 871c5cb3cd9356f677633acb04fe82021a9787c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952236"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="494ed-102">Anti-aliasing con linee e curve</span><span class="sxs-lookup"><span data-stu-id="494ed-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="494ed-103">Quando si utilizza GDI+ per creare una linea, si specifica il punto iniziale e il punto finale della linea, ma non è necessario fornire informazioni sui singoli pixel della riga.</span><span class="sxs-lookup"><span data-stu-id="494ed-103">When you use GDI+ to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> <span data-ttu-id="494ed-104">GDI+ funziona insieme al software per i driver di visualizzazione per determinare quali pixel verranno accesi per visualizzare la riga in un particolare dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="494ed-104">GDI+ works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="494ed-105">Aliasing</span><span class="sxs-lookup"><span data-stu-id="494ed-105">Aliasing</span></span>  
 <span data-ttu-id="494ed-106">Prendere in considerazione la linea rossa diritta che va dal punto (4, 2) al punto (16, 10).</span><span class="sxs-lookup"><span data-stu-id="494ed-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="494ed-107">Si supponga che il sistema di coordinate abbia l'origine nell'angolo superiore sinistro e che l'unità di misura sia il pixel.</span><span class="sxs-lookup"><span data-stu-id="494ed-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="494ed-108">Si supponga inoltre che l'asse x punti a destra e che l'asse y punti verso il basso.</span><span class="sxs-lookup"><span data-stu-id="494ed-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="494ed-109">Nella figura seguente viene illustrata una vista ingrandita della linea rossa disegnata su uno sfondo a più colori.</span><span class="sxs-lookup"><span data-stu-id="494ed-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="494ed-110">![Linea, senza antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="494ed-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="494ed-111">I pixel rossi utilizzati per il rendering della linea sono opachi.</span><span class="sxs-lookup"><span data-stu-id="494ed-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="494ed-112">Nessun pixel parzialmente trasparente nella riga.</span><span class="sxs-lookup"><span data-stu-id="494ed-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="494ed-113">Questo tipo di rendering della linea fornisce un aspetto irregolare alla riga e la linea assomiglia a una scalinata.</span><span class="sxs-lookup"><span data-stu-id="494ed-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="494ed-114">Questa tecnica di rappresentazione di una linea con una scala è detta aliasing; la scala è un alias per la linea teorica.</span><span class="sxs-lookup"><span data-stu-id="494ed-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="494ed-115">Anti-aliasing</span><span class="sxs-lookup"><span data-stu-id="494ed-115">Antialiasing</span></span>  
 <span data-ttu-id="494ed-116">Una tecnica più sofisticata per il rendering di una linea prevede l'uso di pixel parzialmente trasparenti insieme ai pixel opachi.</span><span class="sxs-lookup"><span data-stu-id="494ed-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="494ed-117">I pixel vengono impostati in rosso puro o in una combinazione di colore rosso e sfondo, a seconda della relativa chiusura.</span><span class="sxs-lookup"><span data-stu-id="494ed-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="494ed-118">Questo tipo di rendering è denominato anti-aliasing e produce una linea che l'occhio umano percepisce come più uniforme.</span><span class="sxs-lookup"><span data-stu-id="494ed-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="494ed-119">Nella figura seguente viene illustrato il modo in cui alcuni pixel vengono combinati con lo sfondo per produrre una riga con antialiasing.</span><span class="sxs-lookup"><span data-stu-id="494ed-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="494ed-120">![Antialiasing di una linea](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="494ed-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="494ed-121">L'anti-aliasing, detto anche smussamento, può essere applicato anche alle curve.</span><span class="sxs-lookup"><span data-stu-id="494ed-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="494ed-122">La figura seguente mostra una visualizzazione ingrandita di un'ellisse smussata.</span><span class="sxs-lookup"><span data-stu-id="494ed-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="494ed-123">![Antialiasing di curve](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="494ed-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="494ed-124">La figura seguente mostra la stessa ellisse nelle dimensioni effettive, una volta senza anti-aliasing e una volta con l'anti-aliasing.</span><span class="sxs-lookup"><span data-stu-id="494ed-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="494ed-125">![Esempio di antialiasing](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="494ed-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="494ed-126">Per creare linee e curve che usano l'anti-aliasing, creare un'istanza della <xref:System.Drawing.Graphics> classe e impostarne la <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> .</span><span class="sxs-lookup"><span data-stu-id="494ed-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="494ed-127">Chiamare quindi uno dei metodi di disegno di quella stessa <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="494ed-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="494ed-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="494ed-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="494ed-129">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="494ed-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="494ed-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="494ed-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
