---
title: Utilizzo dei contenitori di grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952763"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="d3abf-102">Utilizzo dei contenitori di grafica</span><span class="sxs-lookup"><span data-stu-id="d3abf-102">Using Graphics Containers</span></span>
<span data-ttu-id="d3abf-103">Un <xref:System.Drawing.Graphics> oggetto fornisce metodi come <xref:System.Drawing.Graphics.DrawLine%2A> , <xref:System.Drawing.Graphics.DrawImage%2A> e per la <xref:System.Drawing.Graphics.DrawString%2A> visualizzazione di immagini vettoriali, immagini raster e testo.</span><span class="sxs-lookup"><span data-stu-id="d3abf-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="d3abf-104">Un <xref:System.Drawing.Graphics> oggetto dispone inoltre di diverse proprietà che influenzano la qualità e l'orientamento degli elementi disegnati.</span><span class="sxs-lookup"><span data-stu-id="d3abf-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="d3abf-105">Ad esempio, la proprietà modalità di smussamento determina se l'anti-aliasing viene applicato a linee e curve e la proprietà trasformazione globale influisce sulla posizione e sulla rotazione degli elementi disegnati.</span><span class="sxs-lookup"><span data-stu-id="d3abf-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="d3abf-106">Un <xref:System.Drawing.Graphics> oggetto è associato a un dispositivo di visualizzazione specifico.</span><span class="sxs-lookup"><span data-stu-id="d3abf-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="d3abf-107">Quando si utilizza un <xref:System.Drawing.Graphics> oggetto da creare in una finestra, l' <xref:System.Drawing.Graphics> oggetto viene anche associato a tale finestra specifica.</span><span class="sxs-lookup"><span data-stu-id="d3abf-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="d3abf-108">Un <xref:System.Drawing.Graphics> oggetto può essere considerato come un contenitore perché include un set di proprietà che influenzano il disegno ed è collegato a informazioni specifiche del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3abf-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="d3abf-109">È possibile creare un contenitore secondario all'interno di un oggetto esistente chiamando <xref:System.Drawing.Graphics> il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di tale <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d3abf-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3abf-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d3abf-110">In This Section</span></span>  
 [<span data-ttu-id="d3abf-111">Gestione dello stato di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="d3abf-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="d3abf-112">Viene descritto come gestire le impostazioni di qualità, l'area di ridimensionamento e le trasformazioni di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d3abf-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="d3abf-113">Utilizzo di contenitori di grafica annidati</span><span class="sxs-lookup"><span data-stu-id="d3abf-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="d3abf-114">Viene illustrato come utilizzare i contenitori per controllare lo stato dell' <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d3abf-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
