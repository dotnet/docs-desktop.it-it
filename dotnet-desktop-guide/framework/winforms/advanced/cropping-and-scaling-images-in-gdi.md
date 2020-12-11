---
title: Ritaglio e ridimensionamento di immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952470"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="bb3b0-102">Ritaglio e ridimensionamento di immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="bb3b0-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="bb3b0-103">È possibile usare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo della <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e immagini raster.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="bb3b0-104"><xref:System.Drawing.Graphics.DrawImage%2A> è un metodo di overload, quindi è possibile fornire gli argomenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="bb3b0-105">Variazioni di DrawImage</span><span class="sxs-lookup"><span data-stu-id="bb3b0-105">DrawImage Variations</span></span>  
 <span data-ttu-id="bb3b0-106">Una variante del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un oggetto <xref:System.Drawing.Bitmap> e un oggetto <xref:System.Drawing.Rectangle> .</span><span class="sxs-lookup"><span data-stu-id="bb3b0-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="bb3b0-107">Il rettangolo specifica la destinazione per l'operazione di disegno. ovvero specifica il rettangolo in cui si desidera creare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="bb3b0-108">Se le dimensioni del rettangolo di destinazione sono diverse da quelle dell'immagine originale, l'immagine viene ridimensionata in modo da adattarsi al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="bb3b0-109">Nell'esempio di codice seguente viene illustrato come creare la stessa immagine tre volte: una volta senza scalabilità, una volta con un'espansione e una volta con una compressione:</span><span class="sxs-lookup"><span data-stu-id="bb3b0-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="bb3b0-110">Nella figura seguente sono illustrate le tre immagini.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="bb3b0-111">![Ridimensionamento](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="bb3b0-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="bb3b0-112">Alcune varianti del <xref:System.Drawing.Graphics.DrawImage%2A> Metodo hanno un parametro source-Rectangle, oltre a un parametro Destination-Rectangle.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="bb3b0-113">Il parametro source-Rectangle specifica la parte dell'immagine originale da creare.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="bb3b0-114">Il rettangolo di destinazione specifica il rettangolo in cui creare la parte dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="bb3b0-115">Se le dimensioni del rettangolo di destinazione sono diverse dalla dimensione del rettangolo di origine, l'immagine viene ridimensionata in modo da adattarsi al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="bb3b0-116">Nell'esempio di codice seguente viene illustrato come costruire un oggetto <xref:System.Drawing.Bitmap> dal file Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="bb3b0-117">L'intera immagine viene disegnata senza alcun ridimensionamento in corrispondenza di (0, 0).</span><span class="sxs-lookup"><span data-stu-id="bb3b0-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="bb3b0-118">Una piccola parte dell'immagine viene disegnata due volte: una volta con una compressione e una volta con un'espansione.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="bb3b0-119">Nella figura seguente viene illustrata l'immagine non ridimensionata e le parti di immagine compresse ed espanse.</span><span class="sxs-lookup"><span data-stu-id="bb3b0-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="bb3b0-120">![Ritaglio e ridimensionamento](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="bb3b0-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3b0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb3b0-121">See also</span></span>

- [<span data-ttu-id="bb3b0-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="bb3b0-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="bb3b0-123">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="bb3b0-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
