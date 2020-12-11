---
title: 'Procedura: implementare la logica di convalida negli oggetti personalizzati'
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: 8520504757e9e9ec9557b84ca2608b4cb99daf62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968575"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Procedura: implementare la logica di convalida negli oggetti personalizzati
Questo esempio illustra come implementare la logica di convalida in un oggetto personalizzato e quindi associarla.  
  
## <a name="example"></a>Esempio  
 È possibile fornire la logica di convalida sul livello business se l'oggetto di origine implementa <xref:System.ComponentModel.IDataErrorInfo> , come nell'esempio seguente, che definisce un `Person` oggetto che implementa <xref:System.ComponentModel.IDataErrorInfo> :  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Nell'esempio seguente, la proprietà Text della casella di testo viene associata alla `Person.Age` proprietà, che è stata resa disponibile per l'associazione tramite una dichiarazione di risorsa a cui è assegnato `x:Key` `data` . <xref:System.Windows.Controls.DataErrorValidationRule>Verifica gli errori di convalida generati dall'implementazione di <xref:System.ComponentModel.IDataErrorInfo> .  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 In alternativa, anziché utilizzare <xref:System.Windows.Controls.DataErrorValidationRule> , è possibile impostare la <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà su `true` .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [Implementare la convalida dell'associazione](how-to-implement-binding-validation.md)
- [Procedure](data-binding-how-to-topics.md)
