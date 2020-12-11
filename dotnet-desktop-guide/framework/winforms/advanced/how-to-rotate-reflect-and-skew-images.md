---
title: 'Procedura: Ruotare, capovolgere e inclinare immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962539"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="ad11a-102">Procedura: Ruotare, capovolgere e inclinare immagini</span><span class="sxs-lookup"><span data-stu-id="ad11a-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="ad11a-103">È possibile ruotare, riflettere e inclinare un'immagine specificando punti di destinazione per gli angoli superiore sinistro, superiore destro e inferiore sinistro dell'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="ad11a-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="ad11a-104">I tre punti di destinazione determinano una trasformazione affine che esegue il mapping dell'immagine rettangolare originale a un parallelogramma.</span><span class="sxs-lookup"><span data-stu-id="ad11a-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad11a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad11a-105">Example</span></span>  
 <span data-ttu-id="ad11a-106">Si supponga, ad esempio, che l'immagine originale sia un rettangolo con angolo superiore sinistro in corrispondenza di (0, 0), angolo superiore destro in corrispondenza di (100, 0) e angolo inferiore sinistro in (0, 50).</span><span class="sxs-lookup"><span data-stu-id="ad11a-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="ad11a-107">Si supponga ora di eseguire il mapping di questi tre punti ai punti di destinazione come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ad11a-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="ad11a-108">Punto originale</span><span class="sxs-lookup"><span data-stu-id="ad11a-108">Original point</span></span>|<span data-ttu-id="ad11a-109">Punto di destinazione</span><span class="sxs-lookup"><span data-stu-id="ad11a-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="ad11a-110">Superiore sinistro (0,0)</span><span class="sxs-lookup"><span data-stu-id="ad11a-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="ad11a-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="ad11a-111">(200, 20)</span></span>|  
|<span data-ttu-id="ad11a-112">In alto a destra (100, 0)</span><span class="sxs-lookup"><span data-stu-id="ad11a-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="ad11a-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="ad11a-113">(110, 100)</span></span>|  
|<span data-ttu-id="ad11a-114">In basso a sinistra (0, 50)</span><span class="sxs-lookup"><span data-stu-id="ad11a-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="ad11a-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="ad11a-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="ad11a-116">La figura seguente mostra l'immagine originale e l'immagine mappata al parallelogramma.</span><span class="sxs-lookup"><span data-stu-id="ad11a-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="ad11a-117">L'immagine originale è stata inclinata, riflessa, ruotata e convertita.</span><span class="sxs-lookup"><span data-stu-id="ad11a-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="ad11a-118">L'asse x lungo il bordo superiore dell'immagine originale viene mappato alla riga che esegue fino a (200, 20) e (110, 100).</span><span class="sxs-lookup"><span data-stu-id="ad11a-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="ad11a-119">L'asse y lungo il bordo sinistro dell'immagine originale viene mappato alla riga che esegue fino a (200, 20) e (250, 30).</span><span class="sxs-lookup"><span data-stu-id="ad11a-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![Immagine originale e immagine mappata al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="ad11a-121">Nella figura seguente viene illustrata una trasformazione simile applicata a un'immagine fotografica:</span><span class="sxs-lookup"><span data-stu-id="ad11a-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![Immagine di un scalatore e immagine mappata al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="ad11a-123">Nella figura seguente viene illustrata una trasformazione simile applicata a un metafile:</span><span class="sxs-lookup"><span data-stu-id="ad11a-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![Illustrazione di forme e testo e di cui è stato eseguito il mapping al parallelogramma.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="ad11a-125">Nell'esempio seguente vengono generate le immagini mostrate nella prima illustrazione.</span><span class="sxs-lookup"><span data-stu-id="ad11a-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad11a-126">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ad11a-126">Compiling the Code</span></span>  
 <span data-ttu-id="ad11a-127">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="ad11a-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ad11a-128">Assicurarsi di sostituire `Stripes.bmp` con il percorso di un'immagine valida nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ad11a-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad11a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad11a-129">See also</span></span>

- [<span data-ttu-id="ad11a-130">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="ad11a-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
