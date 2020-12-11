---
title: 'Procedura: Ritagliare e modificare le dimensioni di immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951459"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="8ece8-102">Procedura: Ritagliare e modificare le dimensioni di immagini</span><span class="sxs-lookup"><span data-stu-id="8ece8-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="8ece8-103">La <xref:System.Drawing.Graphics> classe fornisce diversi <xref:System.Drawing.Graphics.DrawImage%2A> metodi, alcuni dei quali hanno parametri di origine e di destinazione rettangolari che è possibile usare per ritagliare e ridimensionare le immagini.</span><span class="sxs-lookup"><span data-stu-id="8ece8-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ece8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ece8-104">Example</span></span>  
 <span data-ttu-id="8ece8-105">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file su disco Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="8ece8-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="8ece8-106">Il codice disegna l'intera immagine Apple nelle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="8ece8-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="8ece8-107">Il codice chiama quindi il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto per creare una parte dell'immagine Apple in un rettangolo di destinazione più grande dell'immagine Apple originale.</span><span class="sxs-lookup"><span data-stu-id="8ece8-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="8ece8-108">Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la parte della mela da creare osservando il rettangolo di origine, specificato dal terzo, dal quarto, dal quinto e dal sesto argomento.</span><span class="sxs-lookup"><span data-stu-id="8ece8-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="8ece8-109">In questo caso, la mela viene ritagliata al 75% della larghezza e il 75% dell'altezza.</span><span class="sxs-lookup"><span data-stu-id="8ece8-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="8ece8-110">Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la posizione in cui creare la mela ritagliata e la dimensione della mela ritagliata esaminando il rettangolo di destinazione, specificato dal secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ece8-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="8ece8-111">In questo caso, il rettangolo di destinazione è più grande del 30% e il 30% più alto rispetto all'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="8ece8-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="8ece8-112">La figura seguente mostra l'Apple originale e l'Apple ritagliata e ridimensionata.</span><span class="sxs-lookup"><span data-stu-id="8ece8-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![Screenshot di un'immagine originale e della stessa immagine ritagliata.](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ece8-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8ece8-114">Compiling the Code</span></span>  
 <span data-ttu-id="8ece8-115">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8ece8-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8ece8-116">Assicurarsi di sostituire `Apple.gif` con il nome e il percorso di un file di immagine validi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8ece8-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ece8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ece8-117">See also</span></span>

- [<span data-ttu-id="8ece8-118">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="8ece8-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="8ece8-119">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="8ece8-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
