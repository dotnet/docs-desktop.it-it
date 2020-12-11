---
title: Creare elenchi di Master-Detail con il controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961930"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Forms
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Se <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile usare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato Master/Details. Una <xref:System.Windows.Forms.DataGrid> viene designata come griglia master e la seconda viene designata come griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlate vengono visualizzate nell'elenco dettagli. Se, ad esempio, <xref:System.Data.DataSet> contiene una tabella Customers e una tabella Orders correlata, è necessario specificare la tabella Customers come griglia master e la tabella Orders come griglia dei dettagli. Quando un cliente viene selezionato dalla griglia master, tutti gli ordini associati a tale cliente nella tabella Orders vengono visualizzati nella griglia dei dettagli.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Per impostare una relazione master/dettagli a livello di codice  
  
1. Creare due nuovi <xref:System.Windows.Forms.DataGrid> controlli e impostarne le proprietà.  
  
2. Aggiungere tabelle al set di dati.  
  
3. Dichiarare una variabile di tipo <xref:System.Data.DataRelation> per rappresentare la relazione che si desidera creare.  
  
4. Creare un'istanza della relazione specificando un nome per la relazione e specificando la tabella, la colonna e l'elemento che collegheranno le due tabelle.  
  
5. Aggiungere la relazione alla <xref:System.Data.DataSet> raccolta dell'oggetto <xref:System.Data.DataSet.Relations%2A> .  
  
6. Utilizzare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo dell'oggetto <xref:System.Windows.Forms.DataGrid> per associare ogni griglia a <xref:System.Data.DataSet> .  
  
     Nell'esempio seguente viene illustrato come impostare una relazione Master/Detail tra le tabelle Customers e Orders in un oggetto generato in precedenza <xref:System.Data.DataSet> ( `ds` ).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [DataGrid (controllo)](datagrid-control-windows-forms.md)
- [Panoramica del controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
