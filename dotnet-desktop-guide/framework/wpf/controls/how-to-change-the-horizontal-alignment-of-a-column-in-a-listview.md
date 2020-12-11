---
title: "Procedura: modificare l'allineamento orizzontale di una colonna in ListView"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: cdf479fc9f84f88fccc877e9fdf8ca56d53c1c4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967531"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Procedura: modificare l'allineamento orizzontale di una colonna in ListView
Per impostazione predefinita, il contenuto di ogni colonna in un oggetto <xref:System.Windows.Controls.ListViewItem> è allineato a sinistra. È possibile modificare l'allineamento di ogni colonna fornendo un oggetto <xref:System.Windows.DataTemplate> e impostando la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà sull'elemento all'interno di <xref:System.Windows.DataTemplate> . In questo argomento viene illustrato come <xref:System.Windows.Controls.ListView> Allinea il contenuto per impostazione predefinita e come modificare l'allineamento di una colonna in un oggetto <xref:System.Windows.Controls.ListView> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente i dati nelle `Title` `ISBN` colonne e sono allineati a sinistra.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Per modificare l'allineamento della `ISBN` colonna, è necessario specificare che la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà di ogni oggetto <xref:System.Windows.Controls.ListViewItem> sia <xref:System.Windows.HorizontalAlignment.Stretch> , in modo che gli elementi in ogni <xref:System.Windows.Controls.ListViewItem> possano estendersi o essere posizionati lungo l'intera larghezza di ogni colonna. Poiché <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare uno stile che imposta <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> . Successivamente, è necessario usare un oggetto <xref:System.Windows.DataTemplate> per visualizzare il contenuto invece di usare la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Proprietà. Per visualizzare l'oggetto `ISBN` di ogni modello, <xref:System.Windows.DataTemplate> può contenere solo un oggetto la <xref:System.Windows.Controls.TextBlock> cui <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà è impostata su <xref:System.Windows.HorizontalAlignment.Right> .  
  
 Nell'esempio seguente viene definito lo stile ed è <xref:System.Windows.DataTemplate> necessario per rendere la `ISBN` colonna allineata a destra e viene modificato <xref:System.Windows.Controls.GridViewColumn> per fare riferimento a <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
- [Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)
