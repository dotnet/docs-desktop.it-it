---
title: 'Procedura: Appiattire un percorso curvo in una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963385"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="328ab-102">Procedura: Appiattire un percorso curvo in una linea</span><span class="sxs-lookup"><span data-stu-id="328ab-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="328ab-103">Un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di linee e spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="328ab-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="328ab-104">È possibile aggiungere diversi tipi di curve (ellissi, archi, spline cardinali) a un tracciato, ma ogni curva viene convertita in una spline di Bézier prima di essere archiviata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="328ab-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="328ab-105">L'appiattimento di un tracciato è costituito dalla conversione di ogni spline di Bézier nel percorso a una sequenza di linee rette.</span><span class="sxs-lookup"><span data-stu-id="328ab-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="328ab-106">Nella figura seguente viene illustrato un percorso prima e dopo l'appiattimento.</span><span class="sxs-lookup"><span data-stu-id="328ab-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="328ab-107">![Curve e linee rette](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="328ab-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="328ab-108">Per rendere flat un tracciato</span><span class="sxs-lookup"><span data-stu-id="328ab-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="328ab-109">chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="328ab-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="328ab-110">Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di planarità che specifica la distanza massima tra il percorso bidimensionale e il percorso originale.</span><span class="sxs-lookup"><span data-stu-id="328ab-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328ab-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="328ab-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="328ab-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="328ab-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="328ab-113">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="328ab-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
