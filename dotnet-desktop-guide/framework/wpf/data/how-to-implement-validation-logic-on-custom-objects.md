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
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="df9c2-102">Procedura: implementare la logica di convalida negli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="df9c2-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="df9c2-103">Questo esempio illustra come implementare la logica di convalida in un oggetto personalizzato e quindi associarla.</span><span class="sxs-lookup"><span data-stu-id="df9c2-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df9c2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="df9c2-104">Example</span></span>  
 <span data-ttu-id="df9c2-105">È possibile fornire la logica di convalida sul livello business se l'oggetto di origine implementa <xref:System.ComponentModel.IDataErrorInfo> , come nell'esempio seguente, che definisce un `Person` oggetto che implementa <xref:System.ComponentModel.IDataErrorInfo> :</span><span class="sxs-lookup"><span data-stu-id="df9c2-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="df9c2-106">Nell'esempio seguente, la proprietà Text della casella di testo viene associata alla `Person.Age` proprietà, che è stata resa disponibile per l'associazione tramite una dichiarazione di risorsa a cui è assegnato `x:Key` `data` .</span><span class="sxs-lookup"><span data-stu-id="df9c2-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="df9c2-107"><xref:System.Windows.Controls.DataErrorValidationRule>Verifica gli errori di convalida generati dall'implementazione di <xref:System.ComponentModel.IDataErrorInfo> .</span><span class="sxs-lookup"><span data-stu-id="df9c2-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="df9c2-108">In alternativa, anziché utilizzare <xref:System.Windows.Controls.DataErrorValidationRule> , è possibile impostare la <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="df9c2-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9c2-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df9c2-109">See also</span></span>

- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="df9c2-110">Implementare la convalida dell'associazione</span><span class="sxs-lookup"><span data-stu-id="df9c2-110">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="df9c2-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="df9c2-111">How-to Topics</span></span>](data-binding-how-to-topics.md)
