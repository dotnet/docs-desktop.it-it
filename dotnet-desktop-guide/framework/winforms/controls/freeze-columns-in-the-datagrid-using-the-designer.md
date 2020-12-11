---
title: Bloccare le colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 554d5eaa55401bdafc455c2dfb20d7c5d214a9be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962182"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f450f-102">Procedura: Bloccare le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f450f-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="f450f-103">Quando gli utenti visualizzano i dati contenuti in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form, a volte devono fare spesso riferimento a una sola colonna o a un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="f450f-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="f450f-104">Ad esempio, quando si visualizza una tabella di informazioni sui clienti che contiene molte colonne, è utile visualizzare il nome del cliente in qualsiasi momento, pur consentendo ad altre colonne di scorrere al di fuori dell'area visibile.</span><span class="sxs-lookup"><span data-stu-id="f450f-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="f450f-105">A tale scopo, è possibile bloccare le colonne nel controllo.</span><span class="sxs-lookup"><span data-stu-id="f450f-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="f450f-106">Quando si blocca una colonna, vengono bloccate anche tutte le colonne alla sua sinistra (o alla sua destra, nelle lingue scritte da destra a sinistra).</span><span class="sxs-lookup"><span data-stu-id="f450f-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="f450f-107">Le colonne bloccate rimangono ferme mentre tutte le altre colonne possono scorrere.</span><span class="sxs-lookup"><span data-stu-id="f450f-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="f450f-108">Se viene abilitato il riordinamento delle colonne, le colonne bloccate vengono considerate come un gruppo distinto dalle colonne non bloccate.</span><span class="sxs-lookup"><span data-stu-id="f450f-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="f450f-109">Gli utenti possono riposizionare le colonne in entrambi i gruppi, ma non possono spostare una colonna da un gruppo all'altro.</span><span class="sxs-lookup"><span data-stu-id="f450f-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="f450f-110">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f450f-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f450f-111">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f450f-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="f450f-112">Per bloccare una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f450f-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="f450f-113">Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi selezionare **modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="f450f-113">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="f450f-114">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="f450f-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="f450f-115">Nella griglia **Proprietà colonna** impostare la <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="f450f-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f450f-116">È inoltre possibile bloccare una colonna quando viene aggiunta selezionando la casella **bloccati** nella finestra di dialogo **Aggiungi colonna** .</span><span class="sxs-lookup"><span data-stu-id="f450f-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="f450f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f450f-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f450f-118">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f450f-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="f450f-119">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f450f-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="f450f-120">[Procedura: visualizzare il testo da destra a sinistra in Windows Form per la globalizzazione](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f450f-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="f450f-121">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="f450f-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f450f-122">Procedura: aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="f450f-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
