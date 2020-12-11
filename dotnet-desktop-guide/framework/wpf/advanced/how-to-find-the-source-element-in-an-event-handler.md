---
title: "Procedura: cercare l'elemento di origine in un gestore eventi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967864"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Procedura: cercare l'elemento di origine in un gestore eventi
Questo esempio illustra come trovare l'elemento di origine in un gestore eventi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi dichiarato in un file code-behind. Quando un utente fa clic sul pulsante a cui è collegato il gestore, il gestore modifica il valore di una proprietà. Il codice del gestore utilizza la <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà dei dati dell'evento indirizzato riportati negli argomenti dell'evento per modificare il <xref:System.Windows.FrameworkElement.Width%2A> valore della proprietà nell' <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.RoutedEventArgs>
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Procedure](events-how-to-topics.md)
