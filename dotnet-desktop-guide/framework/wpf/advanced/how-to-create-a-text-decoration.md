---
title: 'Procedura: creare un effetto di testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967789"
---
# <a name="how-to-create-a-text-decoration"></a>Procedura: creare un effetto di testo
Un <xref:System.Windows.TextDecoration> oggetto è un ornamento visivo che è possibile aggiungere al testo. Sono disponibili quattro tipi di decorazioni di testo: sottolineatura, linea di base, barratura e Overline. Nell'esempio seguente vengono illustrate le posizioni delle decorazioni di testo relative al testo.  
  
 ![Diagramma dei tipi di decorazione di testo](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 Per aggiungere un effetto di testo al testo, creare un <xref:System.Windows.TextDecoration> oggetto e modificarne le proprietà. Utilizzare la <xref:System.Windows.TextDecoration.Location%2A> proprietà per specificare la posizione in cui viene visualizzato l'effetto di testo, ad esempio sottolineato. Utilizzare la <xref:System.Windows.TextDecoration.Pen%2A> proprietà per specificare l'aspetto della decorazione di testo, ad esempio un riempimento a tinta unita o un colore sfumato. Se non si specifica un valore per la <xref:System.Windows.TextDecoration.Pen%2A> proprietà, per impostazione predefinita viene impostato lo stesso colore del testo. Una volta definito un <xref:System.Windows.TextDecoration> oggetto, aggiungerlo alla <xref:System.Windows.TextDecorations> raccolta dell'oggetto testo desiderato.  
  
 Nell'esempio seguente viene illustrata una decorazione di testo a cui è stato applicato uno stile con un pennello sfumato lineare e una penna tratteggiata.  
  
 ![Decorazione di testo con sottolineatura sfumata lineare](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 L' <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso. Per impostazione predefinita, <xref:System.Windows.Documents.Hyperlink> Usa un <xref:System.Windows.TextDecoration> oggetto per visualizzare una sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere a elevato utilizzo di prestazioni per creare un'istanza, in particolare se sono presenti molti <xref:System.Windows.Documents.Hyperlink> oggetti. Se si fa uso estensivo di <xref:System.Windows.Documents.Hyperlink> elementi, può essere utile visualizzare una sottolineatura solo quando si attiva un evento, ad esempio l' <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, ma viene visualizzata solo quando <xref:System.Windows.ContentElement.MouseEnter> viene attivato l'evento.  
  
 ![Collegamenti ipertestuali con TextDecoration](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 Per altre informazioni, vedere [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, un effetto del testo di sottolineatura usa il valore del tipo di carattere predefinito.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 Nell'esempio di codice seguente viene creata una decorazione di testo sottolineato con un pennello tinta unita per la penna.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 Nell'esempio di codice seguente viene creata una decorazione di testo sottolineata con un pennello sfumato lineare per la penna tratteggiata.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Specificare se un collegamento ipertestuale è sottolineato](how-to-specify-whether-a-hyperlink-is-underlined.md)
