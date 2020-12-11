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
# <a name="how-to-bind-an-adorner-to-an-element"></a>Procedura: associare uno strumento decorativo visuale a un elemento
Questo esempio illustra come associare uno strumento decorativo a livello di codice a un oggetto specificato <xref:System.Windows.UIElement> .  
  
## <a name="example"></a>Esempio  
 Per associare uno strumento decorativo a un particolare <xref:System.Windows.UIElement> , attenersi alla seguente procedura:  
  
1. Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> oggetto per l'oggetto <xref:System.Windows.UIElement> da decorare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> esamina la struttura ad albero visuale, iniziando dall' **oggetto UIElement** specificato e restituisce il primo livello dello strumento decorativo rilevato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).  
  
2. Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo visuale all' **oggetto UIElement** di destinazione.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a <xref:System.Windows.Controls.TextBox> un *oggetto denominato TextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)
