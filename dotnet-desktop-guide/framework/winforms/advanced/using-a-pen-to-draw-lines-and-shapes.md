---
title: Utilizzo di un oggetto Pen per creare linee e forme
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: d20b4e47c9f8a5dd7a144e6ebb3151d3ab65a800
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952776"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="fae1c-102">Utilizzo di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="fae1c-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="fae1c-103">Usare `Pen` gli oggetti GDI+ per creare segmenti di linea, curve e strutture di forme.</span><span class="sxs-lookup"><span data-stu-id="fae1c-103">Use GDI+ `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="fae1c-104">In questa sezione la *riga* fa riferimento a una di queste, a meno che non sia specificato solo un segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="fae1c-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="fae1c-105">Impostare le proprietà di una penna per controllare il colore, la larghezza, l'allineamento e lo stile delle linee disegnate con tale penna.</span><span class="sxs-lookup"><span data-stu-id="fae1c-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fae1c-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fae1c-106">In This Section</span></span>  
 [<span data-ttu-id="fae1c-107">Procedura: Usare un oggetto Pen per disegnare linee</span><span class="sxs-lookup"><span data-stu-id="fae1c-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="fae1c-108">Viene illustrato come creare linee.</span><span class="sxs-lookup"><span data-stu-id="fae1c-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="fae1c-109">Procedura: Usare un oggetto Pen per disegnare rettangoli</span><span class="sxs-lookup"><span data-stu-id="fae1c-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="fae1c-110">Viene descritto come creare rettangoli.</span><span class="sxs-lookup"><span data-stu-id="fae1c-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="fae1c-111">Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="fae1c-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="fae1c-112">Viene illustrato come modificare la larghezza e l'allineamento di un `Pen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="fae1c-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="fae1c-113">Procedura: Disegnare una linea con estremità</span><span class="sxs-lookup"><span data-stu-id="fae1c-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="fae1c-114">Viene descritto come aggiungere i tappi finali durante il disegno di una linea.</span><span class="sxs-lookup"><span data-stu-id="fae1c-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="fae1c-115">Procedura: Unire le linee</span><span class="sxs-lookup"><span data-stu-id="fae1c-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="fae1c-116">Mostra come unire due righe.</span><span class="sxs-lookup"><span data-stu-id="fae1c-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="fae1c-117">Procedura: Disegnare una linea tratteggiata personalizzata</span><span class="sxs-lookup"><span data-stu-id="fae1c-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="fae1c-118">Viene descritto come creare una linea tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="fae1c-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="fae1c-119">Procedura: Disegnare una linea con riempimento a trama</span><span class="sxs-lookup"><span data-stu-id="fae1c-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="fae1c-120">Viene illustrato come creare una linea riempita da trama.</span><span class="sxs-lookup"><span data-stu-id="fae1c-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fae1c-121">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="fae1c-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="fae1c-122">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="fae1c-122">Describes this class and has links to all its members.</span></span>
