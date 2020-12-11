---
title: Visualizza icone per il controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961861"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Procedura: Visualizzare icone per il controllo ListView di Windows Forms
Il <xref:System.Windows.Forms.ListView> controllo Windows Forms può visualizzare icone da tre elenchi di immagini. Le visualizzazioni List, Details e SmallIcon visualizzano immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.SmallImageList%2A> Proprietà. La vista LargeIcon visualizza le immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.LargeImageList%2A> Proprietà. Una visualizzazione elenco può anche visualizzare un set di icone aggiuntivo, impostato nella <xref:System.Windows.Forms.ListView.StateImageList%2A> proprietà, accanto alle icone grandi o piccole. Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Per visualizzare le immagini in una visualizzazione elenco  
  
1. Impostare la proprietà appropriata ( <xref:System.Windows.Forms.ListView.SmallImageList%2A> , <xref:System.Windows.Forms.ListView.LargeImageList%2A> o <xref:System.Windows.Forms.ListView.StateImageList%2A> ) sul <xref:System.Windows.Forms.ImageList> componente esistente che si desidera utilizzare.  
  
     È possibile impostare queste proprietà nella finestra di progettazione con il Finestra Proprietà o nel codice.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Impostare la <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> proprietà o per ogni elemento elenco a cui è associata un'icona.  
  
     Queste proprietà possono essere impostate nel codice o nell'editor della **raccolta ListViewItem**. Per aprire l' **Editor della raccolta ListViewItem**, fare clic sul pulsante con i puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) accanto alla <xref:System.Windows.Forms.ListView.Items%2A> proprietà nella finestra **Proprietà** .  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere colonne al controllo ListView di Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
