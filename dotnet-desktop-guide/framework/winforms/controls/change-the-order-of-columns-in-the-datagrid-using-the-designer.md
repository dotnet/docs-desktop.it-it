---
title: Modificare l'ordine delle colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952589"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="258e0-102">Procedura: Modificare l'ordine delle colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="258e0-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="258e0-103">Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo Windows Forms a un'origine dati, l'ordine di visualizzazione delle colonne generate automaticamente è determinato dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="258e0-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="258e0-104">Se l'ordine non è quello desiderato, è possibile modificare l'ordine delle colonne utilizzando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="258e0-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="258e0-105">È anche possibile aggiungere colonne non vincolate al controllo e modificarne l'ordine di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="258e0-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="258e0-106">Per informazioni su come modificare l'ordine delle colonne a livello di codice, vedere [procedura: modificare l'ordine delle colonne nel controllo Windows Forms DataGridView](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="258e0-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="258e0-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="258e0-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="258e0-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="258e0-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="258e0-109">Per modificare l'ordine delle colonne utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="258e0-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="258e0-110">Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllo, quindi selezionare **modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="258e0-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="258e0-111">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="258e0-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="258e0-112">Fare clic sulla freccia in su o in giù a destra dell'elenco **colonne selezionate** fino a quando la colonna selezionata non si trova nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="258e0-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="258e0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="258e0-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="258e0-114">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="258e0-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="258e0-115">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="258e0-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="258e0-116">Procedura: aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="258e0-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
