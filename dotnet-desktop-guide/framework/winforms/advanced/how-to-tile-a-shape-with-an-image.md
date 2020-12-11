---
title: 'Procedura: Riempire una forma con immagini affiancate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962482"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="b5958-102">Procedura: Riempire una forma con immagini affiancate</span><span class="sxs-lookup"><span data-stu-id="b5958-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="b5958-103">Così come i riquadri possono essere posizionati uno accanto all'altro per coprire un pavimento, le immagini rettangolari possono essere posizionate l'una accanto all'altra per riempire (affiancare) una forma.</span><span class="sxs-lookup"><span data-stu-id="b5958-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="b5958-104">Per affiancare l'interno di una forma, utilizzare un pennello di trama.</span><span class="sxs-lookup"><span data-stu-id="b5958-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="b5958-105">Quando si costruisce un <xref:System.Drawing.TextureBrush> oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b5958-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="b5958-106">Quando si usa il pennello trama per disegnare l'interno di una forma, la forma viene riempita con copie ripetute dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b5958-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="b5958-107">La proprietà modalità a capo dell' <xref:System.Drawing.TextureBrush> oggetto determina il modo in cui l'immagine è orientata mentre viene ripetuta in una griglia rettangolare.</span><span class="sxs-lookup"><span data-stu-id="b5958-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="b5958-108">È possibile fare in modo che tutti i riquadri nella griglia abbiano lo stesso orientamento oppure è possibile far passare l'immagine da una posizione della griglia a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="b5958-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="b5958-109">Il capovolgimento può essere orizzontale, verticale o entrambi.</span><span class="sxs-lookup"><span data-stu-id="b5958-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="b5958-110">Gli esempi seguenti illustrano l'affiancamento con tipi diversi di capovolgimento.</span><span class="sxs-lookup"><span data-stu-id="b5958-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="b5958-111">Per affiancare un'immagine</span><span class="sxs-lookup"><span data-stu-id="b5958-111">To tile an image</span></span>  
  
- <span data-ttu-id="b5958-112">Questo esempio usa l'immagine 75 × 75 seguente per affiancare un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b5958-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![Immagine del riquadro che mostra una casa rossa e una struttura ad albero.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="b5958-114">Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato all'immagine.</span><span class="sxs-lookup"><span data-stu-id="b5958-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="b5958-115">Si noti che tutti i riquadri hanno lo stesso orientamento; Nessun capovolgimento.</span><span class="sxs-lookup"><span data-stu-id="b5958-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![Rettangolo affiancato all'immagine utilizzando lo stesso orientamento per tutti i riquadri.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="b5958-117">Per capovolgere un'immagine orizzontalmente durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="b5958-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="b5958-118">In questo esempio viene usata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b5958-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="b5958-119">La modalità a capo automatico è impostata per capovolgere orizzontalmente l'immagine.</span><span class="sxs-lookup"><span data-stu-id="b5958-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="b5958-120">Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato all'immagine.</span><span class="sxs-lookup"><span data-stu-id="b5958-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="b5958-121">Si noti che quando si passa da un riquadro all'altro in una determinata riga, l'immagine viene capovolta orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="b5958-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![Rettangolo affiancato all'immagine capovolto orizzontalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="b5958-123">Per capovolgere un'immagine verticalmente durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="b5958-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="b5958-124">In questo esempio viene usata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b5958-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="b5958-125">La modalità Wrap è impostata per capovolgere l'immagine verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b5958-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="b5958-126">Per capovolgere un'immagine orizzontalmente e verticalmente durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="b5958-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="b5958-127">In questo esempio viene usata la stessa immagine 75 × 75 per affiancare un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="b5958-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="b5958-128">La modalità a capo è impostata per capovolgere l'immagine sia orizzontalmente che verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b5958-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="b5958-129">Nella figura seguente viene illustrato il modo in cui il rettangolo viene affiancato dall'immagine.</span><span class="sxs-lookup"><span data-stu-id="b5958-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="b5958-130">Si noti che quando si passa da un riquadro all'altro in una determinata riga, l'immagine viene capovolta orizzontalmente e quando si passa da un riquadro all'altro in una colonna specificata, l'immagine viene capovolta verticalmente.</span><span class="sxs-lookup"><span data-stu-id="b5958-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![Rettangolo affiancato all'immagine capovolto orizzontalmente e verticalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="b5958-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5958-132">See also</span></span>

- [<span data-ttu-id="b5958-133">Utilizzo di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="b5958-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
