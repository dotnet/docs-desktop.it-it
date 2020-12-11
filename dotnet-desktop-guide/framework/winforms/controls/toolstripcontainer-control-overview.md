---
title: Cenni preliminari sul controllo ToolStripContainer
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966565"
---
# <a name="toolstripcontainer-control-overview"></a>Cenni preliminari sul controllo ToolStripContainer
Un oggetto <xref:System.Windows.Forms.ToolStripContainer> dispone di pannelli sui lati sinistro, destro, superiore e inferiore per il posizionamento e il raggruppamento di <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> controlli, e <xref:System.Windows.Forms.StatusStrip> . Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra. Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso. È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.  
  
 Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati. Ogni pannello di un <xref:System.Windows.Forms.ToolStripContainer> è espandibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.  
  
### <a name="important-toolstripcontainer-members"></a>Membri di ToolStripContainer importanti  
  
|Name|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Ottiene il pannello inferiore dell'oggetto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello inferiore dell'oggetto <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Ottiene il pannello sinistro dell'oggetto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello sinistro di <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Ottiene il pannello destro di <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello destro di <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Ottiene il pannello superiore di <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Ottiene o imposta un valore che indica se il pannello superiore di <xref:System.Windows.Forms.ToolStripContainer> è visibile.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
