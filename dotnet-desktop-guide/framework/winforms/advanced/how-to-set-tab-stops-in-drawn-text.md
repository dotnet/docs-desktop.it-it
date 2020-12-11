---
title: 'Procedura: Impostare tabulazioni nel testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962530"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="cda6c-102">Procedura: Impostare tabulazioni nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="cda6c-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="cda6c-103">È possibile impostare le tabulazioni per il testo chiamando il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo di un <xref:System.Drawing.StringFormat> oggetto e passando <xref:System.Drawing.StringFormat> l'oggetto al <xref:System.Drawing.Graphics.DrawString%2A> metodo della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="cda6c-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cda6c-104">Non <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> supporta l'aggiunta di tabulazioni al testo disegnato, sebbene sia possibile espandere le tabulazioni esistenti utilizzando il <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span><span class="sxs-lookup"><span data-stu-id="cda6c-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda6c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cda6c-105">Example</span></span>  
 <span data-ttu-id="cda6c-106">Nell'esempio seguente vengono impostate le tabulazioni a 150, 250 e 350.</span><span class="sxs-lookup"><span data-stu-id="cda6c-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="cda6c-107">Quindi, il codice visualizza un elenco a schede di nomi e punteggi dei test.</span><span class="sxs-lookup"><span data-stu-id="cda6c-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="cda6c-108">La figura seguente mostra il testo a schede:</span><span class="sxs-lookup"><span data-stu-id="cda6c-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Screenshot che mostra un elenco a schede di nomi e punteggi.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="cda6c-110">Il codice seguente passa due argomenti al <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="cda6c-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="cda6c-111">Il secondo argomento è una matrice che contiene offset di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="cda6c-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="cda6c-112">Il primo argomento passato a <xref:System.Drawing.StringFormat.SetTabStops%2A> è 0, che indica che il primo offset nella matrice viene misurato dalla posizione 0, dal bordo sinistro del rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="cda6c-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cda6c-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cda6c-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="cda6c-114">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="cda6c-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda6c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cda6c-115">See also</span></span>

- [<span data-ttu-id="cda6c-116">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="cda6c-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="cda6c-117">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="cda6c-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
