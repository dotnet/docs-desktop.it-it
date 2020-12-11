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
# <a name="how-to-animate-a-popup"></a>Procedura: animare un controllo Popup
Questo esempio illustra due modi per animare un <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente la proprietà viene impostata <xref:System.Windows.Controls.Primitives.PopupAnimation> su un valore di <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide> , che fa sì che l'oggetto venga sottoposto <xref:System.Windows.Controls.Primitives.Popup> a "Slide-in" quando viene visualizzato.  
  
 Per ruotare l'oggetto <xref:System.Windows.Controls.Primitives.Popup> , in questo esempio viene assegnato un oggetto <xref:System.Windows.Media.RotateTransform> alla <xref:System.Windows.UIElement.RenderTransform%2A> proprietà nell'oggetto <xref:System.Windows.Controls.Canvas> , che è l'elemento figlio di <xref:System.Windows.Controls.Primitives.Popup> .  
  
 Per il corretto funzionamento della trasformazione, è necessario che nell'esempio venga impostata la <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà su `true` . Inoltre, nel <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Canvas> contenuto deve essere specificato spazio sufficiente per la rotazione dell'oggetto <xref:System.Windows.Controls.Primitives.Popup> .  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 Nell'esempio seguente viene illustrato come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, che si verifica quando <xref:System.Windows.Controls.Button> si fa clic su un oggetto, attiva l'oggetto <xref:System.Windows.Media.Animation.Storyboard> che avvia l'animazione.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [Procedure](popup-how-to-topics.md)
- [Cenni preliminari sul controllo Popup](popup-overview.md)
