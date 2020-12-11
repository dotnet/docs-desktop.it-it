---
title: 'Procedura: Aggiungere un controllo a una scheda'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: 9806583fda60f1cb8a5ef2d97f42eba158593f61
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962134"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="6ce90-102">Procedura: Aggiungere un controllo a una scheda</span><span class="sxs-lookup"><span data-stu-id="6ce90-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="6ce90-103">È possibile utilizzare il Windows Forms <xref:System.Windows.Forms.TabControl> per visualizzare altri controlli in modo organizzato.</span><span class="sxs-lookup"><span data-stu-id="6ce90-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="6ce90-104">Nella procedura seguente viene illustrato come aggiungere un pulsante alla prima scheda. Per informazioni sull'aggiunta di un'icona alla parte label di una scheda, vedere [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="6ce90-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="6ce90-105">Per aggiungere un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6ce90-105">To add a control programmatically</span></span>  
  
1. <span data-ttu-id="6ce90-106">Usare il <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> metodo della raccolta restituita dalla <xref:System.Windows.Forms.Control.Controls%2A> proprietà di <xref:System.Windows.Forms.TabPage> :</span><span class="sxs-lookup"><span data-stu-id="6ce90-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ce90-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ce90-107">See also</span></span>

- [<span data-ttu-id="6ce90-108">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="6ce90-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="6ce90-109">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="6ce90-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="6ce90-110">Procedura: Modificare l'aspetto di TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ce90-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="6ce90-111">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="6ce90-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="6ce90-112">Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ce90-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
