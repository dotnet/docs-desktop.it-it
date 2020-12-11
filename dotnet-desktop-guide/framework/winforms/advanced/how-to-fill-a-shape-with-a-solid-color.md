---
title: 'Procedura: Riempire una forma con un colore a tinta unita'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962614"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="bc0f2-102">Procedura: Riempire una forma con un colore a tinta unita</span><span class="sxs-lookup"><span data-stu-id="bc0f2-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="bc0f2-103">Per riempire una forma con un colore a tinta unita, creare un <xref:System.Drawing.SolidBrush> oggetto e quindi passare l' <xref:System.Drawing.SolidBrush> oggetto come argomento a uno dei metodi Fill della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="bc0f2-104">Nell'esempio seguente viene illustrato come riempire un'ellisse con il colore rosso.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc0f2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc0f2-105">Example</span></span>  
 <span data-ttu-id="bc0f2-106">Nel codice seguente, il <xref:System.Drawing.SolidBrush.%23ctor%2A> costruttore accetta un <xref:System.Drawing.Color> oggetto come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="bc0f2-107">I valori utilizzati dal <xref:System.Drawing.Color.FromArgb%2A> Metodo rappresentano i componenti alfa, rosso, verde e blu del colore.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="bc0f2-108">Ognuno di questi valori deve essere compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="bc0f2-109">Il primo 255 indica che il colore è completamente opaco e il secondo 255 indica che il componente rosso è a intensità piena.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="bc0f2-110">I due zeri indicano che i componenti verde e blu hanno un'intensità pari a 0.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="bc0f2-111">I quattro numeri (0, 0, 100, 60) passati al <xref:System.Drawing.Graphics.FillEllipse%2A> Metodo specificano la posizione e le dimensioni del rettangolo di delimitazione per l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="bc0f2-112">Il rettangolo ha un angolo superiore sinistro di (0,0), una larghezza di 100 e un'altezza di 60.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc0f2-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bc0f2-113">Compiling the Code</span></span>  
 <span data-ttu-id="bc0f2-114">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bc0f2-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0f2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc0f2-115">See also</span></span>

- [<span data-ttu-id="bc0f2-116">Utilizzo di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="bc0f2-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
