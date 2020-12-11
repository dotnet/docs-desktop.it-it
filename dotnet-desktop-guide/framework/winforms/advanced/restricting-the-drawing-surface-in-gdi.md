---
title: Limitazione della superficie di disegno in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963094"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="456b2-102">Limitazione della superficie di disegno in GDI+</span><span class="sxs-lookup"><span data-stu-id="456b2-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="456b2-103">Il ritaglio comporta la limitazione del disegno a un determinato rettangolo o area.</span><span class="sxs-lookup"><span data-stu-id="456b2-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="456b2-104">La figura seguente mostra la stringa "Hello" ritagliata in un'area a forma di cuore.</span><span class="sxs-lookup"><span data-stu-id="456b2-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="456b2-105">![Superficie di disegno limitata](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="456b2-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="456b2-106">Ritaglio con aree</span><span class="sxs-lookup"><span data-stu-id="456b2-106">Clipping with Regions</span></span>  
 <span data-ttu-id="456b2-107">Le aree possono essere costruite da percorsi e i percorsi possono contenere le strutture delle stringhe, quindi è possibile usare il testo delineato per il ritaglio.</span><span class="sxs-lookup"><span data-stu-id="456b2-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="456b2-108">Nella figura seguente viene illustrato un set di ellissi concentrici ritagliati all'interno di una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="456b2-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="456b2-109">![Superficie di disegno limitata](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="456b2-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="456b2-110">Per disegnare con il ritaglio, creare un <xref:System.Drawing.Graphics> oggetto, impostarne la <xref:System.Drawing.Graphics.Clip%2A> proprietà e quindi chiamare i metodi di disegno dello stesso <xref:System.Drawing.Graphics> oggetto:</span><span class="sxs-lookup"><span data-stu-id="456b2-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="456b2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="456b2-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="456b2-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="456b2-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="456b2-113">Utilizzo delle regioni</span><span class="sxs-lookup"><span data-stu-id="456b2-113">Using Regions</span></span>](using-regions.md)
