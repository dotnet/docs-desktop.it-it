---
title: 'Procedura: Convertire i colori delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963232"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="dc06d-102">Procedura: Convertire i colori delle immagini</span><span class="sxs-lookup"><span data-stu-id="dc06d-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="dc06d-103">Una traduzione aggiunge un valore a uno o più dei quattro componenti del colore.</span><span class="sxs-lookup"><span data-stu-id="dc06d-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="dc06d-104">Nella tabella seguente vengono fornite le voci della matrice di colori che rappresentano le traduzioni.</span><span class="sxs-lookup"><span data-stu-id="dc06d-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="dc06d-105">Componente da tradurre</span><span class="sxs-lookup"><span data-stu-id="dc06d-105">Component to be translated</span></span>|<span data-ttu-id="dc06d-106">Voce matrice</span><span class="sxs-lookup"><span data-stu-id="dc06d-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="dc06d-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="dc06d-107">Red</span></span>|<span data-ttu-id="dc06d-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="dc06d-108">[4][0]</span></span>|  
|<span data-ttu-id="dc06d-109">Green</span><span class="sxs-lookup"><span data-stu-id="dc06d-109">Green</span></span>|<span data-ttu-id="dc06d-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="dc06d-110">[4][1]</span></span>|  
|<span data-ttu-id="dc06d-111">Blu</span><span class="sxs-lookup"><span data-stu-id="dc06d-111">Blue</span></span>|<span data-ttu-id="dc06d-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="dc06d-112">[4][2]</span></span>|  
|<span data-ttu-id="dc06d-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="dc06d-113">Alpha</span></span>|<span data-ttu-id="dc06d-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="dc06d-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dc06d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc06d-115">Example</span></span>  
 <span data-ttu-id="dc06d-116">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="dc06d-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="dc06d-117">Il codice aggiunge quindi 0,75 al componente rosso di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="dc06d-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="dc06d-118">L'immagine originale viene disegnata insieme all'immagine trasformata.</span><span class="sxs-lookup"><span data-stu-id="dc06d-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="dc06d-119">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine trasformata a destra:</span><span class="sxs-lookup"><span data-stu-id="dc06d-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![Screenshot dell'immagine originale e trasformata.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="dc06d-121">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la traduzione rossa.</span><span class="sxs-lookup"><span data-stu-id="dc06d-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="dc06d-122">Si noti che poiché il valore massimo per un componente colore è 1, il componente rosso nella seconda riga non cambia.</span><span class="sxs-lookup"><span data-stu-id="dc06d-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="dc06d-123">Analogamente, il valore minimo per un componente colore è 0.</span><span class="sxs-lookup"><span data-stu-id="dc06d-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="dc06d-124">Originale</span><span class="sxs-lookup"><span data-stu-id="dc06d-124">Original</span></span>|<span data-ttu-id="dc06d-125">Convertito</span><span class="sxs-lookup"><span data-stu-id="dc06d-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="dc06d-126">Nero (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="dc06d-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="dc06d-128">Rosso (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="dc06d-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="dc06d-130">Verde (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="dc06d-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="dc06d-132">Blu (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="dc06d-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="dc06d-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc06d-134">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dc06d-134">Compiling the Code</span></span>  
 <span data-ttu-id="dc06d-135">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="dc06d-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="dc06d-136">Sostituire `ColorBars.bmp` con il nome e il percorso di un file di immagine validi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="dc06d-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc06d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc06d-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="dc06d-138">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="dc06d-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="dc06d-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="dc06d-139">Recoloring Images</span></span>](recoloring-images.md)
