---
title: Aggiungere tabelle e colonne al controllo DataGrid utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 7d00deb453793f7fc1f1c5d59913cb704ad546d9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962260"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

È possibile visualizzare i dati nel <xref:System.Windows.Forms.DataGrid> controllo Windows Forms in tabelle e colonne creando <xref:System.Windows.Forms.DataGridTableStyle> oggetti e aggiungendoli all' <xref:System.Windows.Forms.GridTableStylesCollection> oggetto, a cui si accede tramite la <xref:System.Windows.Forms.DataGrid> proprietà del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> . In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella dati specificata nella <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà di <xref:System.Windows.Forms.DataGridTableStyle> . Per impostazione predefinita, uno stile di tabella senza gli stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne presenti nella tabella aggiungendo <xref:System.Windows.Forms.DataGridColumnStyle> oggetti all'oggetto, a <xref:System.Windows.Forms.GridColumnStylesCollection> cui si accede tramite la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà di ognuno di essi <xref:System.Windows.Forms.DataGridTableStyle> .

Le procedure riportate di seguito richiedono un progetto di **applicazione Windows** con un modulo che contiene un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni su come configurare tale progetto, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md). Per impostazione predefinita, in Visual Studio 2005 il <xref:System.Windows.Forms.DataGrid> controllo non si trova nella **casella degli strumenti**. Per informazioni sull'aggiunta, vedere [procedura: aggiungere elementi alla casella degli strumenti](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una tabella al controllo DataGrid nella finestra di progettazione

1. Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per altre informazioni, vedere [procedura: associare il controllo DataGrid Windows Forms a un'origine dati usando la finestra di progettazione](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. Selezionare la <xref:System.Windows.Forms.DataGrid> proprietà del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> nella finestra Proprietà, quindi fare clic sul pulsante con i puntini di sospensione ( ![ ...) nell'finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla proprietà per visualizzare l'editor della **raccolta DataGridTableStyle**.

3. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile tabella.

4. Fare clic su **OK** per chiudere l'editor della raccolta, quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto alla <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Proprietà.

     Quando si riapre l'editor della raccolta, tutte le tabelle dati associato al controllo verranno visualizzate nell'elenco a discesa per la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dello stile della tabella.

5. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della tabella.

6. Nella casella **Proprietà** dell'editor della raccolta selezionare il valore della <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> tabella che si desidera visualizzare.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una colonna al controllo DataGrid nella finestra di progettazione

1. Nella casella **membri** dell'editor della **raccolta DataGridTableStyle** Selezionare lo stile di tabella appropriato. Nella casella **Proprietà** dell'editor della raccolta, selezionare la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> raccolta, quindi fare clic sul pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla proprietà per visualizzare l' **Editor della raccolta DataGridColumnStyle**.

2. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile colonna oppure fare clic sulla freccia verso il basso accanto a **Aggiungi** per specificare un tipo di colonna.

     Nella casella di riepilogo a discesa è possibile selezionare il <xref:System.Windows.Forms.DataGridTextBoxColumn> <xref:System.Windows.Forms.DataGridBoolColumn> tipo o.

3. Fare clic su OK per chiudere l' **Editor della raccolta DataGridColumnStyle**, quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto alla <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Proprietà.

     Quando si riapre l'editor della raccolta, tutte le colonne di dati nella tabella di dati associata verranno visualizzate nell'elenco a discesa per la <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> proprietà dello stile della colonna.

4. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della colonna.

5. Nella casella **Proprietà** dell'editor della raccolta selezionare il <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valore per la colonna che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [DataGrid (controllo)](datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
