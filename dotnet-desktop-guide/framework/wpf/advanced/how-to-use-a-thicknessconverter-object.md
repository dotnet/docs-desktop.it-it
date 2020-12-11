---
title: 'Procedura: utilizzare un oggetto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 7420824ad939012d12f61ecbb72f2d00ce483e8b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963727"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Procedura: utilizzare un oggetto ThicknessConverter

## <a name="example"></a>Esempio  

 In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.ThicknessConverter> e utilizzarla per modificare lo spessore di un bordo.  
  
 Nell'esempio viene definito un metodo personalizzato denominato. `changeThickness` questo metodo converte prima di tutto il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> , come definito in un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file separato, in un'istanza di <xref:System.Windows.Thickness> e successivamente converte il contenuto in un oggetto <xref:System.String> . Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Windows.Thickness> . Questo valore viene quindi passato nuovamente come valore della <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà dell'oggetto <xref:System.Windows.Controls.Border> .  
  
 Questo esempio non viene eseguito.  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [Procedura: modificare la proprietà Margin](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [Procedura: convertire un oggetto ListBoxItem in un nuovo tipo di dati](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
