---
title: Formattazione dei dati nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 3a09acf72841a2135ed2d155f3715ccc30860856
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951090"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formattazione di dati nel controllo DataGridView di Windows Form

Il <xref:System.Windows.Forms.DataGridView> controllo fornisce la conversione automatica tra i valori delle celle e i tipi di dati visualizzati nelle colonne padre. Le colonne della casella di testo, ad esempio, visualizzano le rappresentazioni di stringa di valori di data, ora, numero e enumerazione e convertono i valori di stringa immessi dall'utente nei tipi richiesti dall'archivio dati.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formattazione con la classe DataGridViewCellStyle  

 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce la formattazione dei dati di base dei valori delle celle attraverso la <xref:System.Windows.Forms.DataGridViewCellStyle> classe. È possibile usare la <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> proprietà per formattare i valori di data, ora, numero ed enumerazione per le impostazioni cultura predefinite correnti usando gli identificatori di formato descritti in [formattazione dei tipi](/dotnet/standard/base-types/formatting-types). È anche possibile formattare questi valori per impostazioni cultura specifiche usando la <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> Proprietà. Il formato specificato viene usato sia per visualizzare i dati che per analizzare i dati immessi dall'utente nel formato specificato.  
  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> classe fornisce proprietà di formattazione aggiuntive per WordWrap, l'allineamento del testo e la visualizzazione personalizzata dei valori di database null. Per altre informazioni, vedere [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formattazione con l'evento CellFormatting  

 Se la formattazione di base non soddisfa le proprie esigenze, è possibile fornire la formattazione dei dati personalizzata in un gestore per l' <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. Il <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> passato al gestore dispone di una <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> proprietà che contiene inizialmente il valore della cella. In genere, questo valore viene convertito automaticamente nel tipo di visualizzazione. Per convertire il valore manualmente, impostare la <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> proprietà su un valore del tipo di visualizzazione.  
  
> [!NOTE]
> Se è attiva una stringa di formato per la cella, la modifica del valore della proprietà viene sostituita <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> a meno che non si imposti la <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> proprietà su `true` .  
  
 L' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento è utile anche quando si desidera impostare le <xref:System.Windows.Forms.DataGridViewCellStyle> proprietà per le singole celle in base ai relativi valori. Per altre informazioni, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Se l'analisi predefinita dei valori specificati dall'utente non soddisfa le proprie esigenze, è possibile gestire l' <xref:System.Windows.Forms.DataGridView.CellParsing> evento del <xref:System.Windows.Forms.DataGridView> controllo per fornire l'analisi personalizzata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Visualizzazione di dati nel controllo DataGridView Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
