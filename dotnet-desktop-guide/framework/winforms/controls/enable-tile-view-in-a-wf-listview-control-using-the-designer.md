---
title: Abilitare la visualizzazione affiancata nel controllo ListView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962914"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="f79f7-102">Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f79f7-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="f79f7-103">La funzionalità di visualizzazione affiancata del <xref:System.Windows.Forms.ListView> controllo consente di fornire un equilibrio visivo tra informazioni grafiche e testuali.</span><span class="sxs-lookup"><span data-stu-id="f79f7-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="f79f7-104">Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="f79f7-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="f79f7-105">Funzioni di visualizzazione affiancate in combinazione con le funzionalità di raggruppamento o di contrassegno di inserimento nel <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f79f7-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="f79f7-106">La visualizzazione affiancata usa un'icona 32 x 32 e varie righe di testo, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="f79f7-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="f79f7-107">![Visualizzazione affiancata in un controllo ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Icone e testo di visualizzazione affiancata")</span><span class="sxs-lookup"><span data-stu-id="f79f7-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="f79f7-108">Le proprietà e i metodi della visualizzazione affiancata consentono di specificare i campi di colonna da visualizzare per ogni elemento e di controllare collettivamente le dimensioni e l'aspetto di tutti gli elementi all'interno di una finestra di visualizzazione affiancata.</span><span class="sxs-lookup"><span data-stu-id="f79f7-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="f79f7-109">Per maggiore chiarezza, la prima riga di testo in una sezione è sempre il nome dell'elemento; non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f79f7-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="f79f7-110">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f79f7-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f79f7-111">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f79f7-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="f79f7-112">Per impostare la visualizzazione affiancata nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f79f7-112">To set tile view in the designer</span></span>

1. <span data-ttu-id="f79f7-113">In Visual Studio selezionare il <xref:System.Windows.Forms.ListView> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="f79f7-113">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="f79f7-114">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.ListView.View%2A> proprietà e scegliere **riquadro**.</span><span class="sxs-lookup"><span data-stu-id="f79f7-114">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f79f7-115">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="f79f7-116">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="f79f7-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
