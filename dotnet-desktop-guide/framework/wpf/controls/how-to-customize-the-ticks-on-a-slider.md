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
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Procedura: personalizzare i segni di graduazione di un controllo Slider

Questo esempio illustra come creare un <xref:System.Windows.Controls.Slider> controllo con segni di graduazione.  
  
## <a name="example"></a>Esempio  

 Viene <xref:System.Windows.Controls.Primitives.TickBar> visualizzato quando si imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None> , che corrisponde al valore predefinito.  
  
 Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.Slider> con un oggetto <xref:System.Windows.Controls.Primitives.TickBar> che Visualizza i segni di graduazione. Le <xref:System.Windows.Controls.Slider.TickPlacement%2A> <xref:System.Windows.Controls.Slider.TickFrequency%2A> proprietà e definiscono la posizione dei segni di graduazione e l'intervallo tra di essi. Quando si sposta il controllo <xref:System.Windows.Controls.Primitives.Thumb> , le descrizioni comando visualizzano il valore di <xref:System.Windows.Controls.Slider> . La <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> proprietà definisce il punto in cui si verificano le descrizioni comandi. I <xref:System.Windows.Controls.Primitives.Thumb> movimenti corrispondono alla posizione dei segni di graduazione perché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostato su `true` .  
  
 Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà per creare segni di graduazione lungo il <xref:System.Windows.Controls.Slider> a intervalli irregolari.  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [Procedura: associare un dispositivo di scorrimento a un valore di proprietà](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
