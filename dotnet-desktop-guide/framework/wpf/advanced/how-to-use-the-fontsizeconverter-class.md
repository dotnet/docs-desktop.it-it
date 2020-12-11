---
title: 'Procedura: Usare la classe FontSizeConverter'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: b4662ef60866150008d84f22de44852b65373282
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968695"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Procedura: Usare la classe FontSizeConverter
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.FontSizeConverter> e utilizzarla per modificare le dimensioni del carattere.  
  
 Nell'esempio viene definito un metodo personalizzato denominato `changeSize` che converte il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> , come definito in un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file separato, in un'istanza di <xref:System.Double> e successivamente in un oggetto <xref:System.String> . Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Double> . Questo valore viene quindi passato nuovamente come valore della <xref:System.Windows.Controls.TextBlock.FontSize%2A> proprietà dell' <xref:System.Windows.Controls.TextBlock> elemento.  
  
 Questo esempio definisce anche un secondo metodo personalizzato chiamato `changeFamily` . Questo metodo converte la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà dell'oggetto <xref:System.Windows.Controls.ListBoxItem> in un oggetto <xref:System.String> , quindi passa tale valore alla <xref:System.Windows.Controls.TextBlock.FontFamily%2A> proprietà dell' <xref:System.Windows.Controls.TextBlock> elemento.  
  
 Questo esempio non viene eseguito.  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FontSizeConverter>
