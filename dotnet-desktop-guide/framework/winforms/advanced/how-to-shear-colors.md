---
title: 'Procedura: Variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962515"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="975eb-102">Procedura: Variare le componenti cromatiche</span><span class="sxs-lookup"><span data-stu-id="975eb-102">How to: Shear Colors</span></span>
<span data-ttu-id="975eb-103">Il taglio aumenta o diminuisce un componente colore di un importo proporzionale a un altro componente colore.</span><span class="sxs-lookup"><span data-stu-id="975eb-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="975eb-104">Si consideri, ad esempio, la trasformazione in cui il componente rosso viene aumentato di una metà del valore del componente blu.</span><span class="sxs-lookup"><span data-stu-id="975eb-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="975eb-105">In tale trasformazione, il colore (0,2, 0,5, 1) diventerà (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="975eb-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="975eb-106">Il nuovo componente rosso è 0,2 + (1/2) (1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="975eb-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="975eb-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="975eb-107">Example</span></span>  
 <span data-ttu-id="975eb-108">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="975eb-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="975eb-109">Il codice applica quindi la trasformazione di taglio descritta nel paragrafo precedente a ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="975eb-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="975eb-110">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine tranciata a destra:</span><span class="sxs-lookup"><span data-stu-id="975eb-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![Due quadrati con strip colorati affiancati che illustrano l'immagine originale e l'immagine tranciata.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="975eb-112">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la trasformazione di taglio.</span><span class="sxs-lookup"><span data-stu-id="975eb-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="975eb-113">Originale</span><span class="sxs-lookup"><span data-stu-id="975eb-113">Original</span></span>|<span data-ttu-id="975eb-114">Tranciati</span><span class="sxs-lookup"><span data-stu-id="975eb-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="975eb-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="975eb-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="975eb-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="975eb-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="975eb-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="975eb-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="975eb-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="975eb-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="975eb-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="975eb-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="975eb-123">Compiling the Code</span></span>  
 <span data-ttu-id="975eb-124">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="975eb-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="975eb-125">Sostituire `ColorBars.bmp` con il nome e il percorso di un'immagine validi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="975eb-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975eb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="975eb-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="975eb-127">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="975eb-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="975eb-128">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="975eb-128">Recoloring Images</span></span>](recoloring-images.md)
