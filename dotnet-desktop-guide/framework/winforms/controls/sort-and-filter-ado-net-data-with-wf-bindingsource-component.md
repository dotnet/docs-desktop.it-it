---
title: Ordinare e filtrare i dati di ADO.NET con il componente BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 404e67f1eeed240a171cb1cfef9094a746c3cecb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951394"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms

È possibile esporre le funzionalità di ordinamento e filtro del <xref:System.Windows.Forms.BindingSource> controllo tramite le <xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà e. È possibile applicare l'ordinamento semplice quando l'origine dati sottostante è un oggetto <xref:System.ComponentModel.IBindingList> ed è possibile applicare il filtro e l'ordinamento avanzato quando l'origine dati è un oggetto <xref:System.ComponentModel.IBindingListView> . La <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà richiede la sintassi ADO.NET standard: una stringa che rappresenta il nome di una colonna di dati nell'origine dati seguita da `ASC` o `DESC` per indicare se l'elenco deve essere ordinato in ordine crescente o decrescente. È possibile impostare l'ordinamento avanzato o l'ordinamento a più colonne separando ogni colonna con un separatore virgola. La <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà accetta un'espressione stringa.  
  
> [!NOTE]
> L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Per filtrare i dati con BindingSource  
  
- Impostare la <xref:System.Windows.Forms.BindingSource.Filter%2A> proprietà su espressione desiderata.  
  
     Nell'esempio di codice seguente, l'espressione è un nome di colonna seguito da un valore che si desidera per la colonna.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Per ordinare i dati con BindingSource  
  
1. Impostare la <xref:System.Windows.Forms.BindingSource.Sort%2A> proprietà sul nome della colonna che si desidera seguito da `ASC` o `DESC` per indicare l'ordine crescente o decrescente.  
  
2. Separare più colonne con una virgola.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Esempio  

 L'esempio di codice seguente consente di caricare i dati dalla tabella Customers del database di esempio Northwind in un <xref:System.Windows.Forms.DataGridView> controllo e di filtrare e ordinare i dati visualizzati.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

 Per eseguire questo esempio, incollare il codice in un form che contiene un oggetto <xref:System.Windows.Forms.BindingSource> denominato `BindingSource1` e un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` . Gestire l' <xref:System.Windows.Forms.Form.Load> evento per il form e chiamare `InitializeSortedFilteredBindingSource` nel metodo del gestore dell'evento Load.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Procedura: Installare database di esempio](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Componente BindingSource](bindingsource-component.md)
