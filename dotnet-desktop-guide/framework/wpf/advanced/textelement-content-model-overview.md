---
title: Cenni preliminari sul modello di contenuto TextElement
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: b4bf5bf1810adec4eb71ae79e747d507952c0734
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967555"
---
# <a name="textelement-content-model-overview"></a>Cenni preliminari sul modello di contenuto TextElement
Questa panoramica sul modello di contenuto descrive il contenuto supportato per un <xref:System.Windows.Documents.TextElement> . La <xref:System.Windows.Documents.Paragraph> classe è di tipo <xref:System.Windows.Documents.TextElement> . Un modello di contenuto descrive gli oggetti o gli elementi che possono essere contenuti in altri oggetti o elementi. Questa panoramica riepiloga il modello di contenuto usato per gli oggetti derivati da <xref:System.Windows.Documents.TextElement> . Per altre informazioni, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>Diagramma del modello di contenuto  
 Il diagramma seguente riepiloga il modello di contenuto per le classi derivate da e il <xref:System.Windows.Documents.TextElement> modo in cui le altre `TextElement` classi non rientrano in questo modello.  
  
 ![Diagramma: schema di contenimento del contenuto del flusso](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può osservare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base al fatto che una classe sia derivata dalla <xref:System.Windows.Documents.Block> classe o da una <xref:System.Windows.Documents.Inline> classe. Ad esempio, una <xref:System.Windows.Documents.Span> classe ( <xref:System.Windows.Documents.Inline> derivata da) può avere solo <xref:System.Windows.Documents.Inline> elementi figlio, ma un <xref:System.Windows.Documents.Figure> (anche una <xref:System.Windows.Documents.Inline> classe derivata da) può avere solo <xref:System.Windows.Documents.Block> elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. È ad esempio possibile usare il diagramma per determinare come costruire il contenuto del flusso di un oggetto <xref:System.Windows.Controls.RichTextBox> .  
  
1. Un <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve contenere un <xref:System.Windows.Documents.Block> oggetto derivato da. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
     ![Diagramma: regole di contenimento di RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. In base al diagramma, è possibile <xref:System.Windows.Documents.Block> scegliere tra diversi elementi, tra cui <xref:System.Windows.Documents.Paragraph> ,, <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table> , <xref:System.Windows.Documents.List> e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da blocchi nel diagramma precedente). Supponiamo di volere un <xref:System.Windows.Documents.Table> . In base al diagramma precedente, un <xref:System.Windows.Documents.Table> oggetto contiene elementi che contengono <xref:System.Windows.Documents.TableRowGroup> <xref:System.Windows.Documents.TableRow> elementi contenenti <xref:System.Windows.Documents.TableCell> un <xref:System.Windows.Documents.Block> oggetto derivato da. Di seguito è riportato il segmento corrispondente per <xref:System.Windows.Documents.Table> tratto dal diagramma precedente.  
  
     ![Diagramma: schema padre&#47;figlio per la tabella](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ecco il markup corrispondente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Anche in questo caso, uno o più <xref:System.Windows.Documents.Block> elementi sono necessari sotto un <xref:System.Windows.Documents.TableCell> . Per rendere più chiaro l'esempio, viene inserito del testo nella cella. Questa operazione può essere eseguita usando un oggetto <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. Di seguito sono riportati i segmenti corrispondenti del diagramma che indicano che un oggetto <xref:System.Windows.Documents.Paragraph> può assumere un <xref:System.Windows.Documents.Inline> elemento e che un <xref:System.Windows.Documents.Run> elemento (un <xref:System.Windows.Documents.Inline> elemento) può solo assumere testo normale.  
  
     ![Diagramma: schema padre&#47;figlio per il paragrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramma: padre&#47;schema figlio per l'esecuzione](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>Uso del contenuto TextElement a livello di codice  
 Il contenuto di un oggetto <xref:System.Windows.Documents.TextElement> è costituito da raccolte e pertanto la modifica del contenuto degli oggetti a livello di codice <xref:System.Windows.Documents.TextElement> viene eseguita con queste raccolte. Sono disponibili tre diverse raccolte utilizzate dalle <xref:System.Windows.Documents.TextElement> classi derivate da:  
  
- <xref:System.Windows.Documents.InlineCollection>: Rappresenta una raccolta di <xref:System.Windows.Documents.Inline> elementi. <xref:System.Windows.Documents.InlineCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> e <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Rappresenta una raccolta di <xref:System.Windows.Documents.Block> elementi. <xref:System.Windows.Documents.BlockCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> e <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Elemento di contenuto del flusso che rappresenta un particolare elemento di contenuto in un oggetto ordinato o non ordinato <xref:System.Windows.Documents.List> .  
  
 È possibile modificare (aggiungere o rimuovere elementi) da queste raccolte usando le rispettive proprietà di **Inlines**, **Blocks** e **ListItems**. Negli esempi seguenti viene illustrato come modificare il contenuto di un intervallo utilizzando la proprietà **Inlines** .  
  
> [!NOTE]
> Per modificare il contenuto di una tabella vengono usate diverse raccolte, che tuttavia non vengono illustrate in questa sezione. Per ulteriori informazioni, vedere [Cenni preliminari sulle tabelle](table-overview.md).  
  
 Nell'esempio seguente viene creato un nuovo <xref:System.Windows.Documents.Span> oggetto, quindi viene utilizzato il `Add` metodo per aggiungere due esecuzioni di testo come elementi figlio del contenuto di <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Nell'esempio seguente viene creato un nuovo elemento che viene <xref:System.Windows.Documents.Run> inserito all'inizio dell'oggetto <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Inline> elemento in <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Nell'esempio seguente vengono cancellati tutti i contenuti ( <xref:System.Windows.Documents.Inline> elementi) da <xref:System.Windows.Documents.Span> .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>Tipi che condividono questo modello di contenuto  
 I tipi seguenti ereditano dalla <xref:System.Windows.Documents.TextElement> classe e possono essere usati per visualizzare il contenuto descritto in questa panoramica.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Si noti che questo elenco include solo i tipi non astratti distribuiti con la Windows SDK. È possibile utilizzare altri tipi che ereditano da <xref:System.Windows.Documents.TextElement> .  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>Tipi in grado di contenere oggetti TextElement  
 Vedere [modello di contenuto WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare elementi di contenuto di flusso tramite la proprietà Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
