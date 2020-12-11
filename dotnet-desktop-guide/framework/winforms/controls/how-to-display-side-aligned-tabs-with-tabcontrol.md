---
title: 'Procedura: Visualizzare schede allineate lateralmente con TabControl'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tab pages [Windows Forms], displaying side-aligned tabs
- tabs [Windows Forms], displaying side-aligned tabs
- TabControl control [Windows Forms], displaying side-aligned tabs
ms.assetid: 110d5abd-3ae3-4ded-95bf-778aaac798a0
ms.openlocfilehash: d98c5906d99dff9371f8290e7dbc9c9011cd0c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961840"
---
# <a name="how-to-display-side-aligned-tabs-with-tabcontrol"></a><span data-ttu-id="9e8b4-102">Procedura: Visualizzare schede allineate lateralmente con TabControl</span><span class="sxs-lookup"><span data-stu-id="9e8b4-102">How to: Display Side-Aligned Tabs with TabControl</span></span>
<span data-ttu-id="9e8b4-103">La proprietà <xref:System.Windows.Forms.TabControl.Alignment%2A> di <xref:System.Windows.Forms.TabControl> supporta la visualizzazione di schede in verticale (lungo il bordo sinistro o destro del controllo) anziché in orizzontale (lungo la parte superiore o inferiore del controllo).</span><span class="sxs-lookup"><span data-stu-id="9e8b4-103">The <xref:System.Windows.Forms.TabControl.Alignment%2A> property of <xref:System.Windows.Forms.TabControl> supports displaying tabs vertically (along the left or right edge of the control), as opposed to horizontally (across the top or bottom of the control).</span></span> <span data-ttu-id="9e8b4-104">Per impostazione predefinita, questa visualizzazione verticale comporta un'esperienza utente non soddisfacente, perché la proprietà <xref:System.Windows.Forms.TabPage.Text%2A> dell'oggetto <xref:System.Windows.Forms.TabPage> non viene visualizzata nella scheda quando sono abilitati gli stili visivi.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-104">By default, this vertical display results in a poor user experience, because the <xref:System.Windows.Forms.TabPage.Text%2A> property of the <xref:System.Windows.Forms.TabPage> object does not display in the tab when visual styles are enabled.</span></span> <span data-ttu-id="9e8b4-105">Non esiste inoltre alcun modo diretto per controllare la direzione del testo all'interno della scheda. <xref:System.Windows.Forms.TabControl> Per migliorare questa esperienza, è possibile usare Owner Draw on.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-105">There is also no direct way to control the direction of the text within the tab. You can use owner draw on <xref:System.Windows.Forms.TabControl> to improve this experience.</span></span>  
  
 <span data-ttu-id="9e8b4-106">La procedura seguente mostra come eseguire il rendering di schede allineate a destra, con il testo della scheda visualizzato da sinistra a destra, usando la funzionalità "Owner Draw".</span><span class="sxs-lookup"><span data-stu-id="9e8b4-106">The following procedure shows how to render right-aligned tabs, with the tab text running from left to right, by using the "owner draw" feature.</span></span>  
  
### <a name="to-display-right-aligned-tabs"></a><span data-ttu-id="9e8b4-107">Per visualizzare le schede allineate a destra</span><span class="sxs-lookup"><span data-stu-id="9e8b4-107">To display right-aligned tabs</span></span>  
  
1. <span data-ttu-id="9e8b4-108">Aggiungere un oggetto <xref:System.Windows.Forms.TabControl> al form.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-108">Add a <xref:System.Windows.Forms.TabControl> to your form.</span></span>  
  
2. <span data-ttu-id="9e8b4-109">Impostare la proprietà <xref:System.Windows.Forms.TabControl.Alignment%2A> su <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-109">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property to <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
3. <span data-ttu-id="9e8b4-110">Impostare la proprietà <xref:System.Windows.Forms.TabControl.SizeMode%2A> su <xref:System.Windows.Forms.TabSizeMode.Fixed> in modo che tutte le schede siano della stessa larghezza.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-110">Set the <xref:System.Windows.Forms.TabControl.SizeMode%2A> property to <xref:System.Windows.Forms.TabSizeMode.Fixed>, so that all tabs are the same width.</span></span>  
  
4. <span data-ttu-id="9e8b4-111">Impostare la proprietà <xref:System.Windows.Forms.TabControl.ItemSize%2A> sulle dimensioni fisse preferite per le schede.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-111">Set the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property to the preferred fixed size for the tabs.</span></span> <span data-ttu-id="9e8b4-112">Tenere presente che la proprietà <xref:System.Windows.Forms.TabControl.ItemSize%2A> si comporta come se le schede si trovassero nella parte superiore, sebbene siano allineate a destra.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-112">Keep in mind that the <xref:System.Windows.Forms.TabControl.ItemSize%2A> property behaves as though the tabs were on top, although they are right-aligned.</span></span> <span data-ttu-id="9e8b4-113">Di conseguenza, per aumentare la larghezza delle schede, è necessario modificare la proprietà <xref:System.Drawing.Size.Height%2A> mentre, per aumentarne l'altezza, è necessario modificare la proprietà <xref:System.Drawing.Size.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-113">As a result, in order to make the tabs wider, you must change the <xref:System.Drawing.Size.Height%2A> property, and in order to make them taller, you must change the <xref:System.Drawing.Size.Width%2A> property.</span></span>  
  
     <span data-ttu-id="9e8b4-114">Per ottenere risultati migliori con l'esempio di codice riportato di seguito, impostare <xref:System.Drawing.Size.Width%2A> delle schede su 25 e <xref:System.Drawing.Size.Height%2A> su 100.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-114">For best result with the code example below, set the <xref:System.Drawing.Size.Width%2A> of the tabs to 25 and the <xref:System.Drawing.Size.Height%2A> to 100.</span></span>  
  
5. <span data-ttu-id="9e8b4-115">Impostare la proprietà <xref:System.Windows.Forms.TabControl.DrawMode%2A> su <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-115">Set the <xref:System.Windows.Forms.TabControl.DrawMode%2A> property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>.</span></span>  
  
6. <span data-ttu-id="9e8b4-116">Definire un gestore per l'evento <xref:System.Windows.Forms.TabControl.DrawItem> di <xref:System.Windows.Forms.TabControl> che esegue il rendering del testo da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="9e8b4-116">Define a handler for the <xref:System.Windows.Forms.TabControl.DrawItem> event of <xref:System.Windows.Forms.TabControl> that renders the text from left to right.</span></span>  
  
     [!code-csharp[TabControl.RightAlignedTabs#1](~/samples/snippets/csharp/VS_Snippets_Winforms/TabControl.RightAlignedTabs/CS/Form1.cs#1)]
     [!code-vb[TabControl.RightAlignedTabs#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/TabControl.RightAlignedTabs/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9e8b4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e8b4-117">See also</span></span>

- [<span data-ttu-id="9e8b4-118">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="9e8b4-118">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
