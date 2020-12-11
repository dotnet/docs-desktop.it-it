---
title: 'Procedura: utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968701"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Procedura: utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument
Questo esempio illustra come usare le funzionalità di separazione delle colonne di un oggetto <xref:System.Windows.Documents.FlowDocument> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un oggetto <xref:System.Windows.Documents.FlowDocument> e vengono impostati gli <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> attributi, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> .  <xref:System.Windows.Documents.FlowDocument>Contiene un solo paragrafo del contenuto di esempio.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Nella figura seguente vengono illustrati gli effetti <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A> degli <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> attributi, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> in un oggetto di cui è stato eseguito il rendering <xref:System.Windows.Documents.FlowDocument> .  
  
 ![Screenshot che mostra l'attributo della colonna FlowDocument intra.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
