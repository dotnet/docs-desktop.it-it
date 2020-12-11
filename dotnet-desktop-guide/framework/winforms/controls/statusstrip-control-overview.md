---
title: Cenni preliminari sul controllo StatusStrip
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: 9f2426220e8fe0f13d2098de8975be2ad2e43845
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964273"
---
# <a name="statusstrip-control-overview"></a>Cenni preliminari sul controllo StatusStrip

In un controllo <xref:System.Windows.Forms.StatusStrip> sono in genere presenti informazioni su un oggetto visualizzato su un <xref:System.Windows.Forms.Form>, sui componenti dell'oggetto o informazioni contestuali collegate alle operazioni di tale oggetto all'interno dell'applicazione. In genere, un controllo <xref:System.Windows.Forms.StatusStrip> è composto da oggetti <xref:System.Windows.Forms.ToolStripStatusLabel>, in ciascuno dei quali è visualizzato un testo e/o un'icona. Il controllo <xref:System.Windows.Forms.StatusStrip> può contenere anche controlli <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> e <xref:System.Windows.Forms.ToolStripProgressBar>.  
  
 Il valore predefinito <xref:System.Windows.Forms.StatusStrip> non ha pannelli. Per aggiungere pannelli a un controllo <xref:System.Windows.Forms.StatusStrip> usare il metodo <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.  
  
 Esiste supporto completo per la gestione di elementi e comandi comuni di <xref:System.Windows.Forms.StatusStrip> in Visual Studio.  
  
 Vedere anche [StatusStrip editor della raccolta Items](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) e finestra di [dialogo attività di StatusStrip](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).  
  
 Benché il controllo <xref:System.Windows.Forms.StatusStrip> sostituisca ed estenda il controllo <xref:System.Windows.Forms.StatusBar> delle versioni precedenti, il controllo <xref:System.Windows.Forms.StatusBar> viene mantenuto per compatibilità con le versioni precedenti e per eventuale uso futuro.  
  
### <a name="important-statusstrip-members"></a>Membri importanti di StatusStrip  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.StatusStrip> supporta la funzionalità di overflow.|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.StatusStrip> si estende da un'estremità all'altra nella propria classe <xref:System.Windows.Forms.ToolStripContainer>.|  
  
### <a name="important-statusstrip-companion-classes"></a>Classi importanti correlate a StatusStrip  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Rappresenta un pannello in un controllo <xref:System.Windows.Forms.StatusStrip>.|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Visualizza un oggetto <xref:System.Windows.Forms.ToolStripDropDown> associato dal quale l'utente può selezionare un singolo elemento.|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Rappresenta un controllo in due parti con un pulsante standard e un menu a discesa.|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Visualizza lo stato di completamento di un processo.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
