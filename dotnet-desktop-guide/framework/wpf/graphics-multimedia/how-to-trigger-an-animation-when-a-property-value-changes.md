---
title: "Procedura: attivare un'animazione quando il valore di una proprietà viene modificato"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967972"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Procedura: attivare un'animazione quando il valore di una proprietà viene modificato
Questo esempio illustra come usare un oggetto <xref:System.Windows.Trigger> per avviare un oggetto <xref:System.Windows.Media.Animation.Storyboard> quando viene modificato il valore di una proprietà. È possibile usare un oggetto <xref:System.Windows.Trigger> all'interno di un oggetto <xref:System.Windows.Style> , <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Trigger> per animare l'oggetto <xref:System.Windows.UIElement.Opacity%2A> di un oggetto <xref:System.Windows.Controls.Button> quando la relativa <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà diventa `true` .  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Le animazioni applicate dagli <xref:System.Windows.Trigger> oggetti proprietà si comportano in modo più complesso rispetto alle animazioni <xref:System.Windows.EventTrigger> o alle animazioni avviate mediante i <xref:System.Windows.Media.Animation.Storyboard> metodi.  Le "consegne" con animazioni definite da altri <xref:System.Windows.Trigger> oggetti, ma compongono con <xref:System.Windows.EventTrigger> animazioni attivate dal metodo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Trigger>
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
