---
title: Impostare stili di cella e formati di dati predefiniti per il controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951047"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Forms usando la finestra di progettazione

Il <xref:System.Windows.Forms.DataGridView> controllo consente di specificare gli stili di cella predefiniti e i formati di dati delle celle per l'intero controllo, per colonne specifiche, per le intestazioni di riga e di colonna e per le righe alternate per creare un effetto Ledger. Gli stili predefiniti impostati per l'intero controllo vengono sottoposti a override dagli stili predefiniti impostati per le colonne e le righe alternate. Inoltre, gli stili impostati nel codice per singole righe e celle eseguono l'override degli stili predefiniti.

Per ulteriori informazioni sugli stili delle celle, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md). Per impostare gli stili per le righe alternate, vedere [procedura: impostare stili di righe alternate per il controllo Windows Forms DataGridView usando la finestra di progettazione](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).

È anche possibile impostare gli stili usando la <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà per influire su tutte le righe che verranno aggiunte al controllo. Per ulteriori informazioni sul modello di riga, vedere [procedura: utilizzare il modello di riga per personalizzare le righe nel controllo Windows Forms DataGridView](use-the-row-template-to-customize-rows-in-the-datagrid.md).

Per le procedure riportate di seguito è necessario un progetto di **applicazione Windows** con un modulo contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Per impostare gli stili predefiniti per tutte le celle nel controllo

1. Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.

2. Nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> proprietà, o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> . Verrà visualizzata la finestra di dialogo **Generatore CellStyle** .

3. Definire lo stile impostando le proprietà, usando il riquadro di **Anteprima** per confermare le scelte effettuate.

> [!NOTE]
> Se gli stili di visualizzazione sono abilitati, le intestazioni di riga e di colonna (ad eccezione di <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> ) vengono automaticamente disegnate in base al tema corrente, eseguendo l'override dei <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> valori delle proprietà e.
>
> È possibile impostare gli stili delle celle per più <xref:System.Windows.Forms.DataGridView> controlli selezionati usando la finestra di progettazione, ma solo se hanno valori identici per la proprietà di stile della cella che si vuole modificare. Se uno o più stili di cella sono diversi per tale proprietà, le finestre **Proprietà** della finestra di dialogo **Generatore CellStyle** saranno vuote.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Per impostare gli stili predefiniti per le celle in singole colonne

1. Fare clic con il pulsante destro del mouse sul <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione e scegliere **modifica colonne**.

2. Consente di selezionare una colonna nell'elenco **colonne selezionate** .

3. Nella griglia **Proprietà colonna** fare clic sul pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Proprietà. Verrà visualizzata la finestra di dialogo **Generatore CellStyle** .

4. Definire lo stile impostando le proprietà, usando il riquadro di **Anteprima** per confermare le scelte effettuate.

### <a name="to-format-data-in-cells"></a>Per formattare i dati nelle celle

1. Utilizzare una delle procedure precedenti per visualizzare una finestra di dialogo del **Generatore CellStyle** correlata a una proprietà di stile di cella predefinito.

2. Nella finestra di dialogo **Generatore di CellStyle** fare clic sul pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Proprietà. Verrà visualizzata la finestra di dialogo **stringa formato** .

3. Selezionare un tipo di formato, quindi modificare i dettagli del tipo (ad esempio il numero di posizioni decimali da visualizzare), usando la casella di **esempio** per confermare le scelte.

4. Se si associa il <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati che può contenere valori null, compilare la casella di testo **valore null** . Questo valore viene visualizzato quando il valore della cella è uguale a un riferimento null ( `Nothing` in Visual Basic) o <xref:System.DBNull.Value?displayProperty=nameWithType> .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms usando la finestra di progettazione](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Procedura: creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
