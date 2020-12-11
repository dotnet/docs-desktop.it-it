---
title: Impedisci l'aggiunta e l'eliminazione di righe nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963541"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="6f699-102">Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="6f699-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="6f699-103">Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6f699-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6f699-104">Le nuove righe vengono immesse nella riga speciale per i nuovi record nella parte inferiore del controllo.</span><span class="sxs-lookup"><span data-stu-id="6f699-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="6f699-105">Quando si disabilita l'aggiunta di righe, la riga per i nuovi record non viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="6f699-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="6f699-106">È quindi possibile rendere il controllo interamente di sola lettura disabilitando l'eliminazione delle righe e la modifica delle celle.</span><span class="sxs-lookup"><span data-stu-id="6f699-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="6f699-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="6f699-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6f699-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6f699-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="6f699-109">Per impedire l'aggiunta e l'eliminazione di righe</span><span class="sxs-lookup"><span data-stu-id="6f699-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="6f699-110">Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi deselezionare le caselle di controllo **Consenti aggiunta** e **Abilita eliminazione** .</span><span class="sxs-lookup"><span data-stu-id="6f699-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f699-111">Per rendere il controllo interamente di sola lettura, deselezionare anche la casella di controllo **Abilita modifica** .</span><span class="sxs-lookup"><span data-stu-id="6f699-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f699-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f699-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6f699-113">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="6f699-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="6f699-114">Procedura: aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="6f699-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
