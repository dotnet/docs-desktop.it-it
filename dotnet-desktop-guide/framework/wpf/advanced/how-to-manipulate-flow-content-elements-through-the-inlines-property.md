---
title: 'Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 92f23fbf44464eb7658f3382f873f3db63f7cb26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966277"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a>Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines
Questi esempi illustrano alcune delle operazioni più comuni che possono essere eseguite sugli elementi di contenuto del flusso in linea (e contenitori di tali elementi, ad esempio <xref:System.Windows.Controls.TextBlock> ) tramite la proprietà **Inlines** . Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.InlineCollection> . Gli elementi di contenuto del flusso che includono una proprietà **Inlines** includono:  
  
- <xref:System.Windows.Documents.Bold>  
  
- <xref:System.Windows.Documents.Hyperlink>  
  
- <xref:System.Windows.Documents.Italic>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Span>  
  
- <xref:System.Windows.Documents.Underline>  
  
 Questi esempi si verificano <xref:System.Windows.Documents.Span> come elementi di contenuto del flusso, ma queste tecniche sono applicabili a tutti gli elementi o controlli che ospitano una <xref:System.Windows.Documents.InlineCollection> raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un nuovo <xref:System.Windows.Documents.Span> oggetto, quindi viene utilizzato il metodo **Add** per aggiungere due esecuzioni di testo come elementi figlio del contenuto di <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un nuovo elemento che viene <xref:System.Windows.Documents.Run> inserito all'inizio dell'oggetto <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene ottenuto il numero di elementi di primo livello <xref:System.Windows.Documents.Inline> contenuti in <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Inline> elemento in <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono cancellati tutti i contenuti ( <xref:System.Windows.Documents.Inline> elementi) da <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
