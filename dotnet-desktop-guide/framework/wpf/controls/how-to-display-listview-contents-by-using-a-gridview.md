---
title: 'Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968593"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView
Questo esempio illustra come definire una <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È possibile definire la modalità di visualizzazione di un oggetto <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> gli oggetti. Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti che si associano al contenuto di dati specificato per il <xref:System.Windows.Controls.ListView> controllo. <xref:System.Windows.Controls.GridView>In questo esempio vengono specificati tre <xref:System.Windows.Controls.GridViewColumn> oggetti che vengono mappati ai `FirstName` `LastName` campi, e `EmployeeNumber` dell'oggetto `EmployeeInfoDataSource` impostato come del <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListView> controllo.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Nell'illustrazione seguente viene illustrato come viene visualizzato questo esempio.  
  
 ![Screenshot che mostra un ListView con l'output di GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
- [Procedure](listview-how-to-topics.md)
