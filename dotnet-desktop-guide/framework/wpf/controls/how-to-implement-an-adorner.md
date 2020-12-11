---
title: 'Procedura: implementare strumenti decorativi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965707"
---
# <a name="how-to-implement-an-adorner"></a>Procedura: implementare strumenti decorativi
In questo esempio viene illustrata un'implementazione di Adorner minima.  
  
## <a name="notes-for-implementers"></a>Note per gli implementatori  
 È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.   Un modo comune per implementare il comportamento di rendering consiste nell'eseguire l'override del <xref:System.Windows.UIElement.OnRender%2A> metodo e usare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli oggetti visivi dello strumento decorativo in base alle esigenze, come illustrato in questo esempio.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Uno strumento decorativo personalizzato viene creato implementando una classe che eredita dalla <xref:System.Windows.Documents.Adorner> classe astratta.  Lo strumento decorativo di esempio decora semplicemente gli angoli di un oggetto <xref:System.Windows.UIElement> con i cerchi eseguendo l'override del <xref:System.Windows.UIElement.OnRender%2A> metodo.  
  
### <a name="code"></a>Codice  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli strumenti decorativi visuali](adorners-overview.md)
