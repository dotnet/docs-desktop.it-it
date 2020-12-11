---
title: 'Procedura: Usare un oggetto Pen per disegnare linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963223"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="06be4-102">Procedura: Usare un oggetto Pen per disegnare linee</span><span class="sxs-lookup"><span data-stu-id="06be4-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="06be4-103">Per creare linee, sono necessari un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="06be4-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="06be4-104">L' <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawLine%2A> metodo e l' <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio il colore e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="06be4-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06be4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="06be4-105">Example</span></span>  
 <span data-ttu-id="06be4-106">Nell'esempio seguente viene disegnata una riga da (20, 10) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="06be4-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="06be4-107">La prima istruzione usa il <xref:System.Drawing.Pen.%23ctor%2A> costruttore della classe per creare una penna nera.</span><span class="sxs-lookup"><span data-stu-id="06be4-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="06be4-108">L'unico argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore è un <xref:System.Drawing.Color> oggetto creato con il <xref:System.Drawing.Color.FromArgb%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="06be4-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="06be4-109">I valori utilizzati per creare l' <xref:System.Drawing.Color> oggetto, (255, 0, 0, 0), corrispondono ai componenti alfa, rosso, verde e blu del colore.</span><span class="sxs-lookup"><span data-stu-id="06be4-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="06be4-110">Questi valori definiscono una penna nera opaca.</span><span class="sxs-lookup"><span data-stu-id="06be4-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="06be4-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="06be4-111">Compiling the Code</span></span>  
 <span data-ttu-id="06be4-112">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="06be4-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06be4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06be4-113">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="06be4-114">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="06be4-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="06be4-115">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="06be4-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
