---
title: Curve aperte e chiuse in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963115"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="67b0f-102">Curve aperte e chiuse in GDI+</span><span class="sxs-lookup"><span data-stu-id="67b0f-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="67b0f-103">Nella figura seguente sono illustrate due curve: una aperta e una chiusa.</span><span class="sxs-lookup"><span data-stu-id="67b0f-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="67b0f-104">![Apri & curve chiuse](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="67b0f-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="67b0f-105">Interfaccia gestita per curve</span><span class="sxs-lookup"><span data-stu-id="67b0f-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="67b0f-106">Le curve chiuse hanno una parte interna e pertanto possono essere riempite con un pennello.</span><span class="sxs-lookup"><span data-stu-id="67b0f-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="67b0f-107">La <xref:System.Drawing.Graphics> classe in GDI+ fornisce i metodi seguenti per compilare forme e curve chiuse: <xref:System.Drawing.Graphics.FillRectangle%2A> , <xref:System.Drawing.Graphics.FillEllipse%2A> , <xref:System.Drawing.Graphics.FillPie%2A> , <xref:System.Drawing.Graphics.FillPolygon%2A> , <xref:System.Drawing.Graphics.FillClosedCurve%2A> , <xref:System.Drawing.Graphics.FillPath%2A> e <xref:System.Drawing.Graphics.FillRegion%2A> .</span><span class="sxs-lookup"><span data-stu-id="67b0f-107">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="67b0f-108">Ogni volta che si chiama uno di questi metodi, è necessario passare uno dei tipi di pennello specifici ( <xref:System.Drawing.SolidBrush> ,, <xref:System.Drawing.Drawing2D.HatchBrush> <xref:System.Drawing.TextureBrush> , <xref:System.Drawing.Drawing2D.LinearGradientBrush> o <xref:System.Drawing.Drawing2D.PathGradientBrush> ) come argomento.</span><span class="sxs-lookup"><span data-stu-id="67b0f-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="67b0f-109">Il <xref:System.Drawing.Graphics.FillPie%2A> metodo è un complemento al <xref:System.Drawing.Graphics.DrawArc%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="67b0f-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="67b0f-110">Così come il <xref:System.Drawing.Graphics.DrawArc%2A> metodo disegna una parte del contorno di un'ellisse, il <xref:System.Drawing.Graphics.FillPie%2A> metodo riempie una parte dell'area interna di un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="67b0f-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="67b0f-111">Nell'esempio seguente viene disegnato un arco e viene riempita la parte corrispondente dell'interno dell'ellisse:</span><span class="sxs-lookup"><span data-stu-id="67b0f-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="67b0f-112">Nella figura seguente vengono illustrati l'arco e la torta piena.</span><span class="sxs-lookup"><span data-stu-id="67b0f-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="67b0f-113">![Apri & curve chiuse](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="67b0f-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="67b0f-114">Il <xref:System.Drawing.Graphics.FillClosedCurve%2A> metodo è un complemento al <xref:System.Drawing.Graphics.DrawClosedCurve%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="67b0f-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="67b0f-115">Entrambi i metodi chiudono automaticamente la curva connettendo il punto finale al punto iniziale.</span><span class="sxs-lookup"><span data-stu-id="67b0f-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="67b0f-116">Nell'esempio seguente viene disegnata una curva che passa attraverso (0, 0), (60, 20) e (40, 50).</span><span class="sxs-lookup"><span data-stu-id="67b0f-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="67b0f-117">La curva viene quindi chiusa automaticamente connettendosi (40, 50) al punto iniziale (0, 0) e l'interno viene riempito con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="67b0f-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="67b0f-118">Il <xref:System.Drawing.Graphics.FillPath%2A> metodo riempie l'interno delle parti separate di un percorso.</span><span class="sxs-lookup"><span data-stu-id="67b0f-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="67b0f-119">Se una parte di un tracciato non costituisce una curva o una forma chiusa, il <xref:System.Drawing.Graphics.FillPath%2A> metodo chiude automaticamente tale parte del percorso prima di compilarlo.</span><span class="sxs-lookup"><span data-stu-id="67b0f-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="67b0f-120">Nell'esempio seguente viene disegnato e compilato un percorso costituito da un arco, una spline di cardinalità, una stringa e una torta:</span><span class="sxs-lookup"><span data-stu-id="67b0f-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="67b0f-121">Nella figura seguente viene illustrato il percorso con e senza il riempimento a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="67b0f-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="67b0f-122">Si noti che il testo nella stringa è delineato, ma non riempito, dal <xref:System.Drawing.Graphics.DrawPath%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="67b0f-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="67b0f-123">Si tratta del <xref:System.Drawing.Graphics.FillPath%2A> metodo che dipinge gli interni dei caratteri nella stringa.</span><span class="sxs-lookup"><span data-stu-id="67b0f-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="67b0f-124">![Stringa in un percorso](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="67b0f-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b0f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67b0f-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="67b0f-126">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="67b0f-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="67b0f-127">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="67b0f-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="67b0f-128">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="67b0f-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
