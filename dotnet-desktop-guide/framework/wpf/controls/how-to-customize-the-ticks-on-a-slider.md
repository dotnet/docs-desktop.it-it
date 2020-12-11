---
title: 'Procedura: personalizzare i segni di graduazione di un controllo Slider'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 150a546a2c94c1bd552f1f7486652d2b4ad900e3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968644"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="aad57-102">Procedura: personalizzare i segni di graduazione di un controllo Slider</span><span class="sxs-lookup"><span data-stu-id="aad57-102">How to: Customize the Ticks on a Slider</span></span>

<span data-ttu-id="aad57-103">Questo esempio illustra come creare un <xref:System.Windows.Controls.Slider> controllo con segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="aad57-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aad57-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="aad57-104">Example</span></span>  

 <span data-ttu-id="aad57-105">Viene <xref:System.Windows.Controls.Primitives.TickBar> visualizzato quando si imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None> , che corrisponde al valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="aad57-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="aad57-106">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.Slider> con un oggetto <xref:System.Windows.Controls.Primitives.TickBar> che Visualizza i segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="aad57-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="aad57-107">Le <xref:System.Windows.Controls.Slider.TickPlacement%2A> <xref:System.Windows.Controls.Slider.TickFrequency%2A> proprietà e definiscono la posizione dei segni di graduazione e l'intervallo tra di essi.</span><span class="sxs-lookup"><span data-stu-id="aad57-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="aad57-108">Quando si sposta il controllo <xref:System.Windows.Controls.Primitives.Thumb> , le descrizioni comando visualizzano il valore di <xref:System.Windows.Controls.Slider> .</span><span class="sxs-lookup"><span data-stu-id="aad57-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="aad57-109">La <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> proprietà definisce il punto in cui si verificano le descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="aad57-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="aad57-110">I <xref:System.Windows.Controls.Primitives.Thumb> movimenti corrispondono alla posizione dei segni di graduazione perché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostato su `true` .</span><span class="sxs-lookup"><span data-stu-id="aad57-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="aad57-111">Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà per creare segni di graduazione lungo il <xref:System.Windows.Controls.Slider> a intervalli irregolari.</span><span class="sxs-lookup"><span data-stu-id="aad57-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="aad57-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aad57-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="aad57-113">[Procedura: associare un dispositivo di scorrimento a un valore di proprietà](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="aad57-113">[How to: Bind a Slider to a Property Value](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
