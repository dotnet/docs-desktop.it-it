---
title: 'Procedura: ottenere un oggetto ListBoxItem'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: 27a435feb4a941c77af221ab25bd63ea98b16e92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961378"
---
# <a name="how-to-get-a-listboxitem"></a>Procedura: ottenere un oggetto ListBoxItem
Se è necessario ottenere un oggetto specifico in <xref:System.Windows.Controls.ListBoxItem> un indice specifico in un oggetto <xref:System.Windows.Controls.ListBox> , è possibile usare un oggetto <xref:System.Windows.Controls.ItemContainerGenerator> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono illustrati un oggetto <xref:System.Windows.Controls.ListBox> e i relativi elementi.  
  
 [!code-xaml[ListBoxItems#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 Nell'esempio seguente viene illustrato come recuperare l'elemento specificando l'indice dell'elemento nella <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> proprietà di <xref:System.Windows.Controls.ItemContainerGenerator> .  
  
 [!code-csharp[ListBoxItems#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Dopo aver recuperato l'elemento della casella di riepilogo, è possibile visualizzare il contenuto dell'elemento, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ListBoxItems#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
