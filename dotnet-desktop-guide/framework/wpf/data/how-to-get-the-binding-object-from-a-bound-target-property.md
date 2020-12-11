---
title: "Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969724"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata
Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.

## <a name="example"></a>Esempio
 Per ottenere l'oggetto, è possibile eseguire le operazioni seguenti <xref:System.Windows.Data.Binding> :

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.

 In alternativa, è possibile ottenere <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore della <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Proprietà.

 Per l'esempio completo, vedere [esempio di convalida dell'associazione](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).

> [!NOTE]
> Se l'associazione è un <xref:System.Windows.Data.MultiBinding> , utilizzare <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType> . Se è <xref:System.Windows.Data.PriorityBinding> , usare <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType> . Se non si è certi se la proprietà di destinazione è associata usando <xref:System.Windows.Data.Binding> , <xref:System.Windows.Data.MultiBinding> o, <xref:System.Windows.Data.PriorityBinding> è possibile usare <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType> .

## <a name="see-also"></a>Vedere anche

- [Creare un'associazione nel codice](how-to-create-a-binding-in-code.md)
- [Procedure](data-binding-how-to-topics.md)
