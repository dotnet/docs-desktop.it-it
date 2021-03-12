---
title: 'Procedura: creare testo con contorni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 12da12320a09fa825d9c75d4a6e5e3264724de77
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604352"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="1de5b-102">Procedura: creare testo delineato</span><span class="sxs-lookup"><span data-stu-id="1de5b-102">How to: Create outlined text</span></span>

<span data-ttu-id="1de5b-103">Nella maggior parte dei casi, quando si aggiunge l'ornamento alle stringhe di testo nell' [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applicazione, si usa il testo in termini di una raccolta di caratteri discreti o di glifi.</span><span class="sxs-lookup"><span data-stu-id="1de5b-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="1de5b-104">Ad esempio, è possibile creare un pennello sfumato lineare e applicarlo alla <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.TextBox> oggetto.</span><span class="sxs-lookup"><span data-stu-id="1de5b-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="1de5b-105">Quando si visualizza o si modifica la casella di testo, il pennello sfumatura lineare viene applicato automaticamente al set di caratteri corrente nella stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="1de5b-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![Testo visualizzato con pennello sfumato lineare](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="1de5b-107">Tuttavia, è anche possibile convertire il testo in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo visivamente RTF.</span><span class="sxs-lookup"><span data-stu-id="1de5b-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="1de5b-108">Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="1de5b-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![Struttura di testo con pennello sfumato lineare](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="1de5b-110">Quando il testo viene convertito in un <xref:System.Windows.Media.Geometry> oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="1de5b-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="1de5b-111">Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento.</span><span class="sxs-lookup"><span data-stu-id="1de5b-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="1de5b-112">Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="1de5b-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="1de5b-113">Negli esempi seguenti vengono illustrati diversi modi per creare effetti visivi modificando il tratto e il riempimento del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="1de5b-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![Testo con colori diversi per tratto e riempimento](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="1de5b-116">È anche possibile modificare il rettangolo delimitatore del testo convertito o evidenziarlo.</span><span class="sxs-lookup"><span data-stu-id="1de5b-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="1de5b-117">Nell'esempio seguente viene illustrato un modo per creare effetti visivi modificando il tratto e l'evidenziazione del testo convertito.</span><span class="sxs-lookup"><span data-stu-id="1de5b-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![Testo con pennello immagine applicato al tratto ed evidenziato](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="1de5b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de5b-119">Example</span></span>  
 <span data-ttu-id="1de5b-120">La chiave per la conversione di testo in un <xref:System.Windows.Media.Geometry> oggetto consiste nell'utilizzare l' <xref:System.Windows.Media.FormattedText> oggetto.</span><span class="sxs-lookup"><span data-stu-id="1de5b-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="1de5b-121">Dopo aver creato questo oggetto, è possibile usare i <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> metodi e <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> per convertire il testo in <xref:System.Windows.Media.Geometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="1de5b-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="1de5b-122">Il primo metodo restituisce la geometria del testo formattato; il secondo metodo restituisce la geometria del rettangolo di delimitazione del testo formattato.</span><span class="sxs-lookup"><span data-stu-id="1de5b-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="1de5b-123">Nell'esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie del testo formattato e il relativo rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="1de5b-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="1de5b-124">Per visualizzare gli oggetti recuperati <xref:System.Windows.Media.Geometry> , è necessario accedere al <xref:System.Windows.Media.DrawingContext> dell'oggetto che sta visualizzando il testo convertito.</span><span class="sxs-lookup"><span data-stu-id="1de5b-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="1de5b-125">In questi esempi di codice, questo accesso viene ottenuto creando un oggetto controllo personalizzato derivato da una classe che supporta il rendering definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1de5b-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="1de5b-126">Per visualizzare <xref:System.Windows.Media.Geometry> gli oggetti nel controllo personalizzato, specificare una sostituzione per il <xref:System.Windows.UIElement.OnRender%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="1de5b-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="1de5b-127">Il metodo sottoposto a override deve usare il <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> metodo per creare gli <xref:System.Windows.Media.Geometry> oggetti.</span><span class="sxs-lookup"><span data-stu-id="1de5b-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="1de5b-128">Per l'origine dell'oggetto controllo utente personalizzato di esempio, vedere [OutlineTextControl.cs per C#](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) e [OutlineTextControl. vb per Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span><span class="sxs-lookup"><span data-stu-id="1de5b-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1de5b-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1de5b-129">See also</span></span>

- [<span data-ttu-id="1de5b-130">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="1de5b-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
