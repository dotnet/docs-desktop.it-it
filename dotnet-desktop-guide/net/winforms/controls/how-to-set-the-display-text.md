---
title: Imposta il testo visualizzato da un controllo
description: Informazioni su come impostare il testo visualizzato da un controllo Windows Forms. Impostare o restituire il testo utilizzando la proprietà Text oppure modificare il tipo di carattere utilizzando la proprietà font.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.openlocfilehash: 2fd5a62310ae5e7d6e0528c7f12f37ed40f8a626
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964792"
---
# <a name="how-to-set-the-text-displayed-by-a-control-windows-forms-net"></a><span data-ttu-id="6ca17-104">Procedura: impostare il testo visualizzato da un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="6ca17-104">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>

<span data-ttu-id="6ca17-105">I controlli Windows Forms in genere visualizzano testo correlato alla funzione primaria del controllo.</span><span class="sxs-lookup"><span data-stu-id="6ca17-105">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="6ca17-106">Un controllo, ad esempio, <xref:System.Windows.Forms.Button> Visualizza in genere una didascalia che indica l'azione che verrà eseguita se si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="6ca17-106">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="6ca17-107">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ca17-107">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="6ca17-108">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ca17-108">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="6ca17-109">È anche possibile impostare il testo usando la [finestra di progettazione](#designer).</span><span class="sxs-lookup"><span data-stu-id="6ca17-109">You can also set the text by using the [designer](#designer).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="6ca17-110">Designer</span><span class="sxs-lookup"><span data-stu-id="6ca17-110">Designer</span></span>

01. <span data-ttu-id="6ca17-111">Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** del controllo su una stringa appropriata.</span><span class="sxs-lookup"><span data-stu-id="6ca17-111">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

    <span data-ttu-id="6ca17-112">Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) prima della lettera che costituirà il tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="6ca17-112">To create an underlined shortcut key, include an ampersand (&) before the letter that will be the shortcut key.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-text.png" alt-text="Riquadro proprietà di Visual Studio per .NET Windows Forms con proprietà testo visualizzata.":::

01. <span data-ttu-id="6ca17-114">Nella finestra **Proprietà** selezionare il pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio ](../media/visual-studio-ellipsis-button.png) ) accanto alla proprietà **font** .</span><span class="sxs-lookup"><span data-stu-id="6ca17-114">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](../media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/properties-font.png" alt-text="Riquadro delle proprietà di Visual Studio per .NET Windows Forms con la proprietà font mostrata.":::

    <span data-ttu-id="6ca17-116">Nella finestra di dialogo tipo di carattere standard modificare il tipo di carattere con impostazioni quali tipo, dimensioni e stile.</span><span class="sxs-lookup"><span data-stu-id="6ca17-116">In the standard font dialog box, adjust the font with settings such as type, size, and style.</span></span>

    :::image type="content" source="media/how-to-set-the-text-displayed-by-a-windows-forms-control/font-window.png" alt-text="Riquadro delle proprietà di Visual Studio per .NET Windows Forms con la finestra impostazioni carattere.":::

## <a name="programmatic"></a><span data-ttu-id="6ca17-118">Programmatica</span><span class="sxs-lookup"><span data-stu-id="6ca17-118">Programmatic</span></span>

01. <span data-ttu-id="6ca17-119">Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.</span><span class="sxs-lookup"><span data-stu-id="6ca17-119">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

    <span data-ttu-id="6ca17-120">Per creare una chiave di accesso sottolineata, includere una e commerciale (&) prima della lettera che sarà il tasto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6ca17-120">To create an underlined access key, include an ampersand (&) before the letter that will be the access key.</span></span>

01. <span data-ttu-id="6ca17-121">Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="6ca17-121">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="6ca17-122">È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="6ca17-122">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="6ca17-123">La riga di codice seguente, ad esempio, imposta il testo della voce di menu in modo da leggere "& ora per qualcosa di completamente diverso":</span><span class="sxs-lookup"><span data-stu-id="6ca17-123">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

## <a name="see-also"></a><span data-ttu-id="6ca17-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ca17-124">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6ca17-125">Procedura: creare tasti di scelta per i controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ca17-125">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys.md)
