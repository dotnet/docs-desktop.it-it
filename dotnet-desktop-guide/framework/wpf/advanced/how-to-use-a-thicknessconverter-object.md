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
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="60b12-102">Procedura: utilizzare un oggetto ThicknessConverter</span><span class="sxs-lookup"><span data-stu-id="60b12-102">How to: Use a ThicknessConverter Object</span></span>

## <a name="example"></a><span data-ttu-id="60b12-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="60b12-103">Example</span></span>  

 <span data-ttu-id="60b12-104">In questo esempio viene illustrato come creare un'istanza di <xref:System.Windows.ThicknessConverter> e utilizzarla per modificare lo spessore di un bordo.</span><span class="sxs-lookup"><span data-stu-id="60b12-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="60b12-105">Nell'esempio viene definito un metodo personalizzato denominato. `changeThickness` questo metodo converte prima di tutto il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> , come definito in un [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file separato, in un'istanza di <xref:System.Windows.Thickness> e successivamente converte il contenuto in un oggetto <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="60b12-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="60b12-106">Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Windows.Thickness> .</span><span class="sxs-lookup"><span data-stu-id="60b12-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="60b12-107">Questo valore viene quindi passato nuovamente come valore della <xref:System.Windows.Controls.Border.BorderThickness%2A> proprietà dell'oggetto <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="60b12-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="60b12-108">Questo esempio non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="60b12-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="60b12-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60b12-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="60b12-110">[Procedura: modificare la proprietà Margin](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="60b12-110">[How to: Change the Margin Property](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="60b12-111">[Procedura: convertire un oggetto ListBoxItem in un nuovo tipo di dati](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="60b12-111">[How to: Convert a ListBoxItem to a new Data Type](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="60b12-112">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="60b12-112">Panels Overview</span></span>](../controls/panels-overview.md)
