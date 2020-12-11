---
title: 'Procedura: Trovare elementi generati da un oggetto ControlTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 064f70835443accef83ca5f3d912ace861c2216a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952536"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>Procedura: Trovare elementi generati da un oggetto ControlTemplate
Questo esempio illustra come trovare elementi generati da un oggetto <xref:System.Windows.Controls.ControlTemplate> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato uno stile che consente di creare un oggetto semplice <xref:System.Windows.Controls.ControlTemplate> per la <xref:System.Windows.Controls.Button> classe:  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 Per trovare un elemento all'interno del modello dopo l'applicazione del modello, è possibile chiamare il <xref:System.Windows.FrameworkTemplate.FindName%2A> metodo di <xref:System.Windows.Controls.Control.Template%2A> . Nell'esempio seguente viene creata una finestra di messaggio che mostra il valore di larghezza effettivo dell'oggetto <xref:System.Windows.Controls.Grid> all'interno del modello di controllo:  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>Vedere anche

- [Trova elementi DataTemplate-Generated](../data/how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
