---
title: Formattazione e stile di base nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952643"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Formattazione e stile di base nel controllo DataGridView Windows Form
Il `DataGridView` controllo consente di definire in modo semplice l'aspetto di base delle celle e la formattazione di visualizzazione dei valori delle celle. È possibile definire gli stili di aspetto e formattazione per le singole celle, per le celle in colonne e righe specifiche o per tutte le celle nel controllo impostando le proprietà degli oggetti a cui si `DataGridViewCellStyle` accede tramite varie `DataGridView` proprietà del controllo. Inoltre, è possibile modificare questi stili in modo dinamico in base a fattori come il valore della cella gestendo l' `CellFormatting` evento.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Viene descritto come impostare le `DataGridView` proprietà che definiscono l'aspetto del bordo del controllo e le linee limite tra le celle.  
  
 [Stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)  
 Descrive la `DataGridViewCellStyle` classe e il modo in cui le proprietà di quel tipo interagiscono per definire come vengono visualizzate le celle nel controllo.  
  
 [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare le `DataGridViewCellStyle` proprietà per definire l'aspetto predefinito delle celle in righe e colonne specifiche e nell'intero controllo.  
  
 [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come formattare i valori di visualizzazione delle celle usando le `DataGridViewCellStyle` Proprietà.  
  
 [Procedura: Impostare gli stili di carattere e colore nel controllo DataGridView di Windows Form](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare la `DefaultCellStyle` proprietà per impostare le caratteristiche di visualizzazione di base per tutte le celle nel controllo.  
  
 [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Viene descritto come creare un effetto di tipo Ledger nel controllo utilizzando righe alternate visualizzate in modo diverso.  
  
 [Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Viene descritto come utilizzare la `RowTemplate` proprietà per impostare le proprietà delle righe che verranno utilizzate per tutte le righe nel controllo.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewCellStyle> classe.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Fornisce la documentazione di riferimento per l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Proprietà.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Personalizzazione del controllo DataGridView Windows Form](customizing-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.  
  
 [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Fornisce argomenti che descrivono le proprietà di celle, righe e colonne comunemente utilizzate.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
