---
title: "Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963202"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="f0b49-102">Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento</span><span class="sxs-lookup"><span data-stu-id="f0b49-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="f0b49-103">La modalità di interpolazione di un <xref:System.Drawing.Graphics> oggetto influenza il modo in cui GDI+ ridimensiona (estende e compatta) le immagini.</span><span class="sxs-lookup"><span data-stu-id="f0b49-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way GDI+ scales (stretches and shrinks) images.</span></span> <span data-ttu-id="f0b49-104">L' <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione definisce diverse modalità di interpolazione, alcune delle quali sono mostrate nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="f0b49-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="f0b49-105">Per estendere un'immagine, è necessario eseguire il mapping di ogni pixel nell'immagine originale a un gruppo di pixel nell'immagine più grande.</span><span class="sxs-lookup"><span data-stu-id="f0b49-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="f0b49-106">Per compattare un'immagine, è necessario eseguire il mapping dei gruppi di pixel nell'immagine originale a singoli pixel nell'immagine più piccola.</span><span class="sxs-lookup"><span data-stu-id="f0b49-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="f0b49-107">L'efficacia degli algoritmi che eseguono questi mapping determina la qualità di un'immagine ridimensionata.</span><span class="sxs-lookup"><span data-stu-id="f0b49-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="f0b49-108">Gli algoritmi che producono immagini con scalabilità di qualità superiore tendono a richiedere più tempo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="f0b49-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="f0b49-109">Nell'elenco precedente <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> è la modalità di qualità più bassa ed <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> è la modalità di qualità più elevata.</span><span class="sxs-lookup"><span data-stu-id="f0b49-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="f0b49-110">Per impostare la modalità di interpolazione, assegnare uno dei membri dell' <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione alla <xref:System.Drawing.Graphics.InterpolationMode%2A> proprietà di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f0b49-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0b49-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0b49-111">Example</span></span>  
 <span data-ttu-id="f0b49-112">Nell'esempio seguente viene disegnata un'immagine, quindi viene compattata l'immagine con tre diverse modalità di interpolazione.</span><span class="sxs-lookup"><span data-stu-id="f0b49-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="f0b49-113">La figura seguente illustra l'immagine originale e le tre immagini più piccole.</span><span class="sxs-lookup"><span data-stu-id="f0b49-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![Screenshot che mostra un'immagine con diverse impostazioni di interpolazione.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0b49-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f0b49-115">Compiling the Code</span></span>  
 <span data-ttu-id="f0b49-116">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f0b49-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b49-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0b49-117">See also</span></span>

- [<span data-ttu-id="f0b49-118">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="f0b49-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f0b49-119">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="f0b49-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
