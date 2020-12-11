---
title: 'Procedura: Creare miniature'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951471"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="4410e-102">Procedura: Creare miniature</span><span class="sxs-lookup"><span data-stu-id="4410e-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="4410e-103">Un'immagine di anteprima è una versione ridotta di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="4410e-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="4410e-104">È possibile creare un'immagine di anteprima chiamando il <xref:System.Drawing.Image.GetThumbnailImage%2A> metodo di un <xref:System.Drawing.Image> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4410e-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4410e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4410e-105">Example</span></span>  
 <span data-ttu-id="4410e-106">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto da un file jpg.</span><span class="sxs-lookup"><span data-stu-id="4410e-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="4410e-107">L'immagine originale ha una larghezza di 640 pixel e un'altezza di 479 pixel.</span><span class="sxs-lookup"><span data-stu-id="4410e-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="4410e-108">Il codice crea un'immagine di anteprima con una larghezza di 100 pixel e un'altezza di 100 pixel.</span><span class="sxs-lookup"><span data-stu-id="4410e-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="4410e-109">Nell'illustrazione seguente viene mostrata l'immagine di anteprima:</span><span class="sxs-lookup"><span data-stu-id="4410e-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Screenshot che mostra l'anteprima di output.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> <span data-ttu-id="4410e-111">In questo esempio viene dichiarato un metodo di callback, che non viene mai usato.</span><span class="sxs-lookup"><span data-stu-id="4410e-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="4410e-112">Supporta tutte le versioni di GDI+.</span><span class="sxs-lookup"><span data-stu-id="4410e-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4410e-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4410e-113">Compiling the Code</span></span>  
 <span data-ttu-id="4410e-114">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4410e-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4410e-115">Per eseguire l'esempio, attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="4410e-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="4410e-116">Creare una nuova applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4410e-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="4410e-117">Aggiungere il codice di esempio al modulo.</span><span class="sxs-lookup"><span data-stu-id="4410e-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="4410e-118">Creare un gestore per l'evento del form <xref:System.Windows.Forms.Control.Paint></span><span class="sxs-lookup"><span data-stu-id="4410e-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="4410e-119">Nel <xref:System.Windows.Forms.Control.Paint> gestore chiamare il `GetThumbnail` metodo e passare `e` per <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="4410e-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="4410e-120">Trovare un file di immagine di cui si vuole eseguire un'anteprima.</span><span class="sxs-lookup"><span data-stu-id="4410e-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="4410e-121">Nel `GetThumbnail` Metodo specificare il percorso e il nome file dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="4410e-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="4410e-122">Premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="4410e-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="4410e-123">Viene visualizzata un'immagine di anteprima 100 per 100 nel form.</span><span class="sxs-lookup"><span data-stu-id="4410e-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4410e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4410e-124">See also</span></span>

- [<span data-ttu-id="4410e-125">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="4410e-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="4410e-126">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="4410e-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
