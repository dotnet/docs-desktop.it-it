---
title: Ancorare i controlli (Anchor)
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: e7bc514f7347f257a6e2df67571c09df78f3c547
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957163"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="45551-102">Procedura: ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="45551-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="45551-103">Se si progetta un modulo che l'utente può ridimensionare in fase di esecuzione, i controlli sul form devono essere ridimensionati e riposizionati correttamente.</span><span class="sxs-lookup"><span data-stu-id="45551-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="45551-104">Per ridimensionare i controlli in modo dinamico con il modulo, è possibile usare la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="45551-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="45551-105">La <xref:System.Windows.Forms.Control.Anchor%2A> proprietà definisce una posizione di ancoraggio per il controllo.</span><span class="sxs-lookup"><span data-stu-id="45551-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="45551-106">Quando un controllo è ancorato a un form e il form viene ridimensionato, il controllo mantiene la distanza tra il controllo e le posizioni di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="45551-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="45551-107">Se, ad esempio, si dispone di un <xref:System.Windows.Forms.TextBox> controllo ancorato ai bordi sinistro, destro e inferiore del form, quando il form viene ridimensionato, il <xref:System.Windows.Forms.TextBox> controllo viene ridimensionato orizzontalmente in modo da mantenere la stessa distanza dai lati destro e sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="45551-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="45551-108">Inoltre, il controllo si posiziona verticalmente in modo che la posizione sia sempre la stessa a distanza dal bordo inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="45551-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="45551-109">Se un controllo non è ancorato e il form viene ridimensionato, la posizione del controllo rispetto ai bordi del form viene modificata.</span><span class="sxs-lookup"><span data-stu-id="45551-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="45551-110">La <xref:System.Windows.Forms.Control.Anchor%2A> proprietà interagisce con la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="45551-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="45551-111">Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="45551-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="45551-112">Ancoraggio di un controllo in un form</span><span class="sxs-lookup"><span data-stu-id="45551-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="45551-113">In Visual Studio selezionare il controllo che si vuole ancorare.</span><span class="sxs-lookup"><span data-stu-id="45551-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45551-114">È possibile ancorare più controlli simultaneamente premendo il tasto CTRL, facendo clic su ogni controllo per selezionarlo e quindi attenendosi al resto della procedura.</span><span class="sxs-lookup"><span data-stu-id="45551-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="45551-115">Nella finestra **Proprietà** fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Anchor%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="45551-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="45551-116">Viene visualizzato un editor che mostra una croce.</span><span class="sxs-lookup"><span data-stu-id="45551-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="45551-117">Per impostare un ancoraggio, fare clic sulla sezione superiore, a sinistra, a destra o in basso della Croce.</span><span class="sxs-lookup"><span data-stu-id="45551-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="45551-118">Per impostazione predefinita, i controlli sono ancorati nella parte superiore e sinistra.</span><span class="sxs-lookup"><span data-stu-id="45551-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="45551-119">Per cancellare un lato del controllo che è stato ancorato, fare clic su tale ARM della Croce.</span><span class="sxs-lookup"><span data-stu-id="45551-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="45551-120">Per chiudere l' <xref:System.Windows.Forms.Control.Anchor%2A> editor di proprietà, fare di nuovo clic sul <xref:System.Windows.Forms.Control.Anchor%2A> nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="45551-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="45551-121">Quando il form viene visualizzato in fase di esecuzione, il controllo viene ridimensionato in modo che rimanga posizionato alla stessa distanza dal bordo del form.</span><span class="sxs-lookup"><span data-stu-id="45551-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="45551-122">La distanza dal bordo ancorato rimane sempre uguale alla distanza definita quando il controllo è posizionato nell'Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="45551-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="45551-123">Alcuni controlli, ad esempio il <xref:System.Windows.Forms.ComboBox> controllo, hanno un limite per l'altezza.</span><span class="sxs-lookup"><span data-stu-id="45551-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="45551-124">L'ancoraggio del controllo nella parte inferiore del form o del contenitore non può forzare il superamento del limite di altezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="45551-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="45551-125">I controlli ereditati devono essere in grado di essere `Protected` ancorati.</span><span class="sxs-lookup"><span data-stu-id="45551-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="45551-126">Per modificare il livello di accesso di un controllo, impostarne la `Modifiers` proprietà nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="45551-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="45551-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="45551-127">See also</span></span>

- [<span data-ttu-id="45551-128">Controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="45551-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="45551-129">Cenni preliminari sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="45551-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="45551-130">Procedura: ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="45551-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="45551-131">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="45551-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="45551-132">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="45551-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="45551-133">Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="45551-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
