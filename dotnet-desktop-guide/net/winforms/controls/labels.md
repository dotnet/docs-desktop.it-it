---
title: Controllo Etichetta
description: Informazioni sul controllo etichetta in Windows Forms per .NET. Le etichette vengono usate per identificare gli elementi visivi dell'utente.
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967312"
---
# <a name="label-control-overview-windows-forms-net"></a><span data-ttu-id="2e65c-104">Cenni preliminari sul controllo Label (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="2e65c-104">Label control overview (Windows Forms .NET)</span></span>

<span data-ttu-id="2e65c-105">Windows Forms <xref:System.Windows.Forms.Label> controlli vengono utilizzati per visualizzare il testo che non può essere modificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2e65c-105">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text that cannot be edited by the user.</span></span> <span data-ttu-id="2e65c-106">Vengono usati per identificare gli oggetti in un form e per fornire una descrizione di un determinato controllo che rappresenta o fa.</span><span class="sxs-lookup"><span data-stu-id="2e65c-106">They're used to identify objects on a form and to provide a description of what a certain control represents or does.</span></span> <span data-ttu-id="2e65c-107">Ad esempio, è possibile usare le etichette per aggiungere didascalie descrittive a caselle di testo, caselle di riepilogo, caselle combinate e così via.</span><span class="sxs-lookup"><span data-stu-id="2e65c-107">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="2e65c-108">È anche possibile scrivere codice che modifica il testo visualizzato da un'etichetta in risposta agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e65c-108">You can also write code that changes the text displayed by a label in response to events at run time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a><span data-ttu-id="2e65c-109">Utilizzo del controllo Label</span><span class="sxs-lookup"><span data-stu-id="2e65c-109">Working with the Label Control</span></span>  

<span data-ttu-id="2e65c-110">Poiché il <xref:System.Windows.Forms.Label> controllo non può ricevere lo stato attivo, può essere usato per creare chiavi di accesso per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="2e65c-110">Because the <xref:System.Windows.Forms.Label> control can't receive focus, it can be used to create access keys for other controls.</span></span> <span data-ttu-id="2e65c-111">Un tasto di scelta consente a un utente di concentrare il controllo successivo nell'ordine di tabulazione premendo il tasto <kbd>ALT</kbd> con il tasto di scelta scelto.</span><span class="sxs-lookup"><span data-stu-id="2e65c-111">An access key allows a user to focus the next control in tab order by pressing the <kbd>Alt</kbd> key with the chosen access key.</span></span> <span data-ttu-id="2e65c-112">Per altre informazioni, vedere [usare un'etichetta per concentrare un controllo](how-to-create-access-keys.md#use-a-label-to-focus-a-control).</span><span class="sxs-lookup"><span data-stu-id="2e65c-112">For more information, see [Use a label to focus a control](how-to-create-access-keys.md#use-a-label-to-focus-a-control).</span></span>
  
<span data-ttu-id="2e65c-113">La didascalia visualizzata nell'etichetta è contenuta nella <xref:System.Windows.Forms.Label.Text%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e65c-113">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="2e65c-114">La <xref:System.Windows.Forms.Label.TextAlign%2A> proprietà consente di impostare l'allineamento del testo all'interno dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="2e65c-114">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="2e65c-115">Per altre informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-display-text.md).</span><span class="sxs-lookup"><span data-stu-id="2e65c-115">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-display-text.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e65c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e65c-116">See also</span></span>

- [<span data-ttu-id="2e65c-117">Usare un'etichetta per concentrare un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="2e65c-117">Use a label to focus a control (Windows Forms .NET)</span></span>](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [<span data-ttu-id="2e65c-118">Procedura: impostare il testo visualizzato da un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="2e65c-118">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
