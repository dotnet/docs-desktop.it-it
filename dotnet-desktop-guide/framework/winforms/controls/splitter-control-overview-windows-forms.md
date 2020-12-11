---
title: Panoramica del controllo Splitter
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960961"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="a74d4-102">Cenni preliminari sul controllo Splitter (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="a74d4-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a74d4-103">Benché il controllo <xref:System.Windows.Forms.SplitContainer> sostituisca il controllo <xref:System.Windows.Forms.Splitter> delle versioni precedenti aggiungendo funzionalità, il controllo <xref:System.Windows.Forms.Splitter> viene mantenuto per compatibilità con le versioni precedenti e per utilizzo futuro se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="a74d4-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a74d4-104"><xref:System.Windows.Forms.Splitter>I controlli Windows Forms vengono usati per ridimensionare i controlli ancorati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a74d4-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="a74d4-105">Il <xref:System.Windows.Forms.Splitter> controllo viene spesso usato nei form con controlli con lunghezze diverse di dati da presentare, ad esempio Esplora risorse, i cui riquadri dati contengono informazioni di larghezze variabili in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="a74d4-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="a74d4-106">Utilizzo del controllo Splitter</span><span class="sxs-lookup"><span data-stu-id="a74d4-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="a74d4-107">Quando l'utente punta il puntatore del mouse sul bordo non ancorato di un controllo che può essere ridimensionato da un controllo Splitter, il puntatore cambia l'aspetto per indicare che è possibile ridimensionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="a74d4-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="a74d4-108">Con il controllo Splitter, l'utente può ridimensionare il controllo ancorato che si trova immediatamente prima.</span><span class="sxs-lookup"><span data-stu-id="a74d4-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="a74d4-109">Pertanto, per consentire all'utente di ridimensionare un controllo ancorato in fase di esecuzione, ancorare il controllo da ridimensionare a un bordo di un contenitore e quindi ancorare un controllo Splitter allo stesso lato del contenitore.</span><span class="sxs-lookup"><span data-stu-id="a74d4-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74d4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a74d4-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="a74d4-111">Procedura: ancorare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a74d4-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="a74d4-112">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a74d4-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
