---
title: 'Procedura: Ottenere le misure dei tipi di carattere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963331"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="4497e-102">Procedura: Ottenere le misure dei tipi di carattere</span><span class="sxs-lookup"><span data-stu-id="4497e-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="4497e-103">La <xref:System.Drawing.FontFamily> classe fornisce i metodi seguenti che recuperano varie metriche per una particolare combinazione famiglia/stile:</span><span class="sxs-lookup"><span data-stu-id="4497e-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="4497e-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="4497e-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="4497e-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="4497e-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="4497e-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="4497e-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="4497e-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>FontStyle</span><span class="sxs-lookup"><span data-stu-id="4497e-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="4497e-108">I valori restituiti da questi metodi sono nelle unità di progettazione dei tipi di carattere, quindi sono indipendenti dalle dimensioni e dalle unità di un <xref:System.Drawing.Font> oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="4497e-108">The values returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="4497e-109">Nella figura seguente sono illustrate le diverse metriche:</span><span class="sxs-lookup"><span data-stu-id="4497e-109">The following illustration shows the various metrics:</span></span>
  
 ![Illustrazione delle metriche dei tipi di carattere: ascesa, discesa e interlinea.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="4497e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4497e-111">Example</span></span>  
 <span data-ttu-id="4497e-112">Nell'esempio seguente vengono visualizzate le metriche per lo stile regolare della famiglia di caratteri Arial.</span><span class="sxs-lookup"><span data-stu-id="4497e-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="4497e-113">Il codice crea anche un <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni pari a 16 pixel e visualizza le metriche (in pixel) per quel particolare <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4497e-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="4497e-114">Nella figura seguente viene illustrato l'output del codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="4497e-114">The following illustration shows the output of the example code:</span></span>
  
 ![Esempio di output di codice per le metriche dei tipi di carattere Arial.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="4497e-116">Prendere nota delle prime due righe di output nell'illustrazione precedente.</span><span class="sxs-lookup"><span data-stu-id="4497e-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="4497e-117">L' <xref:System.Drawing.Font> oggetto restituisce una dimensione di 16 e l' <xref:System.Drawing.FontFamily> oggetto restituisce un'altezza em di 2.048.</span><span class="sxs-lookup"><span data-stu-id="4497e-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="4497e-118">Questi due numeri (16 e 2.048) rappresentano la chiave per la conversione tra le unità di progettazione dei tipi di carattere e le unità (in questo caso pixel) dell' <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4497e-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="4497e-119">Ad esempio, è possibile convertire l'ascesa da unità di progettazione a pixel come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4497e-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![Formula che mostra la conversione da unità di progettazione a pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="4497e-121">Il codice seguente posiziona il testo verticalmente impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4497e-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="4497e-122">La coordinata y viene aumentata da `font.Height` per ogni nuova riga di testo.</span><span class="sxs-lookup"><span data-stu-id="4497e-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="4497e-123">La <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> oggetto restituisce l'interlinea (in pixel) per quel particolare <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4497e-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="4497e-124">In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19.</span><span class="sxs-lookup"><span data-stu-id="4497e-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="4497e-125">Si noti che questo è lo stesso numero (arrotondato per eccesso a un numero intero) ottenuto convertendo la metrica di spaziatura riga in pixel.</span><span class="sxs-lookup"><span data-stu-id="4497e-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="4497e-126">Si noti che l'altezza em (detta anche dimensioni o dimensioni em) non è la somma dell'ascesa e della discesa.</span><span class="sxs-lookup"><span data-stu-id="4497e-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="4497e-127">La somma dell'ascesa e della discesa è detta altezza della cella.</span><span class="sxs-lookup"><span data-stu-id="4497e-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="4497e-128">L'altezza della cella meno la porta interna è uguale all'altezza em.</span><span class="sxs-lookup"><span data-stu-id="4497e-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="4497e-129">L'altezza della cella più la porta esterna è uguale all'interlinea.</span><span class="sxs-lookup"><span data-stu-id="4497e-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4497e-130">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4497e-130">Compiling the Code</span></span>  
 <span data-ttu-id="4497e-131">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="4497e-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4497e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4497e-132">See also</span></span>

- [<span data-ttu-id="4497e-133">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4497e-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4497e-134">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="4497e-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
