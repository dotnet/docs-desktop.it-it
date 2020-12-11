---
title: "Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli"
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 33e07bb655d81c6a802ebdce871a2fed845a5c96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964861"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="62571-102">Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli</span><span class="sxs-lookup"><span data-stu-id="62571-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="62571-103">La procedura seguente illustra i passaggi di base per la configurazione dell'Unione automatica in un'applicazione con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip> .</span><span class="sxs-lookup"><span data-stu-id="62571-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="62571-104">Per impostare l'Unione automatica dei menu</span><span class="sxs-lookup"><span data-stu-id="62571-104">To set up automatic menu merging</span></span>  
  
1. <span data-ttu-id="62571-105">Creare il form padre MDI impostando la relativa <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="62571-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="62571-106">Aggiungere un oggetto <xref:System.Windows.Forms.MenuStrip> all'elemento padre MDI, impostando la relativa <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà su <xref:System.Windows.Forms.MenuStrip> .</span><span class="sxs-lookup"><span data-stu-id="62571-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3. <span data-ttu-id="62571-107">Creare un form figlio MDI e impostare la relativa <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.</span><span class="sxs-lookup"><span data-stu-id="62571-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4. <span data-ttu-id="62571-108">Aggiungere un oggetto <xref:System.Windows.Forms.MenuStrip> al form figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="62571-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5. <span data-ttu-id="62571-109">Nel form figlio, impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di su <xref:System.Windows.Forms.MenuStrip> `false` .</span><span class="sxs-lookup"><span data-stu-id="62571-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6. <span data-ttu-id="62571-110">Aggiungere voci di menu al form figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire nel form padre <xref:System.Windows.Forms.MenuStrip> quando viene attivato il form figlio.</span><span class="sxs-lookup"><span data-stu-id="62571-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7. <span data-ttu-id="62571-111">Utilizzare la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà nelle voci di menu del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di Unione nel form padre.</span><span class="sxs-lookup"><span data-stu-id="62571-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62571-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62571-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="62571-113">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="62571-113">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
