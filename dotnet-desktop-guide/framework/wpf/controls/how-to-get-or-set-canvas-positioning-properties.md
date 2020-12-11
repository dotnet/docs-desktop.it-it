---
title: 'Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961369"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="5c535-102">Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno</span><span class="sxs-lookup"><span data-stu-id="5c535-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="5c535-103">In questo esempio viene illustrato come utilizzare i metodi di posizionamento dell' <xref:System.Windows.Controls.Canvas> elemento per posizionare il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="5c535-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="5c535-104">In questo esempio viene utilizzato il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> per rappresentare i valori di posizionamento e i valori vengono convertiti in istanze di <xref:System.Double> , che è un argomento obbligatorio per il posizionamento.</span><span class="sxs-lookup"><span data-stu-id="5c535-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="5c535-105">I valori vengono quindi convertiti di nuovo in stringhe e visualizzati come testo in un <xref:System.Windows.Controls.TextBlock> elemento usando il <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="5c535-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c535-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c535-106">Example</span></span>  
 <span data-ttu-id="5c535-107">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ListBox> elemento con undici elementi selezionabili <xref:System.Windows.Controls.ListBoxItem> .</span><span class="sxs-lookup"><span data-stu-id="5c535-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="5c535-108">L' <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento attiva il `ChangeLeft` metodo personalizzato definito dal blocco di codice successivo.</span><span class="sxs-lookup"><span data-stu-id="5c535-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="5c535-109">Ogni <xref:System.Windows.Controls.ListBoxItem> oggetto rappresenta un <xref:System.Double> valore, ovvero uno degli argomenti <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> accettati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="5c535-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="5c535-110">Per poter utilizzare un oggetto <xref:System.Windows.Controls.ListBoxItem> per rappresentare un'istanza di <xref:System.Double> , è necessario innanzitutto convertire il <xref:System.Windows.Controls.ListBoxItem> tipo nel tipo di dati corretto.</span><span class="sxs-lookup"><span data-stu-id="5c535-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="5c535-111">Quando un utente modifica la <xref:System.Windows.Controls.ListBox> selezione, richiama il `ChangeLeft` metodo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5c535-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="5c535-112">Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Double> (si noti che questo valore è già stato convertito in un oggetto <xref:System.String> utilizzando il <xref:System.Windows.Controls.Control.ToString%2A> metodo).</span><span class="sxs-lookup"><span data-stu-id="5c535-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="5c535-113">Questo valore viene quindi passato nuovamente ai <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodi e <xref:System.Windows.Controls.Canvas.GetLeft%2A> di per <xref:System.Windows.Controls.Canvas> poter modificare la posizione dell' `text1` oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c535-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5c535-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c535-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="5c535-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="5c535-115">Panels Overview</span></span>](panels-overview.md)
