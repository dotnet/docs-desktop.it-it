---
title: 'Procedura: specificare se un collegamento ipertestuale è sottolineato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 5718912e24a0697f209669b0ab4e7f4df1765ed3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952193"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a>Procedura: specificare se un collegamento ipertestuale è sottolineato
L' <xref:System.Windows.Documents.Hyperlink> oggetto è un elemento di contenuto del flusso di livello inline che consente di ospitare collegamenti ipertestuali all'interno del contenuto del flusso. Per impostazione predefinita, <xref:System.Windows.Documents.Hyperlink> Usa un <xref:System.Windows.TextDecoration> oggetto per visualizzare una sottolineatura. <xref:System.Windows.TextDecoration> gli oggetti possono essere a elevato utilizzo di prestazioni per creare un'istanza, in particolare se sono presenti molti <xref:System.Windows.Documents.Hyperlink> oggetti. Se si fa uso estensivo di <xref:System.Windows.Documents.Hyperlink> elementi, può essere utile visualizzare una sottolineatura solo quando si attiva un evento, ad esempio l' <xref:System.Windows.ContentElement.MouseEnter> evento.  
  
 Nell'esempio seguente, la sottolineatura per il collegamento "My MSN" è dinamica, ovvero viene visualizzata solo quando <xref:System.Windows.ContentElement.MouseEnter> viene attivato l'evento.  
  
  ![Collegamenti ipertestuali con TextDecoration](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a>Esempio  
 L'esempio di markup seguente mostra un oggetto <xref:System.Windows.Documents.Hyperlink> definito con e senza sottolineatura:  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Nell'esempio di codice seguente viene illustrato come creare una sottolineatura per l' <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.ContentElement.MouseEnter> evento e come rimuoverla nell' <xref:System.Windows.ContentElement.MouseLeave> evento.  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Creare un effetto testo](how-to-create-a-text-decoration.md)
