---
title: Riepilogo della tecnologia del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 1b620cabb756fadb8468fc75879025131e4bffd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951054"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Riepilogo della tecnologia del controllo DataGridView (Windows Form)

Questo argomento riepiloga le informazioni relative al controllo `DataGridView` e alle classi che ne supportano l'uso.  
  
 La visualizzazione dei dati in formato tabulare è un'attività che è probabile eseguire di frequente. Il `DataGridView` controllo è progettato per essere una soluzione completa per la presentazione dei dati in una griglia.  
  
## <a name="keywords"></a>Parole chiave  

 DataGridView, BindingSource, tabella, cella, data binding, modalità virtuale  
  
## <a name="namespaces"></a>Spazi dei nomi  

 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologie correlate  

 `BindingSource`  
  
## <a name="background"></a>Background  

 Le finestre di progettazione dell'interfaccia utente trovano spesso la necessità di visualizzare i dati tabulari agli utenti. Il .NET Framework offre diversi modi per visualizzare i dati in una tabella o in una griglia. Il `DataGridView` controllo rappresenta la più recente evoluzione di questa tecnologia per le applicazioni Windows Forms.  
  
 Il `DataGridView` controllo può visualizzare le righe di dati da un archivio dati. Sono supportati molti tipi di archivi dati. L'archivio dati può contenere dati semplici e non tipizzati, ad esempio una matrice unidimensionale, oppure può contenere dati tipizzati, ad esempio un oggetto <xref:System.Data.DataSet> . Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Il controllo `DataGridView` fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare. È possibile utilizzare il controllo per visualizzare le visualizzazioni di sola lettura o modificabili di set di dati di piccole e grandi dimensioni.  
  
 È possibile estendere il `DataGridView` controllo in diversi modi per creare comportamenti personalizzati nelle applicazioni. Ad esempio, è possibile specificare a livello di codice i propri algoritmi di ordinamento e creare i propri tipi di celle. È possibile personalizzare facilmente l'aspetto del controllo `DataGridView` scegliendo tra diverse proprietà. Molti tipi di archivi dati possono essere usati come origine dati oppure il `DataGridView` controllo può funzionare senza un'origine dati associata.  
  
## <a name="implementing-datagridview-classes"></a>Implementazione di classi DataGridView  

 Sono disponibili diversi modi per sfruttare le `DataGridView` funzionalità di estendibilità del controllo. È possibile personalizzare molti aspetti del controllo tramite eventi e proprietà, ma alcune personalizzazioni richiedono la creazione di nuove classi derivate dalle `DataGridView` classi esistenti.  
  
 Le classi base più utilizzate sono `DataGridViewCell` e `DataGridViewColumn` . È possibile derivare la propria classe di celle da `DataGridViewCell` o da qualsiasi classe figlio. Sebbene sia possibile aggiungere qualsiasi tipo di cella a qualsiasi colonna, in genere si deriva anche una classe di colonna complementare da `DataGridViewColumn` che ospita le celle del tipo di cella personalizzato per impostazione predefinita.  
  
 È possibile implementare l' `IDataGridViewEditingCell` interfaccia nella classe cella derivata per creare un tipo di cella con funzionalità di modifica, ma che non ospita un controllo in modalità di modifica. Per creare un controllo che può essere ospitato in una cella in modalità di modifica, è possibile implementare l' `IDataGridViewEditingControl` interfaccia in una classe derivata da <xref:System.Windows.Forms.Control> .  
  
 Per altre informazioni, vedere [How to: Customize Cells and Columns nel Windows Forms controllo DataGridView estendendo il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) e [procedura: ospitare i controlli in Windows Forms celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Riepilogo delle classi DataGridView  

 <xref:System.Windows.Forms>  
  
|Area tecnologica|Classi/interfacce/elementi di configurazione|  
|---------------------|-------------------------------------------------|  
|Data binding|<xref:System.Windows.Forms.BindingSource>|  
|Presentazione dei dati|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> classi derivate e<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> classi derivate e<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> classi derivate e<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Estendibilità|<xref:System.Windows.Forms.DataGridViewCell> classi derivate e<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> classi derivate e<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novità  

 Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per essere una soluzione completa per la visualizzazione dei dati tabulari con Windows Forms. È consigliabile prendere in considerazione l'uso del <xref:System.Windows.Forms.DataGridView> controllo prima di altre soluzioni, ad esempio <xref:System.Windows.Forms.DataGrid> , quando si crea una nuova applicazione. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo può funzionare in stretta combinazione con il <xref:System.Windows.Forms.BindingSource> componente. Questo componente è stato progettato per essere l'origine dati primaria di un modulo. Può gestire l'interazione tra un <xref:System.Windows.Forms.DataGridView> controllo e la relativa origine dati, indipendentemente dal tipo di origine dati.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo DataGridView](datagridview-control-overview-windows-forms.md)
- [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)
- [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information)
