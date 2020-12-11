---
title: 'Procedura: agganciare e ancorare controlli figlio in un controllo TableLayoutPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: 0e565b56c31d0776f6e89bbbe0b0681ae184758e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962098"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="7adec-102">Procedura: agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7adec-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="7adec-103">Il controllo <xref:System.Windows.Forms.TableLayoutPanel> supporta le proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> nei controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="7adec-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="7adec-104">Per allineare un controllo figlio in una cella TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7adec-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="7adec-105">Creare un controllo <xref:System.Windows.Forms.TableLayoutPanel> nel form.</span><span class="sxs-lookup"><span data-stu-id="7adec-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="7adec-106">Impostare il valore delle <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> proprietà e del controllo <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> su **1**.</span><span class="sxs-lookup"><span data-stu-id="7adec-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3. <span data-ttu-id="7adec-107">Creare un controllo <xref:System.Windows.Forms.Button> nel controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="7adec-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="7adec-108"><xref:System.Windows.Forms.Button> occupa l'angolo superiore sinistro della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4. <span data-ttu-id="7adec-109">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Left`.</span><span class="sxs-lookup"><span data-stu-id="7adec-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="7adec-110">Il controllo <xref:System.Windows.Forms.Button> viene spostato per allinearlo al bordo sinistro della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7adec-111">Questo comportamento è diverso dal comportamento di altri controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="7adec-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="7adec-112">In altri controlli contenitore, il controllo figlio non viene spostato quando viene impostata la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e la distanza tra il controllo ancorato e i limiti del contenitore padre viene stabilita al momento dell’impostazione della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="7adec-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5. <span data-ttu-id="7adec-113">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="7adec-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="7adec-114">Il controllo <xref:System.Windows.Forms.Button> viene spostato in modo che occupi l'angolo superiore sinistro della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6. <span data-ttu-id="7adec-115">Ripetere il passaggio 5 con un valore `Top, Right` per spostare il <xref:System.Windows.Forms.Button> controllo nell'angolo superiore destro della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="7adec-116">Ripetere l'operazione con i valori di `Bottom, Left` e `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="7adec-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="7adec-117">Per estendere un controllo figlio in una cella TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7adec-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="7adec-118">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="7adec-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="7adec-119">Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato in modo da estendersi per tutta la cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7adec-120">Questo comportamento è diverso dal comportamento di altri controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="7adec-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="7adec-121">In altri controlli contenitore, il controllo figlio non viene ridimensionato quando la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà è impostata su `Left, Right` o `Top, Bottom` .</span><span class="sxs-lookup"><span data-stu-id="7adec-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2. <span data-ttu-id="7adec-122">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="7adec-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="7adec-123">Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato in modo da estendersi dalla parte superiore a quella inferiore della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3. <span data-ttu-id="7adec-124">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="7adec-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="7adec-125">Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per riempire la cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4. <span data-ttu-id="7adec-126">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `None`.</span><span class="sxs-lookup"><span data-stu-id="7adec-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="7adec-127">Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato e centrato nella cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5. <span data-ttu-id="7adec-128">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Dock%2A> , su <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="7adec-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="7adec-129">Il controllo <xref:System.Windows.Forms.Button> viene spostato per allinearlo al bordo sinistro della cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="7adec-130">Il controllo <xref:System.Windows.Forms.Button> conserva la larghezza, ma l'altezza viene ridimensionata per riempire la cella in verticale.</span><span class="sxs-lookup"><span data-stu-id="7adec-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7adec-131">È lo stesso comportamento che si verifica in altri controlli contenitore.</span><span class="sxs-lookup"><span data-stu-id="7adec-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6. <span data-ttu-id="7adec-132">Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Dock%2A> , su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="7adec-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="7adec-133">Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per riempire la cella.</span><span class="sxs-lookup"><span data-stu-id="7adec-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7adec-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="7adec-134">Example</span></span>  
 <span data-ttu-id="7adec-135">La figura seguente mostra cinque pulsanti ancorati in cinque celle <xref:System.Windows.Forms.TableLayoutPanel> separate.</span><span class="sxs-lookup"><span data-stu-id="7adec-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="7adec-136">![Ancoraggio TableLayoutPanel](./media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="7adec-136">![TableLayoutPanel Anchoring](./media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="7adec-137">La figura seguente mostra quattro pulsanti ancorati agli angoli di quattro celle <xref:System.Windows.Forms.TableLayoutPanel> separate.</span><span class="sxs-lookup"><span data-stu-id="7adec-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="7adec-138">![Ancoraggio TableLayoutPanel](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="7adec-138">![TableLayoutPanel Anchoring](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="7adec-139">La figura seguente mostra tre pulsanti estesi mediante ancoraggio in tre celle <xref:System.Windows.Forms.TableLayoutPanel> separate.</span><span class="sxs-lookup"><span data-stu-id="7adec-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="7adec-140">![Ancoraggio TableLayoutPanel](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="7adec-140">![TableLayoutPanel Anchoring](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="7adec-141">L'esempio di codice seguente mostra tutte le combinazioni dei valori della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> per un controllo <xref:System.Windows.Forms.Button> in un controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="7adec-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7adec-142">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7adec-142">Compiling the Code</span></span>  
 <span data-ttu-id="7adec-143">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7adec-143">This example requires:</span></span>  
  
- <span data-ttu-id="7adec-144">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7adec-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7adec-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7adec-145">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="7adec-146">Controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7adec-146">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
