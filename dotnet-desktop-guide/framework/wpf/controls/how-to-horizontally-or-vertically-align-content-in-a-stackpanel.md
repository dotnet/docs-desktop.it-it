---
title: 'Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel'
description: Informazioni su come modificare l'orientamento del contenuto in un Windows Presentation Foundation StackPanel e in HorizontalAlignment e VerticalAlignment del contenuto figlio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: b847ee4808c14622f24d758b9eb9ada28712ab3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965710"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel
In questo esempio viene illustrato come modificare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> contenuto di un <xref:System.Windows.Controls.StackPanel> elemento e come modificare l'oggetto e il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> contenuto figlio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati tre <xref:System.Windows.Controls.ListBox> elementi in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] . Ogni <xref:System.Windows.Controls.ListBox> rappresenta i valori possibili delle <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> di un oggetto <xref:System.Windows.Controls.StackPanel> . Quando un utente seleziona un valore in uno degli <xref:System.Windows.Controls.ListBox> elementi, la proprietà associata di e i <xref:System.Windows.Controls.StackPanel> relativi elementi figlio <xref:System.Windows.Controls.Button> cambiano.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Il file code-behind seguente definisce le modifiche apportate agli eventi associati alle <xref:System.Windows.Controls.ListBox> modifiche della selezione. <xref:System.Windows.Controls.StackPanel> è identificato da <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
