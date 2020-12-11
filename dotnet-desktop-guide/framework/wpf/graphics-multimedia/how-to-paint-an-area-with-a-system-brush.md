---
title: "Procedura: disegnare un'area con un pennello di sistema"
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 26511c577bf06b016dfc69cedc7fce2bafb35f32
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965593"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Procedura: disegnare un'area con un pennello di sistema
La <xref:System.Windows.SystemColors> classe fornisce l'accesso ai pennelli e ai colori di sistema, ad esempio <xref:System.Windows.SystemColors.ControlBrush%2A> , <xref:System.Windows.SystemColors.ControlBrushKey%2A> e <xref:System.Windows.SystemColors.DesktopBrush%2A> . Un pennello di sistema è un <xref:System.Windows.Media.SolidColorBrush> oggetto che disegna un'area con il colore di sistema specificato. Un pennello di sistema produce sempre un riempimento a tinta unita e non può essere usato per creare una sfumatura.  
  
 È possibile usare i pennelli di sistema come risorsa statica o dinamica. Usare una risorsa dinamica se si desidera che il pennello si aggiorni automaticamente in caso di modifica mentre l'applicazione è in esecuzione. In caso contrario, usare una risorsa statica. La classe SystemColors contiene un'ampia gamma di proprietà statiche che seguono una rigida convenzione di denominazione:  
  
- *\<SystemColor>* Pennello  
  
     Ottiene un riferimento statico a un oggetto <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
- *\<SystemColor>* BrushKey  
  
     Ottiene un riferimento dinamico a un oggetto <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.  
  
- *\<SystemColor>* Colore  
  
     Ottiene un riferimento statico a una <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
- *\<SystemColor>* ColorKey  
  
     Ottiene un riferimento dinamico alla <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.  
  
 Un colore di sistema è una <xref:System.Windows.Media.Color> struttura che può essere utilizzata per configurare un pennello. Ad esempio, è possibile creare una sfumatura usando i colori di sistema impostando le <xref:System.Windows.Media.GradientStop.Color%2A> proprietà dei <xref:System.Windows.Media.LinearGradientBrush> cursori sfumatura di un oggetto con i colori di sistema. Per un esempio, vedere [usare i colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un riferimento di pennello di sistema dinamico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 L'esempio seguente usa un riferimento di pennello di sistema statico per impostare lo sfondo di un pulsante.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Per un esempio che illustra come usare un colore di sistema in una sfumatura, vedere [usare i colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Vedere anche

- [Usare i colori di sistema in una sfumatura](how-to-use-system-colors-in-a-gradient.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
