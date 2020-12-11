---
title: 'Procedura: Usare una tabella per modificare il mapping dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962461"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="ce5c5-102">Procedura: Usare una tabella per modificare il mapping dei colori</span><span class="sxs-lookup"><span data-stu-id="ce5c5-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="ce5c5-103">Il rimapping è il processo di conversione dei colori in un'immagine in base a una tabella di modifica del mapping dei colori.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="ce5c5-104">La tabella di modifica del mapping dei colori è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="ce5c5-105">Ogni <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice ha una <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e una <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="ce5c5-106">Quando GDI+ disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice dei colori precedenti.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="ce5c5-107">Se il colore di un pixel corrisponde a un colore precedente, il colore viene modificato nel nuovo colore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="ce5c5-108">I colori vengono modificati solo per il rendering: i valori dei colori dell'immagine stessa (archiviati in <xref:System.Drawing.Image> un <xref:System.Drawing.Bitmap> oggetto o) non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="ce5c5-109">Per tracciare un'immagine rimappata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="ce5c5-110">Passare la matrice al <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> oggetto, quindi passare l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce5c5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce5c5-111">Example</span></span>  
 <span data-ttu-id="ce5c5-112">Nell'esempio seguente viene creato un <xref:System.Drawing.Image> oggetto dal file RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="ce5c5-113">Il codice crea una tabella di modifica del mapping dei colori costituita da un singolo <xref:System.Drawing.Imaging.ColorMap> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="ce5c5-114">La <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà dell' `ColorRemap` oggetto è rossa e la <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è blu.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="ce5c5-115">L'immagine viene disegnata una volta senza modificarne il mapping e una volta con il mapping.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="ce5c5-116">Il processo di modifica del mapping modifica tutti i pixel rossi in blu.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="ce5c5-117">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine rimappata a destra.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![Screenshot che mostra l'immagine originale e l'immagine rimappata.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce5c5-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ce5c5-119">Compiling the Code</span></span>  
 <span data-ttu-id="ce5c5-120">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="ce5c5-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce5c5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce5c5-121">See also</span></span>

- [<span data-ttu-id="ce5c5-122">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="ce5c5-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="ce5c5-123">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="ce5c5-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
