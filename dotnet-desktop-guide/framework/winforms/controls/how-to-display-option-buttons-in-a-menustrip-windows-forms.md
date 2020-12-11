---
title: 'Procedura: Visualizzare pulsanti di opzione in un controllo MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964459"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="43b9e-102">Procedura: visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="43b9e-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="43b9e-103">I pulsanti di opzione, noti anche come pulsanti di opzione, sono simili alle caselle di controllo, ad eccezione del fatto che gli utenti possono selezionare solo uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="43b9e-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="43b9e-104">Anche se, per impostazione predefinita <xref:System.Windows.Forms.ToolStripMenuItem> , la classe non fornisce il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del pulsante di opzione per le voci di menu in un <xref:System.Windows.Forms.MenuStrip> controllo.</span><span class="sxs-lookup"><span data-stu-id="43b9e-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="43b9e-105">Quando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu è `true` , gli utenti possono fare clic sull'elemento per abilitare o disabilitare la visualizzazione di un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="43b9e-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="43b9e-106">La <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà indica lo stato corrente dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="43b9e-107">Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che, quando si seleziona un elemento, impostare la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà per l'elemento selezionato in precedenza su `false` .</span><span class="sxs-lookup"><span data-stu-id="43b9e-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="43b9e-108">Nelle procedure seguenti viene descritto come implementare questa e funzionalità aggiuntiva in una classe che eredita la <xref:System.Windows.Forms.ToolStripMenuItem> classe.</span><span class="sxs-lookup"><span data-stu-id="43b9e-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="43b9e-109">La `ToolStripRadioButtonMenuItem` classe esegue l'override dei membri, ad esempio <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> e, <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per fornire il comportamento di selezione e l'aspetto dei pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="43b9e-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="43b9e-110">Questa classe, inoltre, esegue l'override della <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Proprietà in modo che le opzioni di un sottomenu siano disabilitate, a meno che non sia selezionato l'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="43b9e-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="43b9e-111">Per implementare il comportamento di selezione dei pulsanti di opzione</span><span class="sxs-lookup"><span data-stu-id="43b9e-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="43b9e-112">Inizializza la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà su `true` per abilitare la selezione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="43b9e-113">Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> metodo per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="43b9e-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="43b9e-114">Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> metodo per fare in modo che facendo clic su un elemento già selezionato non venga cancellata la selezione.</span><span class="sxs-lookup"><span data-stu-id="43b9e-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="43b9e-115">Per modificare l'aspetto degli elementi del pulsante di opzione</span><span class="sxs-lookup"><span data-stu-id="43b9e-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="43b9e-116">Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> metodo per sostituire il segno di spunta predefinito con un pulsante di opzione usando la <xref:System.Windows.Forms.RadioButtonRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="43b9e-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="43b9e-117">Eseguire l'override dei <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> metodi,, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> e <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> per tenere traccia dello stato del mouse e assicurarsi che il <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> Metodo disegni lo stato corretto del pulsante di opzione.</span><span class="sxs-lookup"><span data-stu-id="43b9e-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="43b9e-118">Per disabilitare le opzioni in un sottomenu quando l'elemento padre non è selezionato</span><span class="sxs-lookup"><span data-stu-id="43b9e-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="43b9e-119">Eseguire l'override della <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Proprietà in modo che l'elemento venga disabilitato quando dispone di un elemento padre con un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valore `true` e un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valore `false` .</span><span class="sxs-lookup"><span data-stu-id="43b9e-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="43b9e-120">Eseguire l'override del <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> metodo per sottoscrivere l' <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> evento dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="43b9e-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="43b9e-121">Nel gestore per l'evento padre-elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> , invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="43b9e-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="43b9e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="43b9e-122">Example</span></span>

<span data-ttu-id="43b9e-123">Nell'esempio di codice seguente vengono fornite la `ToolStripRadioButtonMenuItem` classe completa e una <xref:System.Windows.Forms.Form> classe e una `Program` classe per illustrare il comportamento del pulsante di opzione.</span><span class="sxs-lookup"><span data-stu-id="43b9e-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="43b9e-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="43b9e-124">Compiling the Code</span></span>

<span data-ttu-id="43b9e-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="43b9e-125">This example requires:</span></span>

- <span data-ttu-id="43b9e-126">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="43b9e-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="43b9e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43b9e-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="43b9e-128">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="43b9e-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="43b9e-129">Procedura: Implementare un oggetto ToolStripRenderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="43b9e-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
