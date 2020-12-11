---
title: Formattare il controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964399"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Procedura: Formattare il controllo DataGrid di Windows Forms
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 L'applicazione di colori diversi a diverse parti di un <xref:System.Windows.Forms.DataGrid> controllo può contribuire a rendere le informazioni più semplici da leggere e interpretare. Il colore può essere applicato a righe e colonne. Le righe e le colonne possono anche essere nascoste o visualizzate a propria discrezione.  
  
 Sono disponibili tre aspetti di base per la formattazione del <xref:System.Windows.Forms.DataGrid> controllo. È possibile impostare le proprietà per stabilire uno stile predefinito in cui vengono visualizzati i dati. Da tale base è quindi possibile personalizzare la modalità di visualizzazione di determinate tabelle in fase di esecuzione. Infine, è possibile modificare le colonne visualizzate nella griglia dei dati, nonché i colori e altre formattazioni visualizzate.  
  
 Come passaggio iniziale per la formattazione di una griglia di dati, è possibile impostare le proprietà dell'oggetto <xref:System.Windows.Forms.DataGrid> stesso. Queste scelte di colore e formato costituiscono una base da cui è possibile apportare modifiche in base alle tabelle e alle colonne di dati visualizzate.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid  
  
1. Impostare le proprietà seguenti in base alle esigenze:  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La <xref:System.Windows.Forms.DataGrid.BackColor%2A> proprietà definisce il colore delle righe pari della griglia. Quando si imposta la <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà su un colore diverso, ogni altra riga viene impostata sul nuovo colore (righe 1, 3, 5 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre le <xref:System.Windows.Forms.DataGrid.BackColor%2A> <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà e determinano il colore delle righe nella griglia, la <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> proprietà determina il colore dell'area senza righe, che è visibile solo quando la griglia viene spostata nella parte inferiore o se solo alcune righe sono contenute nella griglia.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Stile del bordo della griglia, uno dei <xref:System.Windows.Forms.BorderStyle> valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Colore di sfondo della didascalia della finestra della griglia visualizzata immediatamente sopra la griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Il tipo di carattere della didascalia nella parte superiore della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Colore di sfondo della didascalia della finestra della griglia.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Tipo di carattere utilizzato per visualizzare il testo nella griglia.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Colore del tipo di carattere visualizzato dai dati nelle righe della griglia dei dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Colore delle linee della griglia dei dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Stile delle linee che separano le celle della griglia, uno dei valori di <xref:System.Windows.Forms.DataGridLineStyle> enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Colore di sfondo delle intestazioni di riga e colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Tipo di carattere utilizzato per le intestazioni di colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione di colonna e i glifi più/meno (per espandere le righe quando vengono visualizzate più tabelle correlate).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Colore del testo di tutti i collegamenti nella griglia dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In una tabella figlio si tratta del colore di sfondo delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In una tabella figlio si tratta del colore di primo piano delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina se i nomi della tabella e della colonna vengono visualizzati nella riga padre, per mezzo dell' <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Larghezza predefinita (in pixel) delle colonne della griglia. Impostare questa proprietà prima di reimpostare <xref:System.Windows.Forms.DataGrid.DataSource%2A> le <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà e (separatamente o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo) oppure la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Altezza della riga, in pixel, delle righe della griglia. Impostare questa proprietà prima di reimpostare <xref:System.Windows.Forms.DataGrid.DataSource%2A> le <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà e (separatamente o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo) oppure la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Larghezza delle intestazioni di riga della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Quando si seleziona una riga o una cella, si tratta del colore di sfondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Quando si seleziona una riga o una cella, questo è il colore di primo piano.|  
  
    > [!NOTE]
    > Tenere presente che, quando si personalizzano i colori dei controlli, è possibile rendere il controllo inaccessibile, a causa di una scelta di colori insufficiente (ad esempio, rosso e verde). Usare i colori disponibili nella tavolozza **colori di sistema** per evitare questo problema.  
  
     Nelle procedure riportate di seguito si presuppone che il form disponga <xref:System.Windows.Forms.DataGrid> di un controllo associato a una tabella di dati. Per ulteriori informazioni, vedere [associazione del controllo Windows Forms DataGrid a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Per impostare lo stile della tabella e della colonna di una tabella dati a livello di codice  
  
1. Creare un nuovo stile di tabella e impostarne le proprietà.  
  
2. Creare uno stile colonna e impostarne le proprietà.  
  
3. Aggiungere lo stile della colonna alla raccolta di stili di colonna dello stile della tabella.  
  
4. Aggiungere lo stile della tabella alla raccolta di stili di tabella della griglia dati.  
  
5. Nell'esempio riportato di seguito, creare un'istanza di un nuovo oggetto <xref:System.Windows.Forms.DataGridTableStyle> e impostarne la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Proprietà.  
  
6. Creare una nuova istanza di un oggetto **GridColumnStyle** e impostarne il **MappingName** (e altre proprietà di layout e visualizzazione).  
  
7. Ripetere i passaggi da 2 a 6 per ogni stile di colonna che si desidera creare.  
  
     Nell'esempio seguente viene illustrato il modo <xref:System.Windows.Forms.DataGridTextBoxColumn> in cui viene creato un oggetto, perché un nome deve essere visualizzato nella colonna. Inoltre, è possibile aggiungere lo stile della colonna a <xref:System.Windows.Forms.GridColumnStylesCollection> dello stile della tabella e aggiungere lo stile della tabella all'oggetto <xref:System.Windows.Forms.GridTableStylesCollection> della griglia dei dati.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName
       ' to the name of a DataColumn in the DataTable.
       ' Set the HeaderText and Width properties.
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to
       ' the GridTableStylesCollection.
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName
       // to the name of a DataColumn in the DataTable.
       // Set the HeaderText and Width properties.
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to
       // the GridTableStylesCollection.
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName
          // to the name of a DataColumn in the DataTable.
          // Set the HeaderText and Width properties.
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to
          // the GridTableStylesCollection.
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (controllo)](datagrid-control-windows-forms.md)
