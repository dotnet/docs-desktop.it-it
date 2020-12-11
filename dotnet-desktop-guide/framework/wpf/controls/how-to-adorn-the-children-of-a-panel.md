---
title: 'Procedura: decorare gli elementi figlio di un riquadro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4c5ac537bfd68e9c43583758047b2ec378d0bb57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966190"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>Procedura: decorare gli elementi figlio di un riquadro
In questo esempio viene illustrato come associare uno strumento decorativo a livello di codice agli elementi figlio di un oggetto specificato <xref:System.Windows.Controls.Panel> .  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo agli elementi figlio di un <xref:System.Windows.Controls.Panel> , attenersi alla procedura seguente:  
  
1. Dichiarare un nuovo <xref:System.Windows.Documents.AdornerLayer> oggetto e chiamare il `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo per trovare un livello dello strumento decorativo per l'elemento i cui elementi figlio devono essere decorati.  
  
2. Enumerare gli elementi figlio dell'elemento padre e chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare uno strumento decorativo a ogni elemento figlio.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) agli elementi figlio di un oggetto <xref:System.Windows.Controls.StackPanel> denominato *StackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)
