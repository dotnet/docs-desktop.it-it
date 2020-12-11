---
title: Linee e riempimenti con fusione alfa
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952254"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="54c51-102">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="54c51-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="54c51-103">In GDI+, un colore è un valore a 32 bit con 8 bit ciascuno per Alpha, rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="54c51-103">In GDI+, a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="54c51-104">Il valore alfa indica la trasparenza del colore, ovvero la misura in cui il colore viene mescolato con il colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="54c51-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="54c51-105">I valori alfa variano da 0 a 255, dove 0 rappresenta un colore completamente trasparente e 255 rappresenta un colore completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="54c51-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="54c51-106">La fusione alfa è una combinazione pixel per pixel dei dati di origine e di colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="54c51-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="54c51-107">Ognuno dei tre componenti (rosso, verde, blu) di un determinato colore di origine viene mescolato con il componente corrispondente del colore di sfondo in base alla formula seguente:</span><span class="sxs-lookup"><span data-stu-id="54c51-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="54c51-108">displayColor = sourceColor × Alpha/255 + backgroundColor × (255 – Alpha)/255</span><span class="sxs-lookup"><span data-stu-id="54c51-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="54c51-109">Si supponga, ad esempio, che il componente rosso del colore di origine sia 150 e che il componente rosso del colore di sfondo sia 100.</span><span class="sxs-lookup"><span data-stu-id="54c51-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="54c51-110">Se il valore alfa è 200, il componente rosso del colore risultante viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="54c51-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="54c51-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="54c51-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54c51-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="54c51-112">In This Section</span></span>  
 [<span data-ttu-id="54c51-113">Procedura: Disegnare linee opache e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="54c51-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="54c51-114">Viene illustrato come creare linee con Blend alfa.</span><span class="sxs-lookup"><span data-stu-id="54c51-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="54c51-115">Procedura: Disegnare con pennelli opachi e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="54c51-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="54c51-116">Viene illustrato come alfa-blend con i pennelli.</span><span class="sxs-lookup"><span data-stu-id="54c51-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="54c51-117">Procedura: Usare la modalità di composizione per controllare la fusione alfa</span><span class="sxs-lookup"><span data-stu-id="54c51-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="54c51-118">Viene descritto come controllare la fusione alfa usando <xref:System.Drawing.Drawing2D.CompositingMode> .</span><span class="sxs-lookup"><span data-stu-id="54c51-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="54c51-119">Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini</span><span class="sxs-lookup"><span data-stu-id="54c51-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="54c51-120">Viene illustrato come usare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto per controllare la fusione alfa.</span><span class="sxs-lookup"><span data-stu-id="54c51-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
