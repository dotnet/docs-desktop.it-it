---
title: "Procedura: Gestire l'overflow di ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952092"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="12891-102">Procedura: gestire l'overflow di ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="12891-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="12891-103">Quando tutti gli elementi di un <xref:System.Windows.Forms.ToolStrip> controllo non rientrano nello spazio assegnato, è possibile abilitare la funzionalità di overflow su <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di specifici <xref:System.Windows.Forms.ToolStripItem> .</span><span class="sxs-lookup"><span data-stu-id="12891-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="12891-104">Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem> che richiedono più spazio rispetto a quello assegnato a <xref:System.Windows.Forms.ToolStrip> , date le dimensioni correnti del modulo, <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato automaticamente un oggetto in <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="12891-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="12891-105">Il <xref:System.Windows.Forms.ToolStripOverflowButton> viene visualizzato e gli elementi abilitati per l'overflow vengono spostati nel menu a discesa di overflow.</span><span class="sxs-lookup"><span data-stu-id="12891-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="12891-106">In questo modo è possibile personalizzare e definire le priorità <xref:System.Windows.Forms.ToolStrip> per adattare correttamente gli elementi alle diverse dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="12891-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="12891-107">È anche possibile modificare l'aspetto degli elementi quando rientrano nell'overflow usando le <xref:System.Windows.Forms.ToolStripItem.Placement%2A> <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> proprietà e e l' <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="12891-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="12891-108">Se si ingrandisce il form in fase di progettazione o in fase di esecuzione, è possibile visualizzare più istanze di nel <xref:System.Windows.Forms.ToolStripItem> Main <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbe addirittura scomparire fino a quando non si diminuiscono le dimensioni del form.</span><span class="sxs-lookup"><span data-stu-id="12891-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="12891-109">Per abilitare l'overflow su un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="12891-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="12891-110">Verificare che la <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> proprietà non sia impostata su `false` per <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="12891-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="12891-111">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="12891-111">The default is `True`.</span></span>

     <span data-ttu-id="12891-112">Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> è `True` (impostazione predefinita), un oggetto <xref:System.Windows.Forms.ToolStripItem> viene inviato al menu a discesa di overflow quando il contenuto dell'oggetto <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un oggetto orizzontale <xref:System.Windows.Forms.ToolStrip> o l'altezza di un oggetto verticale <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="12891-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="12891-113">Per specificare il comportamento di overflow di un oggetto ToolStripItem specifico</span><span class="sxs-lookup"><span data-stu-id="12891-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="12891-114">Impostare la <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> proprietà di sul <xref:System.Windows.Forms.ToolStripItem> valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="12891-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="12891-115">Le possibilità sono `Always` , `Never` e `AsNeeded` .</span><span class="sxs-lookup"><span data-stu-id="12891-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="12891-116">Il valore predefinito è `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="12891-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="12891-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12891-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="12891-118">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="12891-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="12891-119">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="12891-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="12891-120">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="12891-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
