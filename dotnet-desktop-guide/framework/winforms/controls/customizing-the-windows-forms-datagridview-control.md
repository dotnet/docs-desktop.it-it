---
title: Personalizzare il controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951118"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizzazione del controllo DataGridView Windows Form
Il `DataGridView` controllo fornisce diverse proprietà che è possibile utilizzare per modificare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne. Se si hanno esigenze speciali che vanno oltre le funzionalità della <xref:System.Windows.Forms.DataGridViewCellStyle> classe, tuttavia, è anche possibile implementare il disegno del proprietario per il controllo o estenderne le funzionalità creando celle, colonne e righe personalizzate.  
  
 Per disegnare le celle e le righe manualmente, è possibile gestire vari `DataGridView` eventi del disegno. Per modificare la funzionalità esistente o fornire nuove funzionalità, è possibile creare tipi personalizzati derivati dai `DataGridViewCell` `DataGridViewColumn` tipi, e esistenti `DataGridViewRow` . È anche possibile fornire nuove funzionalità di modifica creando tipi derivati che visualizzano un controllo a scelta quando una cella è in modalità di modifica.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Viene descritto come gestire l' <xref:System.Windows.Forms.DataGridView.CellPainting> evento per disegnare manualmente le celle.  
  
 [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Viene descritto come gestire gli <xref:System.Windows.Forms.DataGridView.RowPrePaint> eventi e per <xref:System.Windows.Forms.DataGridView.RowPostPaint> disegnare le righe con uno sfondo sfumato personalizzato e un contenuto che si estende su più colonne.  
  
 [Procedura: Personalizzare celle e colonne nel controllo DataGridView di Windows Forms estendendone il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e per `DataGridViewColumn` evidenziare le celle quando il puntatore del mouse viene posizionato su di essi.  
  
 [Procedura: Disabilitare i pulsanti in una colonna dei pulsanti nel controllo DataGridView di Windows Forms](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e per <xref:System.Windows.Forms.DataGridViewButtonColumn> visualizzare i pulsanti disabilitati in una colonna di un pulsante.  
  
 [Procedura: Ospitare controlli nelle celle DataGridView di Windows Forms](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Viene descritto come implementare l' `IDataGridViewEditingControl` interfaccia e creare tipi personalizzati derivati da `DataGridViewCell` e per `DataGridViewColumn` visualizzare un <xref:System.Windows.Forms.DateTimePicker> controllo quando una cella è in modalità di modifica.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewCell> classe.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewRow> classe.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewColumn> classe.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione e stile di base nel controllo DataGridView Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Tipi di colonna nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
