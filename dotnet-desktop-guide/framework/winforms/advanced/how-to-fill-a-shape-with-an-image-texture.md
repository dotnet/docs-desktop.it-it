---
title: "Procedura: Riempire una forma con una trama basata su un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963397"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="810f9-102">Procedura: Riempire una forma con una trama basata su un'immagine</span><span class="sxs-lookup"><span data-stu-id="810f9-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="810f9-103">È possibile riempire una forma chiusa con una trama usando la <xref:System.Drawing.Image> classe e la <xref:System.Drawing.TextureBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="810f9-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="810f9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="810f9-104">Example</span></span>  
 <span data-ttu-id="810f9-105">Nell'esempio seguente viene riempita un'ellisse con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="810f9-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="810f9-106">Il codice costruisce un <xref:System.Drawing.Image> oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="810f9-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="810f9-107">La terza istruzione ridimensiona l'immagine e la quarta viene riempita dall'ellisse con copie ripetute dell'immagine ridimensionata.</span><span class="sxs-lookup"><span data-stu-id="810f9-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="810f9-108">Nel codice seguente, la <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che venga disegnata.</span><span class="sxs-lookup"><span data-stu-id="810f9-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="810f9-109">Si supponga che l'immagine originale abbia una larghezza di 640 pixel e un'altezza di 480 pixel.</span><span class="sxs-lookup"><span data-stu-id="810f9-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="810f9-110">La trasformazione riduce l'immagine a 75 × 75 impostando i valori di ridimensionamento orizzontale e verticale.</span><span class="sxs-lookup"><span data-stu-id="810f9-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="810f9-111">Nell'esempio seguente, la dimensione dell'immagine è 75 × 75 e la dimensione dell'ellisse è 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="810f9-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="810f9-112">Poiché l'immagine è più piccola dell'ellisse che sta riempiendo, l'ellisse viene affiancata all'immagine.</span><span class="sxs-lookup"><span data-stu-id="810f9-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="810f9-113">L'affiancamento significa che l'immagine viene ripetuta orizzontalmente e verticalmente fino a quando non viene raggiunto il limite della forma.</span><span class="sxs-lookup"><span data-stu-id="810f9-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="810f9-114">Per ulteriori informazioni sull'affiancamento, vedere [procedura: affiancare una forma con un'immagine](how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="810f9-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="810f9-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="810f9-115">Compiling the Code</span></span>  
 <span data-ttu-id="810f9-116">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="810f9-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="810f9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="810f9-117">See also</span></span>

- [<span data-ttu-id="810f9-118">Utilizzo di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="810f9-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
