---
title: "Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961918"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="d5cd3-102">Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="d5cd3-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="d5cd3-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="d5cd3-104"><xref:System.Windows.Forms.ToolBar> i pulsanti sono in grado di visualizzare le icone al loro interno per facilitarne l'identificazione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="d5cd3-105">Questa operazione viene eseguita tramite l'aggiunta di immagini al <xref:System.Windows.Forms.ImageList> componente e l'associazione con il <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="d5cd3-106">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.ToolBar> controllo e un <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="d5cd3-107">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d5cd3-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="d5cd3-108">Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d5cd3-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="d5cd3-109">Aggiungere immagini al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="d5cd3-110">Per altre informazioni, vedere [procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d5cd3-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="d5cd3-111">Selezionare il <xref:System.Windows.Forms.ToolBar> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="d5cd3-112">Nella finestra **Proprietà** impostare la proprietà del <xref:System.Windows.Forms.ToolBar> controllo sul <xref:System.Windows.Forms.ToolBar.ImageList%2A> <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="d5cd3-113">Fare clic sulla <xref:System.Windows.Forms.ToolBar> proprietà del controllo <xref:System.Windows.Forms.ToolBar.Buttons%2A> per selezionarla, quindi fare clic sui puntini di sospensione ( ![ ...) nel pulsante finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) per aprire l' **Editor della raccolta ToolBarButton**.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="d5cd3-114">Usare il pulsante **Aggiungi** per aggiungere pulsanti al <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="d5cd3-115">Nella finestra **Proprietà** visualizzata nel riquadro sul lato destro dell' **Editor della raccolta ToolBarButton**, impostare la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà di ogni pulsante della barra degli strumenti su uno dei valori dell'elenco, che viene disegnato dalle immagini aggiunte al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="d5cd3-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5cd3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5cd3-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="d5cd3-117">Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="d5cd3-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="d5cd3-118">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="d5cd3-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="d5cd3-119">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="d5cd3-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
