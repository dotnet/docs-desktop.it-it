---
title: 'Procedura: applicare uno stile a una riga in un ListView che usa GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 586c549cca6ef3089b37427c7983bb39e56509bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951882"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Procedura: applicare uno stile a una riga in un ListView che implementa una GridView
Questo esempio illustra come applicare uno stile a una riga in un <xref:System.Windows.Controls.ListView> controllo che usa una <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modalità.  
  
## <a name="example"></a>Esempio  
 È possibile applicare uno stile a una riga in un controllo impostando <xref:System.Windows.Controls.ListView> un oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> sul <xref:System.Windows.Controls.ListView> controllo. Impostare lo stile per gli elementi rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Fa riferimento agli <xref:System.Windows.Controls.ControlTemplate> oggetti utilizzati per visualizzare il contenuto della riga.  
  
 Nell'esempio completo, da cui vengono estratti gli esempi seguenti, viene visualizzata una raccolta di informazioni sui brani archiviate in un database XML. Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.  
  
 Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per gli <xref:System.Windows.Controls.ListViewItem> oggetti che rappresentano i brani della raccolta Song. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Fa riferimento a <xref:System.Windows.Controls.ControlTemplate> oggetti che specificano come visualizzare una riga di informazioni sul brano.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa `"Strongly Recommended"` di testo alla riga. Questo modello viene usato come riferimento in <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la classificazione del brano ha un valore pari a 5 (cinque). <xref:System.Windows.Controls.ControlTemplate>Include un <xref:System.Windows.Controls.GridViewRowPresenter> oggetto che imposta il contenuto della riga in colonne in base a quanto definito dalla <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Nell'esempio seguente viene definito <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
