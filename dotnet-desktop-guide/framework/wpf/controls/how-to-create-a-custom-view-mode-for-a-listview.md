---
title: 'Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 6c6c8475849354493330105e93316d6424ebe2f3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604277"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Procedura: creare una modalità di visualizzazione personalizzata per un controllo ListView

Questo esempio illustra come creare una modalità personalizzata <xref:System.Windows.Controls.ListView.View%2A> per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È necessario utilizzare la <xref:System.Windows.Controls.ViewBase> classe quando si crea una visualizzazione personalizzata per il <xref:System.Windows.Controls.ListView> controllo. Nell'esempio seguente viene illustrata una modalità `PlainView` di visualizzazione denominata derivata dalla <xref:System.Windows.Controls.ViewBase> classe.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Per applicare uno stile alla visualizzazione personalizzata, usare la <xref:System.Windows.Style> classe. Nell'esempio seguente viene definito un oggetto <xref:System.Windows.Style> per la `PlainView` modalità di visualizzazione. Nell'esempio precedente, questo stile è impostato come valore della <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> proprietà definita per `PlainView` .  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Per definire il layout dei dati in una modalità di visualizzazione personalizzata, definire un <xref:System.Windows.DataTemplate> oggetto. Nell'esempio seguente viene definito un oggetto <xref:System.Windows.DataTemplate> che può essere utilizzato per visualizzare i dati in `PlainView` modalità di visualizzazione.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.ResourceKey> per la `PlainView` modalità di visualizzazione che utilizza l'oggetto <xref:System.Windows.DataTemplate> definito nell'esempio precedente.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Un <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione personalizzata se si imposta la <xref:System.Windows.Controls.ListView.View%2A> proprietà sulla chiave di risorsa. Nell'esempio seguente viene illustrato come specificare `PlainView` come modalità di visualizzazione per un oggetto <xref:System.Windows.Controls.ListView> .  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Per l'esempio completo, vedere [ListView con più visualizzazioni (C#)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con più visualizzazioni (Visual Basic)](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
