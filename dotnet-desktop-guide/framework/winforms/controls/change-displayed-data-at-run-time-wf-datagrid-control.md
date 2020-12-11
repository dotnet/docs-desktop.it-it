---
title: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 41f22b3149c1d411dcfbdeec4b83c6c0c52c10df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952584"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid di Windows Forms

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Dopo aver creato un Windows Forms <xref:System.Windows.Forms.DataGrid> utilizzando le funzionalità della fase di progettazione, è possibile che si desideri modificare dinamicamente gli elementi dell' <xref:System.Data.DataSet> oggetto della griglia in fase di esecuzione. Possono essere incluse modifiche ai singoli valori della tabella o alla modifica dell'origine dati associata al <xref:System.Windows.Forms.DataGrid> controllo. Le modifiche ai singoli valori vengono eseguite tramite l' <xref:System.Data.DataSet> oggetto, non il <xref:System.Windows.Forms.DataGrid> controllo.  
  
### <a name="to-change-data-programmatically"></a>Per modificare i dati a livello di programmazione  
  
1. Specificare la tabella desiderata dall' <xref:System.Data.DataSet> oggetto e la riga e il campo desiderati dalla tabella e impostare la cella su un valore uguale a quello nuovo.  
  
    > [!NOTE]
    > Per specificare la prima tabella di <xref:System.Data.DataSet> o la prima riga della tabella, utilizzare 0.  
  
     Nell'esempio seguente viene illustrato come modificare la seconda voce della prima riga della prima tabella di un set di dati facendo clic su `Button1` . Le <xref:System.Data.DataSet> `ds` tabelle () e ( `0` e `1` ) sono state create in precedenza.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     In fase di esecuzione è possibile usare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo per associare il <xref:System.Windows.Forms.DataGrid> controllo a un'origine dati diversa. Ad esempio, è possibile disporre di diversi controlli dati ADO.NET, ciascuno connesso a un database diverso.  
  
### <a name="to-change-the-datasource-programmatically"></a>Per modificare l'origine dati a livello di codice  
  
1. Impostare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo sul nome dell'origine dati e della tabella a cui si desidera eseguire l'associazione.  
  
     Nell'esempio seguente viene illustrato come modificare l'origine della data utilizzando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo in un controllo dati ADO.NET (adoPubsAuthors) connesso alla tabella authors nel database pubs.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Dataset ADO.NET](/dotnet/framework/data/adonet/ado-net-datasets)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
