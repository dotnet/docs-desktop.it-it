---
title: 'Procedura: creare un controllo Expander con un controllo ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968125"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="07290-102">Procedura: creare un controllo Expander con un controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="07290-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="07290-103">Questo esempio illustra come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso, ad esempio un'immagine e un testo.</span><span class="sxs-lookup"><span data-stu-id="07290-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="07290-104">Nell'esempio viene inoltre racchiudeto il contenuto di <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="07290-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07290-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="07290-105">Example</span></span>  
 <span data-ttu-id="07290-106">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.Expander> .</span><span class="sxs-lookup"><span data-stu-id="07290-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="07290-107">Nell'esempio viene usato un <xref:System.Windows.Controls.Primitives.BulletDecorator> controllo, che contiene un'immagine e un testo, per definire <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> .</span><span class="sxs-lookup"><span data-stu-id="07290-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="07290-108">Un <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un metodo per lo scorrimento del contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="07290-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="07290-109">Si noti che nell'esempio la <xref:System.Windows.FrameworkElement.Height%2A> proprietà viene impostata su <xref:System.Windows.Controls.ScrollViewer> anziché sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="07290-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="07290-110">Se <xref:System.Windows.FrameworkElement.Height%2A> è impostato sul contenuto, <xref:System.Windows.Controls.ScrollViewer> non consente all'utente di scorrere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="07290-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="07290-111">La <xref:System.Windows.FrameworkElement.Width%2A> proprietà è impostata sul <xref:System.Windows.Controls.Expander> controllo e questa impostazione si applica a <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e al contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="07290-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="07290-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07290-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="07290-113">Cenni preliminari sul controllo Expander</span><span class="sxs-lookup"><span data-stu-id="07290-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="07290-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="07290-114">How-to Topics</span></span>](expander-how-to-topics.md)
