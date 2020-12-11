---
title: 'Procedura: creare e utilizzare un oggetto GridLengthConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 7cf6e12c1f3f9530d4616f0cfdecff1f07820615
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968119"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Procedura: creare e utilizzare un oggetto GridLengthConverter
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare e utilizzare un'istanza di <xref:System.Windows.GridLengthConverter> . Nell'esempio viene definito un metodo personalizzato denominato `changeCol` , che passa <xref:System.Windows.Controls.ListBoxItem> a un oggetto <xref:System.Windows.GridLengthConverter> che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Windows.GridLength> . Il valore convertito viene quindi passato nuovamente come valore della <xref:System.Windows.Controls.ColumnDefinition.Width%2A> proprietà dell' <xref:System.Windows.Controls.ColumnDefinition> elemento.  
  
 Nell'esempio viene inoltre definito un secondo metodo personalizzato, denominato `changeColVal` . Questo metodo personalizzato converte l'oggetto <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> di un oggetto <xref:System.Windows.Controls.Slider> in un oggetto <xref:System.String> e quindi lo passa nuovamente a <xref:System.Windows.Controls.ColumnDefinition> come <xref:System.Windows.Controls.ColumnDefinition.Width%2A> dell'elemento.  
  
 Si noti che un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file separato definisce il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> .  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
