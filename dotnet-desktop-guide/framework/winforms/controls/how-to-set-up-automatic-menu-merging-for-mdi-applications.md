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
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>Procedura: Configurare l'unione automatica dei menu per applicazioni con interfaccia a documenti multipli
La procedura seguente illustra i passaggi di base per la configurazione dell'Unione automatica in un'applicazione con interfaccia a documenti multipli (MDI) con <xref:System.Windows.Forms.MenuStrip> .  
  
### <a name="to-set-up-automatic-menu-merging"></a>Per impostare l'Unione automatica dei menu  
  
1. Creare il form padre MDI impostando la relativa <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà su `true` .  
  
2. Aggiungere un oggetto <xref:System.Windows.Forms.MenuStrip> all'elemento padre MDI, impostando la relativa <xref:System.Windows.Forms.Form.MainMenuStrip%2A> proprietà su <xref:System.Windows.Forms.MenuStrip> .  
  
3. Creare un form figlio MDI e impostare la relativa <xref:System.Windows.Forms.Form.MdiParent%2A> proprietà sul nome del form padre.  
  
4. Aggiungere un oggetto <xref:System.Windows.Forms.MenuStrip> al form figlio MDI.  
  
5. Nel form figlio, impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di su <xref:System.Windows.Forms.MenuStrip> `false` .  
  
6. Aggiungere voci di menu al form figlio <xref:System.Windows.Forms.MenuStrip> che si desidera unire nel form padre <xref:System.Windows.Forms.MenuStrip> quando viene attivato il form figlio.  
  
7. Utilizzare la <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> proprietà nelle voci di menu del form figlio <xref:System.Windows.Forms.MenuStrip> per controllare la modalità di Unione nel form padre.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
