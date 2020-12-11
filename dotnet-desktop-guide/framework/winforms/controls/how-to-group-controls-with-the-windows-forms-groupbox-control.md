---
title: Controlli di gruppo con il controllo GroupBox
description: Informazioni su come raggruppare i controlli con il controllo GroupBox Windows Forms in modo che sia possibile creare un raggruppamento visivo di elementi correlati.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963823"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="66993-103">Procedura: Raggruppare i controlli con il controllo GroupBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66993-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="66993-104"><xref:System.Windows.Forms.GroupBox>I controlli Windows Forms vengono usati per raggruppare altri controlli.</span><span class="sxs-lookup"><span data-stu-id="66993-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="66993-105">Esistono tre motivi per raggruppare i controlli:</span><span class="sxs-lookup"><span data-stu-id="66993-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="66993-106">Per creare un raggruppamento visivo di elementi del form correlati per un'interfaccia utente chiara.</span><span class="sxs-lookup"><span data-stu-id="66993-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="66993-107">Per creare un raggruppamento programmatico (ad esempio, di pulsanti di opzione).</span><span class="sxs-lookup"><span data-stu-id="66993-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="66993-108">Per lo sviluppo di controlli come unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="66993-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="66993-109">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="66993-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="66993-110">Creare un <xref:System.Windows.Forms.GroupBox> controllo in un form.</span><span class="sxs-lookup"><span data-stu-id="66993-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="66993-111">Aggiungere altri controlli alla casella di gruppo, disegnando ognuno all'interno della casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="66993-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="66993-112">Se si dispone di controlli esistenti che si desidera racchiudere in una casella di gruppo, è possibile selezionare tutti i controlli, tagliarli negli Appunti, selezionare il <xref:System.Windows.Forms.GroupBox> controllo e incollarli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="66993-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="66993-113">È anche possibile trascinarli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="66993-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="66993-114">Impostare la <xref:System.Windows.Forms.GroupBox.Text%2A> proprietà della casella di gruppo su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="66993-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66993-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66993-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="66993-116">Controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="66993-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
