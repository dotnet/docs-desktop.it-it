---
title: 'Procedura: Aggiungere funzionalità di ricerca a un controllo ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963637"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Procedura: Aggiungere funzionalità di ricerca a un controllo ListView
Spesso quando si utilizza un elenco di elementi di un controllo di grandi dimensioni <xref:System.Windows.Forms.ListView> , si desidera offrire funzionalità di ricerca all'utente. Il <xref:System.Windows.Forms.ListView> controllo offre questa funzionalità in due modi diversi: corrispondenza del testo e ricerca nella posizione.  
  
 Il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo consente di eseguire una ricerca di testo in un <xref:System.Windows.Forms.ListView> elenco o in una visualizzazione dettagli, data una stringa di ricerca e un indice facoltativo iniziale e finale. Al contrario, il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo consente di trovare un elemento in una <xref:System.Windows.Forms.ListView> visualizzazione icona o affiancata, in base a un set di coordinate x e y e a una direzione per la ricerca.  
  
### <a name="to-find-an-item-using-text"></a>Per trovare un elemento usando il testo  
  
1. Creare un oggetto <xref:System.Windows.Forms.ListView> con la <xref:System.Windows.Forms.ListView.View%2A> proprietà impostata su <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List> , quindi popolare con gli <xref:System.Windows.Forms.ListView> elementi.  
  
2. Chiamare il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo, passando il testo dell'elemento che si desidera trovare.  
  
3. Nell'esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Forms.ListView> oggetto di base, compilarlo con gli elementi e utilizzare l'input di testo dall'utente per trovare un elemento nell'elenco.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Per trovare un elemento usando le coordinate x e y  
  
1. Creare un oggetto <xref:System.Windows.Forms.ListView> con la <xref:System.Windows.Forms.View> proprietà impostata su <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon> , quindi popolare con gli <xref:System.Windows.Forms.ListView> elementi.  
  
2. Chiamare il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo, passando le coordinate x e y desiderate e la direzione in cui si desidera eseguire la ricerca.  
  
3. Nell'esempio di codice seguente viene illustrato come creare un'icona di base <xref:System.Windows.Forms.ListView> , compilarla con gli elementi e acquisire l' <xref:System.Windows.Forms.Control.MouseDown> evento per trovare l'elemento più vicino nella direzione verso l'alto.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
