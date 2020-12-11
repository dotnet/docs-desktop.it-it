---
title: "Procedura: eseguire l'associazione a un'origine dati ADO.NET"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: d7ffaae472d89ebc23804c4032a75253756dc871
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951622"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Procedura: eseguire l'associazione a un'origine dati ADO.NET

Questo esempio illustra come associare un [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> controllo a un ADO.NET `DataSet` .

## <a name="example"></a>Esempio

In questo esempio viene usato un oggetto `OleDbConnection` per la connessione all'origine dati che è un file `Access MDB` specificato nella stringa di connessione. Dopo aver stabilito la connessione viene creato l'oggetto `OleDbDataAdapter` . L' `OleDbDataAdapter` oggetto esegue un'istruzione select Structured Query Language (SQL) per recuperare il recordset dal database. I risultati del comando SQL vengono archiviati in un oggetto `DataTable` di `DataSet` chiamando il `Fill` metodo dell'oggetto `OleDbDataAdapter` . `DataTable` in questo esempio è denominato `BookTable`. Nell'esempio viene quindi impostata la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà di sull' <xref:System.Windows.Controls.ListBox> `DataSet` oggetto.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

È quindi possibile associare la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di <xref:System.Windows.Controls.ListBox> a `BookTable` del `DataSet` :

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` è l'oggetto <xref:System.Windows.DataTemplate> che definisce come vengono visualizzati i dati:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` converte un oggetto `int` in un colore. Con l'uso di questo convertitore, il <xref:System.Windows.Controls.TextBlock.Background%2A> colore del terzo <xref:System.Windows.Controls.TextBlock> viene visualizzato in verde se il valore di `NumPages` è minore di 350 e rosso in caso contrario. L'implementazione del convertitore non viene visualizzata qui.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.BindingListCollectionView>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
