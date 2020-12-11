---
title: 'Procedura: animare un controllo Popup'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967534"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="50ee5-102">Procedura: animare un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="50ee5-102">How to: Animate a Popup</span></span>
<span data-ttu-id="50ee5-103">Questo esempio illustra due modi per animare un <xref:System.Windows.Controls.Primitives.Popup> controllo.</span><span class="sxs-lookup"><span data-stu-id="50ee5-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50ee5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="50ee5-104">Example</span></span>  
 <span data-ttu-id="50ee5-105">Nell'esempio seguente la proprietà viene impostata <xref:System.Windows.Controls.Primitives.PopupAnimation> su un valore di <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide> , che fa sì che l'oggetto venga sottoposto <xref:System.Windows.Controls.Primitives.Popup> a "Slide-in" quando viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="50ee5-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="50ee5-106">Per ruotare l'oggetto <xref:System.Windows.Controls.Primitives.Popup> , in questo esempio viene assegnato un oggetto <xref:System.Windows.Media.RotateTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà nell'oggetto <xref:System.Windows.Controls.Canvas> , che è l'elemento figlio di <xref:System.Windows.Controls.Primitives.Popup> .</span><span class="sxs-lookup"><span data-stu-id="50ee5-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="50ee5-107">Per il corretto funzionamento della trasformazione, è necessario che nell'esempio venga impostata la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="50ee5-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="50ee5-108">Inoltre, nel <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Canvas> contenuto deve essere specificato spazio sufficiente per la rotazione dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> .</span><span class="sxs-lookup"><span data-stu-id="50ee5-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="50ee5-109">Nell'esempio seguente viene illustrato come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, che si verifica quando <xref:System.Windows.Controls.Button> si fa clic su un oggetto, attiva l'oggetto <xref:System.Windows.Media.Animation.Storyboard> che avvia l'animazione.</span><span class="sxs-lookup"><span data-stu-id="50ee5-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="50ee5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50ee5-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="50ee5-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="50ee5-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="50ee5-112">Cenni preliminari sul controllo Popup</span><span class="sxs-lookup"><span data-stu-id="50ee5-112">Popup Overview</span></span>](popup-overview.md)
