---
title: Creare chiavi di accesso per i controlli
description: Informazioni su come impostare il tasto di scelta rapida per un controllo o un'etichetta in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.openlocfilehash: 4d746082ffbaa749b882dcb1a769b5f9541c6fe8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969022"
---
# <a name="add-an-access-key-shortcut-to-a-control-windows-forms-net"></a><span data-ttu-id="acf1a-103">Aggiungere un collegamento alla chiave di accesso a un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="acf1a-103">Add an access key shortcut to a control (Windows Forms .NET)</span></span>

<span data-ttu-id="acf1a-104">Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante.</span><span class="sxs-lookup"><span data-stu-id="acf1a-104">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="acf1a-105">Con una chiave di accesso, l'utente può fare clic su un pulsante premendo <kbd>ALT</kbd> insieme al tasto di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="acf1a-105">With an access key, the user can "click" a button by pressing the <kbd>Alt</kbd> key in combination with the predefined access key.</span></span> <span data-ttu-id="acf1a-106">Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la relativa `Text` proprietà è impostata su "stampa", l'aggiunta di una e commerciale (&) prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acf1a-106">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="acf1a-107">L'utente può eseguire il comando associato al pulsante premendo <kbd>ALT</kbd>.</span><span class="sxs-lookup"><span data-stu-id="acf1a-107">The user can run the command associated with the button by pressing <kbd>Alt</kbd>.</span></span>

<span data-ttu-id="acf1a-108">I controlli che non possono ricevere lo stato attivo non possono avere chiavi di accesso, ad eccezione di controlli Label.</span><span class="sxs-lookup"><span data-stu-id="acf1a-108">Controls that cannot receive focus can't have access keys, except label controls.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="acf1a-109">Designer</span><span class="sxs-lookup"><span data-stu-id="acf1a-109">Designer</span></span>

<span data-ttu-id="acf1a-110">Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** su una stringa che include una e commerciale (&) prima della lettera che sarà il tasto di accesso.</span><span class="sxs-lookup"><span data-stu-id="acf1a-110">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="acf1a-111">Ad esempio, per impostare la lettera "P" come chiave di accesso, immettere **&stampa**.</span><span class="sxs-lookup"><span data-stu-id="acf1a-111">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

:::image type="content" source="media/how-to-create-access-keys/properties-text.png" alt-text="Finestra di dialogo Proprietà con proprietà testo selezionata e chiave di accesso":::

## <a name="programmatic"></a><span data-ttu-id="acf1a-113">Programmatica</span><span class="sxs-lookup"><span data-stu-id="acf1a-113">Programmatic</span></span>

<span data-ttu-id="acf1a-114">Impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.</span><span class="sxs-lookup"><span data-stu-id="acf1a-114">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

## <a name="use-a-label-to-focus-a-control"></a><span data-ttu-id="acf1a-115">Usare un'etichetta per concentrare un controllo</span><span class="sxs-lookup"><span data-stu-id="acf1a-115">Use a label to focus a control</span></span>

<span data-ttu-id="acf1a-116">Anche se un'etichetta non può essere concentrata, ha la possibilità di concentrare il controllo successivo nell'ordine di tabulazione del form.</span><span class="sxs-lookup"><span data-stu-id="acf1a-116">Even though a label cannot be focused, it has the ability to focus the next control in the tab order of the form.</span></span> <span data-ttu-id="acf1a-117">A ogni controllo viene assegnato un valore alla <xref:System.Windows.Forms.Control.TabIndex> proprietà, generalmente in ordine sequenziale crescente.</span><span class="sxs-lookup"><span data-stu-id="acf1a-117">Each control is assigned a value to the <xref:System.Windows.Forms.Control.TabIndex> property, generally in ascending sequential order.</span></span> <span data-ttu-id="acf1a-118">Quando la chiave di accesso viene assegnata alla proprietà [Label. Text](xref:System.Windows.Forms.Label.Text) , il controllo successivo nell'ordine di tabulazione sequenziale è incentrato.</span><span class="sxs-lookup"><span data-stu-id="acf1a-118">When the access key is assigned to the [Label.Text](xref:System.Windows.Forms.Label.Text) property, the next control in the sequential tab order is focused.</span></span>

<span data-ttu-id="acf1a-119">Utilizzando l'esempio della sezione [a livello di codice](#programmatic) , se il pulsante non dispone di un set di testo, ma presenta invece un'immagine di una stampante, è possibile utilizzare un'etichetta per concentrare il pulsante.</span><span class="sxs-lookup"><span data-stu-id="acf1a-119">Using the example from the [Programmatic](#programmatic) section, if the button didn't have any text set, but instead presented an image of a printer, you could use a label to focus the button.</span></span>

```vb
' Set the letter "P" as an access key.
Label1.Text = "&Print"
Label1.TabIndex = 9
Button1.TabIndex = 10
```

```csharp
// Set the letter "P" as an access key.
label1.Text = "&Print";
label1.TabIndex = 9
button1.TabIndex = 10
```

## <a name="display-an-ampersand"></a><span data-ttu-id="acf1a-120">Visualizza una e commerciale</span><span class="sxs-lookup"><span data-stu-id="acf1a-120">Display an ampersand</span></span>

<span data-ttu-id="acf1a-121">Quando si imposta il testo o la didascalia di un controllo che interpreta una e commerciale (&) come chiave di accesso, utilizzare due e commerciali consecutive (&&) per visualizzare una singola e commerciale.</span><span class="sxs-lookup"><span data-stu-id="acf1a-121">When setting the text or caption of a control that interprets an ampersand (&) as an access key, use two consecutive ampersands (&&) to display a single ampersand.</span></span> <span data-ttu-id="acf1a-122">Ad esempio, il testo di un pulsante impostato su `"Print && Close"` viene visualizzato nella didascalia di `Print & Close` :</span><span class="sxs-lookup"><span data-stu-id="acf1a-122">For example, the text of a button set to `"Print && Close"` displays in the caption of `Print & Close`:</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "Print && Close"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "Print && Close";
```

:::image type="content" source="media/how-to-create-access-keys/double-ampersand.png" alt-text="visualizzazione di una e commerciale in un pulsante":::

## <a name="see-also"></a><span data-ttu-id="acf1a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acf1a-124">See also</span></span>

- [<span data-ttu-id="acf1a-125">Procedura: impostare il testo visualizzato da un controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="acf1a-125">How to: Set the text displayed by a Windows Forms control</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.Label>
