---
title: 'Procedura: associare uno strumento decorativo visuale a un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 951643602b09a522d23a6449aefa4be41e051a40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965986"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="c81c6-102">Procedura: associare uno strumento decorativo visuale a un elemento</span><span class="sxs-lookup"><span data-stu-id="c81c6-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="c81c6-103">Questo esempio illustra come associare uno strumento decorativo a livello di codice a un oggetto specificato <xref:System.Windows.UIElement> .</span><span class="sxs-lookup"><span data-stu-id="c81c6-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c81c6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c81c6-104">Example</span></span>  
 <span data-ttu-id="c81c6-105">Per associare uno strumento decorativo a un particolare <xref:System.Windows.UIElement> , attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="c81c6-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="c81c6-106">Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> oggetto per l'oggetto <xref:System.Windows.UIElement> da decorare.</span><span class="sxs-lookup"><span data-stu-id="c81c6-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="c81c6-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> esamina la struttura ad albero visuale, iniziando dall' **oggetto UIElement** specificato e restituisce il primo livello dello strumento decorativo rilevato.</span><span class="sxs-lookup"><span data-stu-id="c81c6-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="c81c6-108">(se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).</span><span class="sxs-lookup"><span data-stu-id="c81c6-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="c81c6-109">Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo visuale all' **oggetto UIElement** di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c81c6-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="c81c6-110">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a <xref:System.Windows.Controls.TextBox> un *oggetto denominato TextBox*.</span><span class="sxs-lookup"><span data-stu-id="c81c6-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> <span data-ttu-id="c81c6-111">Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="c81c6-111">Using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81c6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c81c6-112">See also</span></span>

- [<span data-ttu-id="c81c6-113">Cenni preliminari sugli strumenti decorativi visuali</span><span class="sxs-lookup"><span data-stu-id="c81c6-113">Adorners Overview</span></span>](adorners-overview.md)
