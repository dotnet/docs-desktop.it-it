---
title: 'Procedura: creare un controllo Expander con un controllo ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968125"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Procedura: creare un controllo Expander con un controllo ScrollViewer
Questo esempio illustra come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso, ad esempio un'immagine e un testo. Nell'esempio viene inoltre racchiudeto il contenuto di <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.Expander> . Nell'esempio viene usato un <xref:System.Windows.Controls.Primitives.BulletDecorator> controllo, che contiene un'immagine e un testo, per definire <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> . Un <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un metodo per lo scorrimento del contenuto espanso.  
  
 Si noti che nell'esempio la <xref:System.Windows.FrameworkElement.Height%2A> proprietà viene impostata su <xref:System.Windows.Controls.ScrollViewer> anziché sul contenuto. Se <xref:System.Windows.FrameworkElement.Height%2A> è impostato sul contenuto, <xref:System.Windows.Controls.ScrollViewer> non consente all'utente di scorrere il contenuto. La <xref:System.Windows.FrameworkElement.Width%2A> proprietà è impostata sul <xref:System.Windows.Controls.Expander> controllo e questa impostazione si applica a <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e al contenuto espanso.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Expander>
- [Cenni preliminari sul controllo Expander](expander-overview.md)
- [Procedure](expander-how-to-topics.md)
