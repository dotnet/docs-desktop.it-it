---
title: 'Procedura: allineare un controllo ai bordi dei form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964009"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="6d6a6-102">Procedura: allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6d6a6-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="6d6a6-103">È possibile rendere il controllo allineato al bordo dei form impostando il valore della <xref:System.Windows.Forms.Control.Dock%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="6d6a6-104">che designa la posizione del controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="6d6a6-105">La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="6d6a6-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="6d6a6-106">Impostazione</span><span class="sxs-lookup"><span data-stu-id="6d6a6-106">Setting</span></span>|<span data-ttu-id="6d6a6-107">Effetto sul controllo</span><span class="sxs-lookup"><span data-stu-id="6d6a6-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="6d6a6-108">Il controllo viene ancorato alla parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="6d6a6-109">Il controllo occupa tutto lo spazio rimanente nel form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="6d6a6-110">Il controllo viene ancorato al lato sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="6d6a6-111">Non viene ancorato in alcun punto e viene visualizzato nella posizione specificata da <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="6d6a6-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="6d6a6-112">Il controllo viene ancorato al lato destro del form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="6d6a6-113">Il controllo viene ancorato alla parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="6d6a6-114">Questi valori possono essere impostati anche nel codice.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-114">These values can also be set in code.</span></span> <span data-ttu-id="6d6a6-115">Per altre informazioni, vedere [procedura: allineare un controllo ai bordi dei form](how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6d6a6-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="6d6a6-116">Impostare la proprietà Dock per il controllo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6d6a6-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="6d6a6-117">Nel Progettazione Windows Form in Visual Studio selezionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="6d6a6-118">Nella finestra **Proprietà** fare clic sulla casella di riepilogo a discesa accanto alla <xref:System.Windows.Forms.Control.Dock%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="6d6a6-119">Viene visualizzata un'interfaccia grafica che rappresenta le sei <xref:System.Windows.Forms.Control.Dock%2A> impostazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="6d6a6-120">Scegliere l'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="6d6a6-121">Il controllo ora verrà ancorato nel modo specificato dall'impostazione.</span><span class="sxs-lookup"><span data-stu-id="6d6a6-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d6a6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d6a6-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6d6a6-123">Procedura: Allineare un controllo ai bordi dei moduli</span><span class="sxs-lookup"><span data-stu-id="6d6a6-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="6d6a6-124">Procedura dettagliata: disposizione dei controlli in Windows Form utilizzando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="6d6a6-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="6d6a6-125">Procedura: agganciare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6d6a6-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="6d6a6-126">Procedura: agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6d6a6-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="6d6a6-127">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6d6a6-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="6d6a6-128">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6d6a6-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="6d6a6-129">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6d6a6-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="6d6a6-130">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6d6a6-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
