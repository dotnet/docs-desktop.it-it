---
title: Utilizzo delle trasformazioni per scalare i colori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962371"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="0f60b-102">Utilizzo delle trasformazioni per scalare i colori</span><span class="sxs-lookup"><span data-stu-id="0f60b-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="0f60b-103">Una trasformazione di ridimensionamento moltiplica uno o più dei quattro componenti colore per numero.</span><span class="sxs-lookup"><span data-stu-id="0f60b-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="0f60b-104">Nella tabella seguente vengono fornite le voci della matrice di colori che rappresentano il ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="0f60b-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="0f60b-105">Componente da ridimensionare</span><span class="sxs-lookup"><span data-stu-id="0f60b-105">Component to be scaled</span></span>|<span data-ttu-id="0f60b-106">Voce matrice</span><span class="sxs-lookup"><span data-stu-id="0f60b-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="0f60b-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="0f60b-107">Red</span></span>|<span data-ttu-id="0f60b-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="0f60b-108">[0][0]</span></span>|  
|<span data-ttu-id="0f60b-109">Green</span><span class="sxs-lookup"><span data-stu-id="0f60b-109">Green</span></span>|<span data-ttu-id="0f60b-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="0f60b-110">[1][1]</span></span>|  
|<span data-ttu-id="0f60b-111">Blu</span><span class="sxs-lookup"><span data-stu-id="0f60b-111">Blue</span></span>|<span data-ttu-id="0f60b-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="0f60b-112">[2][2]</span></span>|  
|<span data-ttu-id="0f60b-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="0f60b-113">Alpha</span></span>|<span data-ttu-id="0f60b-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="0f60b-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="0f60b-115">Ridimensionamento di un colore</span><span class="sxs-lookup"><span data-stu-id="0f60b-115">Scaling One Color</span></span>  
 <span data-ttu-id="0f60b-116">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="0f60b-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="0f60b-117">Quindi il codice ridimensiona il componente blu di ogni pixel nell'immagine per un fattore di 2.</span><span class="sxs-lookup"><span data-stu-id="0f60b-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="0f60b-118">L'immagine originale viene disegnata insieme all'immagine trasformata.</span><span class="sxs-lookup"><span data-stu-id="0f60b-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="0f60b-119">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine ridimensionata a destra:</span><span class="sxs-lookup"><span data-stu-id="0f60b-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e scalati.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="0f60b-121">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu.</span><span class="sxs-lookup"><span data-stu-id="0f60b-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="0f60b-122">Si noti che il componente blu nella quarta barra dei colori è stato compreso tra 0,8 e 0,6.</span><span class="sxs-lookup"><span data-stu-id="0f60b-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="0f60b-123">Ciò è dovuto al fatto che GDI+ mantiene solo la parte frazionaria del risultato.</span><span class="sxs-lookup"><span data-stu-id="0f60b-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="0f60b-124">Ad esempio, (2) (0.8) = 1,6 e la parte frazionaria di 1,6 è 0,6.</span><span class="sxs-lookup"><span data-stu-id="0f60b-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="0f60b-125">La conservazione solo della parte frazionaria garantisce che il risultato sia sempre nell'intervallo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="0f60b-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="0f60b-126">Originale</span><span class="sxs-lookup"><span data-stu-id="0f60b-126">Original</span></span>|<span data-ttu-id="0f60b-127">Ridimensionato</span><span class="sxs-lookup"><span data-stu-id="0f60b-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="0f60b-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="0f60b-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="0f60b-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="0f60b-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="0f60b-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="0f60b-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="0f60b-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="0f60b-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="0f60b-136">Ridimensionamento di più colori</span><span class="sxs-lookup"><span data-stu-id="0f60b-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="0f60b-137">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="0f60b-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="0f60b-138">Il codice Ridimensiona quindi i componenti rosso, verde e blu di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0f60b-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="0f60b-139">I componenti rossi vengono ridimensionati fino al 25%, i componenti verdi vengono ridimensionati fino al 35% e i componenti blu vengono ridimensionati fino al 50%.</span><span class="sxs-lookup"><span data-stu-id="0f60b-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="0f60b-140">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine ridimensionata a destra:</span><span class="sxs-lookup"><span data-stu-id="0f60b-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e scalati.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="0f60b-142">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="0f60b-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="0f60b-143">Originale</span><span class="sxs-lookup"><span data-stu-id="0f60b-143">Original</span></span>|<span data-ttu-id="0f60b-144">Ridimensionato</span><span class="sxs-lookup"><span data-stu-id="0f60b-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="0f60b-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="0f60b-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="0f60b-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="0f60b-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="0f60b-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="0f60b-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="0f60b-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="0f60b-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="0f60b-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f60b-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f60b-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="0f60b-154">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f60b-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="0f60b-155">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="0f60b-155">Recoloring Images</span></span>](recoloring-images.md)
