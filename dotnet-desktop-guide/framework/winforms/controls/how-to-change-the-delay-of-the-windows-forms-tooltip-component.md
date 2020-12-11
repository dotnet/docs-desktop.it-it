---
title: Modificare il ritardo del componente della descrizione comando
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963958"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="2feb8-102">Procedura: Modificare il ritardo del componente ToolTip di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2feb8-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="2feb8-103">Sono disponibili più valori di ritardo che è possibile impostare per un <xref:System.Windows.Forms.ToolTip> componente Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2feb8-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="2feb8-104">L'unità di misura per tutte queste proprietà è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="2feb8-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="2feb8-105">La <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> proprietà determina per quanto tempo l'utente deve puntare al controllo associato affinché venga visualizzata la stringa della descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="2feb8-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="2feb8-106">La <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> proprietà imposta il numero di millisecondi necessari per la visualizzazione delle stringhe di descrizione comando successive quando il mouse passa da un controllo associato alla descrizione comando a un altro.</span><span class="sxs-lookup"><span data-stu-id="2feb8-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="2feb8-107">La <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> proprietà determina il periodo di tempo in cui viene visualizzata la stringa della descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="2feb8-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="2feb8-108">È possibile impostare questi valori singolarmente oppure impostando il valore della <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà. le altre proprietà delay vengono impostate in base al valore assegnato alla <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="2feb8-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="2feb8-109">Ad esempio, quando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> è impostato su un valore n, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> viene impostato su n, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> viene impostato sul valore di <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> diviso per cinque (o N/5) e <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> viene impostato su un valore che corrisponde a cinque volte il valore della <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Proprietà (o 5N).</span><span class="sxs-lookup"><span data-stu-id="2feb8-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="2feb8-110">Per impostare il ritardo</span><span class="sxs-lookup"><span data-stu-id="2feb8-110">To set the delay</span></span>  
  
1. <span data-ttu-id="2feb8-111">Impostare le proprietà seguenti, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="2feb8-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2feb8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2feb8-112">See also</span></span>

- [<span data-ttu-id="2feb8-113">Panoramica del componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="2feb8-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="2feb8-114">Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2feb8-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="2feb8-115">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="2feb8-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
