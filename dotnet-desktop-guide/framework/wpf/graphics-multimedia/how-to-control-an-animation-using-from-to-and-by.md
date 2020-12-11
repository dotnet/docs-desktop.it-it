---
title: "Procedura: controllare un'animazione mediante i valori From, To e By"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966736"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Procedura: controllare un'animazione mediante i valori From, To e By
Con "from/to/by" o "Animation di base" viene creata una transizione tra due valori di destinazione. vedere [Cenni preliminari sull'animazione](animation-overview.md) per un'introduzione a diversi tipi di animazioni. Per impostare i valori di destinazione di un'animazione di base, usare le <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .  Nella tabella seguente viene riepilogato il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> modo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> in cui le proprietà, e possono essere utilizzate insieme o separatamente per determinare i valori di destinazione di un'animazione.  
  
|Proprietà specificate|Comportamento risultante|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore di base della proprietà a cui si sta aggiungendo un'animazione o al valore di output di un'animazione precedente, a seconda della configurazione della precedente animazione.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà al valore specificato dalla somma delle <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà e.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|L'animazione avanza dal valore di base della proprietà animata o da un valore di output di un'animazione precedente al valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> Proprietà.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|L'animazione avanza dal valore di base della proprietà animata o dal valore di output di un'animazione precedente alla somma di tale valore e del valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Proprietà.|  
  
> [!NOTE]
> Non impostare sia la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà che la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà sulla stessa animazione.  
  
 Per usare altri metodi di interpolazione o aggiungere un'animazione tra più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Per ulteriori informazioni, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md) .  
  
 Per informazioni sull'applicazione di più animazioni a una singola proprietà, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
 Nell'esempio seguente vengono illustrati i diversi effetti dell'impostazione delle <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà, e <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> sulle animazioni.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
