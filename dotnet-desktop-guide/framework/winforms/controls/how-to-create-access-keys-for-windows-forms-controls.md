---
title: Creare chiavi di accesso per i controlli
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964462"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="0442b-102">Procedura: creare chiavi di accesso per controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0442b-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="0442b-103">Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante.</span><span class="sxs-lookup"><span data-stu-id="0442b-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="0442b-104">Con una chiave di accesso, l'utente può fare clic su un pulsante premendo ALT insieme al tasto di accesso predefinito.</span><span class="sxs-lookup"><span data-stu-id="0442b-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="0442b-105">Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la relativa `Text` proprietà è impostata su "stampa", l'aggiunta di una e commerciale prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0442b-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="0442b-106">L'utente può eseguire il comando associato al pulsante premendo ALT + P.</span><span class="sxs-lookup"><span data-stu-id="0442b-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="0442b-107">I controlli che non possono ricevere lo stato attivo non possono avere chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="0442b-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="0442b-108">Programmatica</span><span class="sxs-lookup"><span data-stu-id="0442b-108">Programmatic</span></span>

<span data-ttu-id="0442b-109">Impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.</span><span class="sxs-lookup"><span data-stu-id="0442b-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> <span data-ttu-id="0442b-110">Per usare una e commerciale in una didascalia senza creare una chiave di accesso, includere due e commerciale (&&).</span><span class="sxs-lookup"><span data-stu-id="0442b-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="0442b-111">Una singola e commerciale viene visualizzata nella didascalia e nessun carattere è sottolineato.</span><span class="sxs-lookup"><span data-stu-id="0442b-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="0442b-112">Designer</span><span class="sxs-lookup"><span data-stu-id="0442b-112">Designer</span></span>

<span data-ttu-id="0442b-113">Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** su una stringa che include una e commerciale (' &') prima della lettera che sarà il tasto di accesso.</span><span class="sxs-lookup"><span data-stu-id="0442b-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="0442b-114">Ad esempio, per impostare la lettera "P" come chiave di accesso, immettere **&stampa**.</span><span class="sxs-lookup"><span data-stu-id="0442b-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0442b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0442b-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="0442b-116">Procedura: rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0442b-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="0442b-117">Procedura: impostare il testo visualizzato da un controllo di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0442b-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="0442b-118">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="0442b-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
