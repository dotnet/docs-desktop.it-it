---
title: 'Procedura: trovare elementi generati da un oggetto DataTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: a0cb3c6f4431e16425d8aae305a917d87a3d7f96
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969730"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto DataTemplate
Questo esempio illustra come trovare elementi generati da un oggetto <xref:System.Windows.DataTemplate> .  
  
## <a name="example"></a>Esempio  
 In questo esempio esiste un <xref:System.Windows.Controls.ListBox> associato ad alcuni dati XML:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox>Usa gli elementi seguenti <xref:System.Windows.DataTemplate> :  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Se si desidera recuperare l' <xref:System.Windows.Controls.TextBlock> elemento generato dall'oggetto <xref:System.Windows.DataTemplate> di un determinato <xref:System.Windows.Controls.ListBoxItem> , è necessario ottenere l'oggetto <xref:System.Windows.Controls.ListBoxItem> , trovare l'oggetto <xref:System.Windows.Controls.ContentPresenter> all'interno di tale oggetto, <xref:System.Windows.Controls.ListBoxItem> quindi chiamare <xref:System.Windows.FrameworkTemplate.FindName%2A> sull'oggetto <xref:System.Windows.DataTemplate> impostato su <xref:System.Windows.Controls.ContentPresenter> . Nell'esempio seguente viene illustrato come eseguire questi passaggi. A scopo dimostrativo, in questo esempio viene creata una finestra di messaggio che mostra il contenuto di testo del <xref:System.Windows.DataTemplate> blocco di testo generato da.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Di seguito è riportata l'implementazione di `FindVisualChild` , che usa i <xref:System.Windows.Media.VisualTreeHelper> metodi:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Trovare elementi generati da un oggetto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
