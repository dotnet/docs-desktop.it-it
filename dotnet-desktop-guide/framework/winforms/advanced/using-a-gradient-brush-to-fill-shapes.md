---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963031"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="dfad7-102">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="dfad7-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="dfad7-103">È possibile utilizzare un pennello sfumatura per riempire una forma con un colore a modifica graduale.</span><span class="sxs-lookup"><span data-stu-id="dfad7-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="dfad7-104">È ad esempio possibile utilizzare una sfumatura orizzontale per riempire una forma con un colore che cambia gradualmente man mano che si passa dal bordo sinistro della forma al bordo destro.</span><span class="sxs-lookup"><span data-stu-id="dfad7-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="dfad7-105">Immaginate un rettangolo con un bordo sinistro nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un bordo destro rosso (rappresentato da 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="dfad7-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="dfad7-106">Se il rettangolo è 256 pixel di larghezza, il componente rosso di un determinato pixel sarà maggiore di uno rispetto al componente rosso del pixel alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="dfad7-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="dfad7-107">Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel ha (1, 0, 0), il terzo pixel ha (2, 0, 0) e così via, fino a quando non si arriva al pixel più a destra, che include componenti colore (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="dfad7-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="dfad7-108">Questi valori di colore interpolati costituiscono la sfumatura di colore.</span><span class="sxs-lookup"><span data-stu-id="dfad7-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="dfad7-109">Una sfumatura lineare cambia colore mentre si sposta orizzontalmente, verticalmente o in parallelo in una linea inclinata specificata.</span><span class="sxs-lookup"><span data-stu-id="dfad7-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="dfad7-110">Una sfumatura di tracciato cambia colore mentre si sposta sull'interno e sul limite di un tracciato.</span><span class="sxs-lookup"><span data-stu-id="dfad7-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="dfad7-111">È possibile personalizzare le sfumature del tracciato per ottenere una vasta gamma di effetti.</span><span class="sxs-lookup"><span data-stu-id="dfad7-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="dfad7-112">Nella figura seguente viene illustrato un rettangolo riempito con un pennello sfumato lineare e un'ellisse riempita con un pennello sfumatura tracciato:</span><span class="sxs-lookup"><span data-stu-id="dfad7-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush:</span></span>  
  
 ![Rettangolo riempito con un pennello sfumato con un'ellisse.](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a><span data-ttu-id="dfad7-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dfad7-114">In This Section</span></span>  
 [<span data-ttu-id="dfad7-115">Procedura: Creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="dfad7-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="dfad7-116">Viene illustrato come creare una sfumatura lineare utilizzando la <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="dfad7-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="dfad7-117">Procedura: Creare una sfumatura percorso</span><span class="sxs-lookup"><span data-stu-id="dfad7-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="dfad7-118">Viene descritto come creare una sfumatura del percorso utilizzando la <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="dfad7-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="dfad7-119">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="dfad7-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="dfad7-120">Viene illustrato come usare la correzione gamma con un pennello sfumatura.</span><span class="sxs-lookup"><span data-stu-id="dfad7-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dfad7-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="dfad7-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="dfad7-122">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="dfad7-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="dfad7-123">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="dfad7-123">Contains a description of this class and has links to all of its members.</span></span>
