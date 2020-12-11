---
title: Visualizza gli elementi secondari nelle colonne con il controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964420"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Forms
Il <xref:System.Windows.Forms.ListView> controllo Windows Forms può visualizzare testo aggiuntivo, o elementi secondari, per ogni elemento nella visualizzazione dettagli. Nella prima colonna viene visualizzato il testo dell'elemento, ad esempio un numero di dipendente. La seconda, la terza e la colonna successiva visualizzano il primo, il secondo e i successivi elementi secondari associati.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Per aggiungere elementi secondari a una voce di elenco  
  
1. Aggiungere le colonne necessarie. Poiché nella prima colonna viene visualizzata la proprietà dell'elemento <xref:System.Windows.Forms.ListView.Text%2A> , è necessaria una colonna maggiore di quella degli elementi secondari. Per altre informazioni sull'aggiunta di colonne, vedere [procedura: aggiungere colonne al controllo Windows Forms ListView](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2. Chiamare il <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> metodo della raccolta restituita dalla <xref:System.Windows.Forms.ListViewItem.SubItems%2A> proprietà di un elemento. L'esempio di codice seguente imposta il nome e il reparto del dipendente per un elemento elenco.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere colonne al controllo ListView di Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare icone per il controllo ListView di Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
