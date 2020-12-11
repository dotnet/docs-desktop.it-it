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
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="d46cf-102">Procedura: Usare la classe FontSizeConverter</span><span class="sxs-lookup"><span data-stu-id="d46cf-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="d46cf-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="d46cf-103">Example</span></span>  
 <span data-ttu-id="d46cf-104">In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.FontSizeConverter> e utilizzarla per modificare le dimensioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="d46cf-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="d46cf-105">Nell'esempio viene definito un metodo personalizzato denominato `changeSize` che converte il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> , come definito in un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file separato, in un'istanza di <xref:System.Double> e successivamente in un oggetto <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="d46cf-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="d46cf-106">Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Double> .</span><span class="sxs-lookup"><span data-stu-id="d46cf-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="d46cf-107">Questo valore viene quindi passato nuovamente come valore della <xref:System.Windows.Controls.TextBlock.FontSize%2A> proprietà dell' <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="d46cf-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="d46cf-108">Questo esempio definisce anche un secondo metodo personalizzato chiamato `changeFamily` .</span><span class="sxs-lookup"><span data-stu-id="d46cf-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="d46cf-109">Questo metodo converte la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà dell'oggetto <xref:System.Windows.Controls.ListBoxItem> in un oggetto <xref:System.String> , quindi passa tale valore alla <xref:System.Windows.Controls.TextBlock.FontFamily%2A> proprietà dell' <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="d46cf-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="d46cf-110">Questo esempio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d46cf-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d46cf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d46cf-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
