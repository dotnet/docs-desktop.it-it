---
title: Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 83643d8acea706bad439683702e4228d240b97bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961411"
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView
In questa panoramica viene illustrato l'ordine di precedenza per le proprietà utilizzate per personalizzare un'intestazione di colonna in <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>Personalizzazione di un'intestazione di colonna in GridView  
 Le proprietà che definiscono il contenuto, il layout e lo stile di un'intestazione di colonna in un oggetto <xref:System.Windows.Controls.GridView> sono disponibili in molte classi correlate. Alcune di queste proprietà hanno funzionalità simili o uguali.  
  
 Le righe nella tabella seguente illustrano i gruppi di proprietà che eseguono la stessa funzione. È possibile utilizzare queste proprietà per personalizzare le intestazioni di colonna in un oggetto <xref:System.Windows.Controls.GridView> . L'ordine di precedenza per le proprietà correlate è da destra a sinistra, in cui la proprietà nella colonna più a destra ha la precedenza più alta. Se, ad esempio, un <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> oggetto è impostato sull' <xref:System.Windows.Controls.GridViewColumnHeader> oggetto e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> è impostato sull'oggetto associato <xref:System.Windows.Controls.GridViewColumn> , <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> avrà la precedenza. In questo scenario, <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> non ha alcun effetto.  
  
 **Proprietà correlate per le intestazioni di colonna in GridView**  
  
|||||  
|-|-|-|-|  
|**Classi**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Proprietà del menu di scelta rapida**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Non applicabile|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **Proprietà**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Non applicabile|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Modello di intestazione**<br /><br /> **Proprietà**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A><sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Proprietà di stile**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup> Per le **proprietà del modello di intestazione**, se si impostano le proprietà del selettore modello e modello, la proprietà modello ha la precedenza. Se ad esempio si impostano entrambe <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> le <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà e, la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà avrà la precedenza.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
