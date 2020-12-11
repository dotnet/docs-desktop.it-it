---
title: Verificare il tasto di modifica premuto
description: Informazioni su come rilevare quando vengono premuti i tasti MAIUSC, ALT o CTRL in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.openlocfilehash: 7feda0f604e1cb40b34f7bf42aa122d817a5a95e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967297"
---
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a><span data-ttu-id="d7d70-103">Come verificare la pressione dei tasti di modifica (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="d7d70-103">How to check for modifier key presses (Windows Forms .NET)</span></span>

<span data-ttu-id="d7d70-104">Quando l'utente digita chiavi nell'applicazione, è possibile monitorare i tasti di modifica premuti, ad esempio <kbd>MAIUSC</kbd>, <kbd>ALT</kbd>e <kbd>CTRL</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d7d70-104">As the user types keys into your application, you can monitor for pressed modifier keys such as the <kbd>SHIFT</kbd>, <kbd>ALT</kbd>, and <kbd>CTRL</kbd>.</span></span> <span data-ttu-id="d7d70-105">Quando si preme un tasto di modifica in combinazione con altre chiavi o anche con un clic del mouse, l'applicazione può rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="d7d70-105">When a modifier key is pressed in combination with other keys or even a mouse click, your application can respond appropriately.</span></span> <span data-ttu-id="d7d70-106">La pressione del tasto <kbd>s</kbd> , ad esempio, può causare la visualizzazione di una "s" sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="d7d70-106">For example, pressing the <kbd>S</kbd> key may cause an "s" to appear on the screen.</span></span> <span data-ttu-id="d7d70-107">Se vengono premuti i tasti <kbd>CTRL + S</kbd> , è possibile salvare il documento corrente.</span><span class="sxs-lookup"><span data-stu-id="d7d70-107">If the keys <kbd>CTRL+S</kbd> are pressed, instead, the current document may be saved.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="d7d70-108">Se si gestisce l' <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> proprietà ricevuta dal gestore eventi specifica i tasti di modifica che vengono premuti.</span><span class="sxs-lookup"><span data-stu-id="d7d70-108">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> property received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="d7d70-109">Inoltre, la <xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> proprietà specifica il carattere che è stato premuto insieme a qualsiasi tasto di modifica combinato con un operatore OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="d7d70-109">Also, the <xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> property specifies the character that was pressed along with any modifier keys combined with a bitwise OR.</span></span>

<span data-ttu-id="d7d70-110">Se si sta gestendo l' <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, il gestore eventi non riceve queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="d7d70-110">If you're handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler doesn't receive this information.</span></span> <span data-ttu-id="d7d70-111">Utilizzare la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà della <xref:System.Windows.Forms.Control> classe per rilevare un modificatore di chiave.</span><span class="sxs-lookup"><span data-stu-id="d7d70-111">Use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class to detect a key modifier.</span></span> <span data-ttu-id="d7d70-112">In entrambi i casi, è necessario eseguire un operatore AND bit per bit del <xref:System.Windows.Forms.Keys> valore appropriato e il valore che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="d7d70-112">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you're testing.</span></span> <span data-ttu-id="d7d70-113">L' <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni tasto di modifica, quindi è importante eseguire l'operazione bit per bit e verificare con il valore corretto.</span><span class="sxs-lookup"><span data-stu-id="d7d70-113">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it's important that you do the bitwise AND check with the correct value.</span></span>

<span data-ttu-id="d7d70-114">Il tasto <kbd>MAIUSC</kbd> , ad esempio, è rappresentato dai valori chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7d70-114">For example, the <kbd>SHIFT</kbd> key is represented by the following key values:</span></span>

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

<span data-ttu-id="d7d70-115">Il valore corretto per testare lo <kbd>spostamento</kbd> come un tasto di modifica è <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d7d70-115">The correct value to test <kbd>SHIFT</kbd> as a modifier key is <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d7d70-116">Analogamente, per verificare la presenza di tasti <kbd>CTRL</kbd> e <kbd>ALT</kbd> come modificatori, è necessario usare <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> rispettivamente i <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> valori e.</span><span class="sxs-lookup"><span data-stu-id="d7d70-116">Similarly, to test for <kbd>CTRL</kbd> and <kbd>ALT</kbd> as modifiers you should use the <xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> and <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> values, respectively.</span></span>

## <a name="detect-modifier-key"></a><span data-ttu-id="d7d70-117">Rileva il tasto di modifica</span><span class="sxs-lookup"><span data-stu-id="d7d70-117">Detect modifier key</span></span>

<span data-ttu-id="d7d70-118">Rilevare se viene premuto un tasto di modifica confrontando la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà e il <xref:System.Windows.Forms.Keys> valore di enumerazione con un operatore and bit per bit.</span><span class="sxs-lookup"><span data-stu-id="d7d70-118">Detect if a modifier key is pressed by comparing the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and the <xref:System.Windows.Forms.Keys> enumeration value with a bitwise AND operator.</span></span>

<span data-ttu-id="d7d70-119">Nell'esempio di codice seguente viene illustrato come determinare se il tasto <kbd>MAIUSC</kbd> è premuto nei <xref:System.Windows.Forms.Control.KeyPress> <xref:System.Windows.Forms.Control.KeyDown> gestori eventi e.</span><span class="sxs-lookup"><span data-stu-id="d7d70-119">The following code example shows how to determine whether the <kbd>SHIFT</kbd> key is pressed within the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyDown> event handlers.</span></span>

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a><span data-ttu-id="d7d70-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d70-120">See also</span></span>

- [<span data-ttu-id="d7d70-121">Panoramica dell'uso della tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="d7d70-121">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="d7d70-122">Utilizzo degli eventi di tastiera (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="d7d70-122">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
