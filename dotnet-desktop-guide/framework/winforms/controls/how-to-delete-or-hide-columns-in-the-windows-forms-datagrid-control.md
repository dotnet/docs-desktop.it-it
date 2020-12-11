---
title: Eliminare o nascondere colonne nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961912"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile eliminare o nascondere a livello di codice le colonne nel <xref:System.Windows.Forms.DataGrid> controllo Windows Forms usando le proprietà e i metodi <xref:System.Windows.Forms.GridColumnStylesCollection> degli <xref:System.Windows.Forms.DataGridColumnStyle> oggetti e (che sono membri della <xref:System.Windows.Forms.DataGridTableStyle> classe).  
  
 Le colonne eliminate o nascoste sono ancora presenti nell'origine dati a cui è associata la griglia ed è comunque possibile accedervi a livello di codice. Non sono più visibili nell'elemento DataGrid.  
  
> [!NOTE]
> Se l'applicazione non accede ad alcune colonne di dati e non si desidera che vengano visualizzate nel DataGrid, è probabile che non sia necessario includerle nell'origine dati.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Per eliminare una colonna da DataGrid a livello di codice  
  
1. Nell'area dichiarazioni del form dichiarare una nuova istanza della <xref:System.Windows.Forms.DataGridTableStyle> classe.  
  
2. Impostare la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> proprietà sulla tabella nell'origine dati a cui si desidera applicare lo stile. Nell'esempio seguente viene usata la <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, che presuppone che sia già impostata.  
  
3. Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella del DataGrid.  
  
4. Chiamare il <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> metodo della <xref:System.Windows.Forms.DataGrid> raccolta di <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> , specificando l'indice di colonna della colonna da eliminare.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Per nascondere una colonna nella griglia a livello di codice  
  
1. Nell'area dichiarazioni del form dichiarare una nuova istanza della <xref:System.Windows.Forms.DataGridTableStyle> classe.  
  
2. Impostare la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dell'oggetto sulla <xref:System.Windows.Forms.DataGridTableStyle> tabella nell'origine dati a cui si desidera applicare lo stile. Nell'esempio di codice seguente viene usata la <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, che presuppone è già impostata.  
  
3. Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella del DataGrid.  
  
4. Nascondere la colonna impostando la relativa `Width` proprietà su 0, specificando l'indice di colonna della colonna da nascondere.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid di Windows Forms](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
