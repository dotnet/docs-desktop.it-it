---
title: 'Procedura: Creare una sfumatura lineare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952397"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="00c4f-102">Procedura: Creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="00c4f-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="00c4f-103">GDI+ fornisce gradienti lineari orizzontali, verticali e diagonali.</span><span class="sxs-lookup"><span data-stu-id="00c4f-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="00c4f-104">Per impostazione predefinita, il colore in una sfumatura lineare cambia in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="00c4f-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="00c4f-105">Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore cambi in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="00c4f-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="00c4f-106">Gli esempi in questo articolo sono metodi che vengono chiamati dal gestore eventi di un controllo <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="00c4f-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="00c4f-107">Nell'esempio seguente vengono riempite una riga, un'ellisse e un rettangolo con un pennello sfumato lineare orizzontale.</span><span class="sxs-lookup"><span data-stu-id="00c4f-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="00c4f-108">Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori.</span><span class="sxs-lookup"><span data-stu-id="00c4f-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="00c4f-109">Il primo punto (0, 10) è associato al primo colore (rosso) e il secondo punto (200, 10) viene associato al secondo colore (blu).</span><span class="sxs-lookup"><span data-stu-id="00c4f-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="00c4f-110">Come ci si aspetterebbe, la linea disegnata da (0, 10) a (200, 10) cambia gradualmente da rosso a blu.</span><span class="sxs-lookup"><span data-stu-id="00c4f-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="00c4f-111">I 10s nei punti (0, 10) e (200, 10) non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="00c4f-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="00c4f-112">Ciò che è importante è che i due punti hanno la stessa seconda coordinata, ovvero la linea che la connette è orizzontale.</span><span class="sxs-lookup"><span data-stu-id="00c4f-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="00c4f-113">Anche l'ellisse e il rettangolo cambiano gradualmente da rosso a blu, perché la coordinata orizzontale va da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="00c4f-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="00c4f-114">La figura seguente mostra la riga, l'ellisse e il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="00c4f-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="00c4f-115">Si noti che la sfumatura di colore si ripete quando la coordinata orizzontale aumenta oltre 200.</span><span class="sxs-lookup"><span data-stu-id="00c4f-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 ![Una linea, un'ellisse e un rettangolo riempiti con una sfumatura di colore.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="00c4f-117">Per utilizzare sfumature lineari orizzontali</span><span class="sxs-lookup"><span data-stu-id="00c4f-117">To use horizontal linear gradients</span></span>  
  
- <span data-ttu-id="00c4f-118">Passare rispettivamente il rosso opaco e il blu opaco come terzo e quarto argomento.</span><span class="sxs-lookup"><span data-stu-id="00c4f-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="00c4f-119">Nell'esempio precedente, i componenti dei colori cambiano in modo lineare quando si passa da una coordinata orizzontale di 0 a una coordinata orizzontale di 200.</span><span class="sxs-lookup"><span data-stu-id="00c4f-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="00c4f-120">Ad esempio, un punto la cui prima coordinata è a metà tra 0 e 200 avrà un componente blu a metà tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="00c4f-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="00c4f-121">GDI+ consente di modificare il modo in cui un colore varia da un bordo di una sfumatura all'altro.</span><span class="sxs-lookup"><span data-stu-id="00c4f-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="00c4f-122">Si supponga di voler creare un pennello sfumato che cambi da nero a rosso in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="00c4f-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="00c4f-123">Coordinata orizzontale</span><span class="sxs-lookup"><span data-stu-id="00c4f-123">Horizontal coordinate</span></span>|<span data-ttu-id="00c4f-124">Componenti RGB</span><span class="sxs-lookup"><span data-stu-id="00c4f-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="00c4f-125">0</span><span class="sxs-lookup"><span data-stu-id="00c4f-125">0</span></span>|<span data-ttu-id="00c4f-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="00c4f-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="00c4f-127">40</span><span class="sxs-lookup"><span data-stu-id="00c4f-127">40</span></span>|<span data-ttu-id="00c4f-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="00c4f-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="00c4f-129">200</span><span class="sxs-lookup"><span data-stu-id="00c4f-129">200</span></span>|<span data-ttu-id="00c4f-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="00c4f-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="00c4f-131">Si noti che il componente rosso è a metà intensità quando la coordinata orizzontale è solo il 20% della strada da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="00c4f-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="00c4f-132">Nell'esempio seguente viene impostata la <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> proprietà per associare tre intensità relative con tre posizioni relative.</span><span class="sxs-lookup"><span data-stu-id="00c4f-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="00c4f-133">Come nella tabella precedente, un'intensità relativa di 0,5 è associata a una posizione relativa di 0,2.</span><span class="sxs-lookup"><span data-stu-id="00c4f-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="00c4f-134">Il codice riempie un'ellisse e un rettangolo con il pennello sfumatura.</span><span class="sxs-lookup"><span data-stu-id="00c4f-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="00c4f-135">Nella figura seguente vengono illustrati l'ellisse e il rettangolo risultanti.</span><span class="sxs-lookup"><span data-stu-id="00c4f-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 ![Ellisse e rettangolo riempiti con una sfumatura di colore orizzontale.](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a><span data-ttu-id="00c4f-137">Per personalizzare le sfumature lineari</span><span class="sxs-lookup"><span data-stu-id="00c4f-137">To customize linear gradients</span></span>  
  
- <span data-ttu-id="00c4f-138">Passare rispettivamente il nero opaco e il rosso opaco come terzo e quarto argomento.</span><span class="sxs-lookup"><span data-stu-id="00c4f-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="00c4f-139">Le sfumature degli esempi precedenti sono state orizzontali; ovvero il colore cambia gradualmente man mano che si sposta lungo una linea orizzontale.</span><span class="sxs-lookup"><span data-stu-id="00c4f-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="00c4f-140">È anche possibile definire sfumature verticali e sfumature diagonali.</span><span class="sxs-lookup"><span data-stu-id="00c4f-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="00c4f-141">Nell'esempio seguente vengono passati i punti (0, 0) e (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="00c4f-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="00c4f-142">Il colore blu è associato a (0, 0) e il colore verde è associato a (200, 100).</span><span class="sxs-lookup"><span data-stu-id="00c4f-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="00c4f-143">Una linea (con larghezza della penna 10) e un'ellisse vengono riempite con il pennello sfumatura lineare.</span><span class="sxs-lookup"><span data-stu-id="00c4f-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="00c4f-144">La figura seguente mostra la riga e l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="00c4f-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="00c4f-145">Si noti che il colore nell'ellisse cambia gradualmente man mano che si sposta lungo ogni riga che è parallela alla riga che attraversa (0,0) e (200, 100).</span><span class="sxs-lookup"><span data-stu-id="00c4f-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 ![Una linea e un'ellisse riempite con una sfumatura di colore diagonale.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="00c4f-147">Per creare sfumature lineari diagonali</span><span class="sxs-lookup"><span data-stu-id="00c4f-147">To create diagonal linear gradients</span></span>  
  
- <span data-ttu-id="00c4f-148">Passare rispettivamente il blu opaco e il verde opaco come terzo e quarto argomento.</span><span class="sxs-lookup"><span data-stu-id="00c4f-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="00c4f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00c4f-149">See also</span></span>

- [<span data-ttu-id="00c4f-150">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="00c4f-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="00c4f-151">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="00c4f-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
